**KALINGA INSTITUTE OF INDUSTRIAL TECHNOLOGY (KIIT)**

**O2C Process Guide**

Step-by-Step Execution with T-Codes & Document Flow

| Name           | Adyasha Pattanaik                                 |
|----------------|---------------------------------------------------|
| Roll Number    | 2305590                                           |
| Programme      | B.Tech                                            |
| Specialization | Computer Science and Engineering (CSE)            |
| Course         | SAP Order to Cash                                 |
| University     | Kalinga Institute of Industrial Technology (KIIT) |

This document walks through every stage of the Order-to-Cash cycle as executed in the SAP ERP sandbox for TechVision Enterprises Pvt. Ltd. Each step includes the transaction code (T-Code), the key inputs required, the document number generated, and the link to the next step in the flow.

## Step 1: Sales Inquiry (T-Code: VA11)

A sales inquiry captures an informal request from a prospective customer for information about product availability and pricing. In this scenario, Nexus Tech Solutions (Chennai) inquired about the procurement of 20 units of HP ProLiant DL380 servers.

**Key Inputs:**

- Customer number: CUST-5001

- Material code: MAT-1101

- Requested quantity: 20 units

- Inquiry type: IN (standard)

Output: Inquiry document number generated (e.g., 1000000021)

Document Flow Link: Sales Inquiry → used as reference to create a Quotation

## Step 2: Sales Quotation (T-Code: VA21)

The quotation is a legally binding price offer issued to the customer with a defined validity window. It is created with reference to the inquiry, ensuring full document traceability. The quote included item pricing at ₹1,45,000 per unit with a 3% volume discount.

**Key Inputs:**

- Reference inquiry number

- Validity: 30 days

- Pricing conditions: PR00 + K007 discount

- Payment terms: NT30

Output: Quotation document number generated (e.g., 2000000015)

Document Flow Link: Quotation accepted → Sales Order created

## Step 3: Sales Order (T-Code: VA01)

The sales order is the central document in the O2C cycle. Once the customer confirms the quotation, a binding sales order (SO) is raised with reference to it. The SO triggers credit checks, material availability checks (ATP), and schedule line determination.

**Key Inputs:**

- Reference quotation number

- Requested delivery date

- Sold-to party: CUST-5001

- Order type: OR (Standard Order)

Output: Sales Order number generated (e.g., 3000001042)

Document Flow Link: Sales Order → triggers Delivery creation

## Step 4: Delivery Processing (T-Code: VL01N)

An outbound delivery document is created with reference to the sales order. This step involves picking confirmation — physically picking the goods from storage location SL01 in the Bengaluru Dispatch Centre — and updating the delivery quantity.

**Key Inputs:**

- Shipping point

- Sales Order number

- Delivery date

- Picking quantity: 20 units

Output: Outbound Delivery document created (e.g., 8000000273)

Document Flow Link: Delivery confirmed → Post Goods Issue

## Step 5: Post Goods Issue (PGI) (T-Code: VL02N)

Posting Goods Issue is the pivotal inventory event in O2C. It reduces the unrestricted stock in the plant, posts a COGS (Cost of Goods Sold) entry in FI, and marks the legal transfer of ownership to the customer. After PGI, the delivery document cannot be reversed without a returns process.

**Key Inputs:**

- Outbound delivery number

- Actual goods-issue date

- Movement type: 601

Output: Material document + Accounting document generated

Document Flow Link: PGI posted → Customer Invoice can be raised

## Step 6: Customer Billing / Invoice (T-Code: VF01)

The billing document (customer invoice) is generated from the delivery. SAP automatically picks up the pricing, tax conditions (GST @18%), and payment terms from the sales order. An accounting document is simultaneously created in FI, debiting the customer account and crediting the Revenue and GST liability accounts.

**Key Inputs:**

- Delivery document reference

- Billing type: F2 (standard invoice)

- Billing date

Output: Billing document + FI accounting document created (e.g., Invoice 9000002187)

Document Flow Link: Invoice sent to customer → Await payment

## Step 7: Payment Receipt (T-Code: F-28)

When the customer remits payment, the incoming payment is posted against the open invoice in the customer's AR sub-ledger. This clears the outstanding receivable and completes the O2C cycle. Bank reconciliation entries are made automatically if the house bank is configured.

**Key Inputs:**

- Customer account: CUST-5001

- Invoice reference number

- Amount received

- Payment date

- House bank / GL account

Output: Clearing document posted; AR open item = ZERO

Document Flow Link: Cycle complete — Document flow fully linked

# End-to-End Document Flow Summary

| **Document Type** | **T-Code** | **SAP Doc No. (Example)** | **Links To**   |
|-------------------|------------|---------------------------|----------------|
| Sales Inquiry     | VA11       | 1000000021                | → Quotation    |
| Sales Quotation   | VA21       | 2000000015                | → Sales Order  |
| Sales Order       | VA01       | 3000001042                | → Delivery     |
| Outbound Delivery | VL01N      | 8000000273                | → PGI          |
| PGI (Mat. Doc)    | VL02N      | 4900000118                | → Invoice      |
| Customer Invoice  | VF01       | 9000002187                | → Payment      |
| Payment Clearing  | F-28       | 1500000044                | → Cycle Closed |

*— Adyasha Pattanaik \| Roll No. 2305590 \| KIIT University \| 2025–26 —*
