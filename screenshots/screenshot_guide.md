**KALINGA INSTITUTE OF INDUSTRIAL TECHNOLOGY (KIIT)**

**Screenshot Guide**

Naming Conventions & Descriptions for SAP Transaction Screenshots

| Name           | Adyasha Pattanaik                                 |
|----------------|---------------------------------------------------|
| Roll Number    | 2305590                                           |
| Programme      | B.Tech                                            |
| Specialization | Computer Science and Engineering (CSE)            |
| Course         | SAP Order to Cash                                 |
| University     | Kalinga Institute of Industrial Technology (KIIT) |

This guide defines the naming convention and expected content for every screenshot to be captured during the SAP O2C execution. Screenshots must be saved in the /screenshots/ folder of the project repository using the exact filenames listed below. Consistent naming ensures automated document flow verification and easier academic evaluation.

# Naming Convention

Format: \[Step Number\]\_\[TCode\]\_\[short descriptor\].png

Example: 01_VA11_inquiry_creation.png

# Screenshot Checklist

| **\#** | **File Name**                     | **T-Code** | **What to Capture**                                                          |
|--------|-----------------------------------|------------|------------------------------------------------------------------------------|
| 01     | 01_VA11_inquiry_creation.png      | VA11       | Inquiry header with customer CUST-5001 and material MAT-1101 visible         |
| 02     | 02_VA21_quotation_overview.png    | VA21       | Quotation item overview showing price, discount, and validity dates          |
| 03     | 03_VA01_sales_order_header.png    | VA01       | Sales order header with customer, order type OR, and requested delivery date |
| 04     | 04_VA01_sales_order_items.png     | VA01       | Sales order item overview with material, quantity, and net value             |
| 05     | 05_VL01N_delivery_creation.png    | VL01N      | Outbound delivery document with ship-to party and delivery date              |
| 06     | 06_VL02N_picking_confirmation.png | VL02N      | Picking screen showing picked quantity = 20 against delivery                 |
| 07     | 07_VL02N_pgi_posted.png           | VL02N      | Goods Issue posted confirmation message with material document number        |
| 08     | 08_VF01_billing_document.png      | VF01       | Billing document overview with total amount, tax, and accounting doc number  |
| 09     | 09_F28_payment_entry.png          | F-28       | Incoming payment entry screen with customer, amount, and invoice reference   |
| 10     | 10_F28_clearing_confirmation.png  | F-28       | Clearing document posted message with document number                        |
| 11     | 11_VA03_document_flow.png         | VA03       | Complete document flow chain from Inquiry to Clearing Document — all green   |
| 12     | 12_FBL5N_ar_zero_balance.png      | FBL5N      | Customer line items report showing zero open AR balance for CUST-5001        |

# Screenshot Quality Standards

- Resolution: Minimum 1280 × 720 pixels; full-screen captures preferred.

- Format: PNG (preferred) or JPG. Avoid screenshots with compression artefacts.

- Content: Ensure document/order numbers are clearly legible in every screenshot.

- Annotations: Optional — a yellow highlight box may be added around the document number for clarity.

- Sensitive Data: The sandbox environment uses fictional data only; no personal or financial data exposure.

# Document Flow Verification

After completing all seven steps, open the final sales order using VA03, navigate to Environment → Display Document Flow, and verify that each document in the chain has a green status indicator. A fully successful O2C execution will display the following chain:

- Inquiry 1000000021 → Status: Completed

- Quotation 2000000015 → Status: Completed

- Sales Order 3000001042 → Status: Completed

- Delivery 8000000273 → Status: Completed

- Material Document 4900000118 → Status: Goods Issue Posted

- Invoice 9000002187 → Status: Billing Document Posted

- Clearing Document 1500000044 → Status: Cleared

Capture this screen as screenshot 11 (11_VA03_document_flow.png). This is the most important screenshot for academic submission as it proves end-to-end execution.

*— Adyasha Pattanaik \| Roll No. 2305590 \| KIIT University \| 2025–26 —*
