**KALINGA INSTITUTE OF INDUSTRIAL TECHNOLOGY (KIIT)**

**Project Overview**

Business Context & Scope — TechVision Enterprises Pvt. Ltd.

| Name           | Adyasha Pattanaik                                 |
|----------------|---------------------------------------------------|
| Roll Number    | 2305590                                           |
| Programme      | B.Tech                                            |
| Specialization | Computer Science and Engineering (CSE)            |
| Course         | SAP Order to Cash                                 |
| University     | Kalinga Institute of Industrial Technology (KIIT) |

# 1. Company Background

TechVision Enterprises Pvt. Ltd. is a mid-sized electronics distribution company headquartered in Bengaluru, Karnataka. Founded in 2012, the firm distributes networking hardware, enterprise server components, and consumer peripherals to over 400 reseller partners spread across South India. With an annual turnover of approximately ₹85 crore and a workforce of 320 employees, TechVision represents the typical profile of a fast-growing SME transitioning from legacy tools to a full-fledged ERP platform.

# 2. Pre-SAP Challenges

Before the SAP implementation, the following systemic issues were documented:

| **Area**           | **Problem Description**                                                                         |
|--------------------|-------------------------------------------------------------------------------------------------|
| Order Visibility   | Sales teams had no single view of an order's status once it left their inbox.                   |
| Inventory Mismatch | Warehouse and accounts teams maintained separate stock registers, creating frequent mismatches. |
| Billing Delays     | Invoices were prepared manually in MS Excel, taking 3–5 days per billing cycle.                 |
| Credit Risk        | Credit limits were tracked on spreadsheets with no real-time enforcement.                       |
| Revenue Leakage    | Untracked shipments occasionally went unbilled for weeks.                                       |
| Audit Gaps         | No system-level audit trail; disputes had to be resolved by searching email threads.            |

# 3. Solution Scope

The SAP O2C implementation scope for this project covers the following components:

- Customer Master Data creation and maintenance (XD01 / XD02).

- Material Master setup for distributable products (MM01).

- Pricing conditions and customer-specific discount structures.

- Full seven-step O2C transaction execution as detailed in the process guide.

- Integration testing between SD delivery documents and FI payment postings.

# 4. Master Data Used

The following master data objects underpin every transaction in this project:

| **Object**           | **SAP T-Code** | **Example Value**                         |
|----------------------|----------------|-------------------------------------------|
| Customer Master      | XD01           | CUST-5001 — Nexus Tech Solutions, Chennai |
| Material Master      | MM01           | MAT-1101 — HP ProLiant DL380 Server Unit  |
| Sales Organisation   | —              | TVSO — TechVision Sales Org               |
| Distribution Channel | —              | 10 — Direct Sales                         |
| Division             | —              | 20 — Networking & Hardware                |
| Plant                | —              | BLR1 — Bengaluru Dispatch Centre          |
| Storage Location     | —              | SL01 — Main Warehouse                     |

# 5. Business Rules & Assumptions

- All sales are domestic (India) and subject to 18% GST.

- Payment terms: Net 30 days from invoice date.

- Credit limit per customer: ₹20,00,000 (configurable in FD32).

- Minimum order quantity: 5 units per material line.

- Delivery lead time: 3–5 working days from order confirmation.

- Returns are out of scope for this project phase.

# 6. Expected Outcomes

Upon successful completion of this implementation, TechVision Enterprises is expected to achieve:

| **Metric**               | **Target Improvement**                     |
|--------------------------|--------------------------------------------|
| Invoice processing time  | Reduce from 3–5 days to same-day           |
| Billing accuracy rate    | Improve from ~84% to \>99%                 |
| Order-to-delivery cycle  | Standardise at 3 working days              |
| Credit overrun incidents | Eliminate through automated credit checks  |
| Audit readiness          | Full document trail available in real time |

*— Adyasha Pattanaik \| Roll No. 2305590 \| KIIT University \| 2025–26 —*
