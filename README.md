# 🧾 SAP Order-to-Cash (O2C) — Full Sales Cycle

**KALINGA INSTITUTE OF INDUSTRIAL TECHNOLOGY (KIIT)**

**SAP Order-to-Cash (O2C)**

Full Sales Cycle — Project Overview

| Name           | Adyasha Pattanaik                                 |
|----------------|---------------------------------------------------|
| Roll Number    | 2305590                                           |
| Programme      | B.Tech                                            |
| Specialization | Computer Science and Engineering (CSE)            |
| Course         | SAP Order to Cash                                 |
| University     | Kalinga Institute of Industrial Technology (KIIT) |

# 1. Introduction

The Order-to-Cash (O2C) cycle is the backbone of any revenue-generating enterprise. It encompasses every touchpoint from the moment a customer expresses interest in a product to the moment their payment is reconciled in the company's books. This project documents the complete O2C implementation inside SAP ERP, using the SAP Sales & Distribution (SD) and Financial Accounting (FI) modules as the primary workhorses.

The chosen business context is TechVision Enterprises Pvt. Ltd., a fictitious mid-tier electronics distribution company operating across South India. Their product catalogue includes networking hardware, server components, and consumer peripherals.

# 2. Business Problem Statement

Before adopting SAP, TechVision Enterprises relied heavily on disconnected spreadsheets and email approvals to manage their sales pipeline. This decentralised approach introduced a host of operational pain points:

- Absence of real-time visibility into open orders and pending deliveries.

- Manual invoice preparation leading to frequent billing discrepancies.

- No automated credit-limit verification, resulting in credit overruns.

- Inventory levels were updated only at month-end, causing stock-out scenarios.

- Revenue recognition was delayed because payment postings were done manually.

- Customer satisfaction declined due to unpredictable delivery timelines.

# 3. Project Objectives

- Configure and execute the full seven-step O2C process within SAP SD.

- Demonstrate the document-flow linkage from Sales Inquiry through to Payment Receipt.

- Illustrate the integration points between the SD, MM, and FI modules.

- Produce academic-grade documentation suitable for examination and future reference.

- Reflect real-world business scenarios through a consistent company case study.

# 4. SAP Modules Involved

| **Module** | **Full Name**        | **Function in O2C**                                          |
|------------|----------------------|--------------------------------------------------------------|
| SD         | Sales & Distribution | Manages inquiries, quotations, orders, delivery, and billing |
| MM         | Materials Management | Handles stock verification and goods-issue confirmation      |
| FI         | Financial Accounting | Processes customer invoices and incoming payment postings    |

# 5. High-Level Workflow

| **Step** | **Activity**        | **T-Code** | **Description**                                      |
|----------|---------------------|------------|------------------------------------------------------|
| Step 1   | Sales Inquiry       | VA11       | Customer requests product/price information          |
| Step 2   | Sales Quotation     | VA21       | Formal quote with validity period issued to customer |
| Step 3   | Sales Order         | VA01       | Customer accepts; binding order document created     |
| Step 4   | Delivery Processing | VL01N      | Outbound delivery document created; goods picked     |
| Step 5   | Post Goods Issue    | VL02N      | Inventory reduced; legal ownership transferred       |
| Step 6   | Customer Billing    | VF01       | Tax-compliant invoice generated from delivery        |
| Step 7   | Payment Receipt     | F-28       | Incoming payment posted; AR open item cleared        |

# 6. Project Structure

| **File / Folder**     | **Purpose**                                                 |
|-----------------------|-------------------------------------------------------------|
| README.md           | Project overview, objectives, and module summary            |
| project_overview.md | Detailed business context for TechVision Enterprises        |
| o2c_process.md      | Step-by-step process guide with T-Codes and screenshots     |
| final_report.md     | Consolidated academic report (6–8 pages)                    |
| screenshot_guide.md | Naming conventions and descriptions for all SAP screenshots |
| /screenshots/         | Folder containing all captured SAP transaction screens      |

# 7. Key Learnings

- Understood how SAP uses document flow to maintain an unbroken audit trail.

- Gained hands-on familiarity with the SD transaction codes used in real deployments.

- Appreciated the three-way integration between SD (sales), MM (inventory), and FI (finance).

- Recognised how automated credit checks protect companies from revenue leakage.

- Developed the ability to trace any billing dispute back to its originating sales inquiry.

# 8. Disclaimer

This project has been developed exclusively for academic purposes as part of the SAP Order to Cash course offered at KIIT University. All company names, customer names, material codes, and financial figures used herein are entirely fictional and bear no resemblance to any real organisation.

*— Adyasha Pattanaik \| Roll No. 2305590 \| KIIT University \| 2025–26 —*
