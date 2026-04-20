**KALINGA INSTITUTE OF INDUSTRIAL TECHNOLOGY (KIIT)**

**Final Academic Report**

SAP Order-to-Cash (O2C) — Full Sales Cycle Implementation

| Name           | Adyasha Pattanaik                                 |
|----------------|---------------------------------------------------|
| Roll Number    | 2305590                                           |
| Programme      | B.Tech                                            |
| Specialization | Computer Science and Engineering (CSE)            |
| Course         | SAP Order to Cash                                 |
| University     | Kalinga Institute of Industrial Technology (KIIT) |

# Abstract

This report documents the design, configuration, and execution of an end-to-end Order-to-Cash (O2C) process using SAP ERP. The study is grounded in a realistic business case involving TechVision Enterprises Pvt. Ltd., a fictional electronics distribution company. Seven core transaction steps were executed — from Sales Inquiry (VA11) to Payment Receipt (F-28) — demonstrating the tight integration between SAP's SD, MM, and FI modules. The project highlights how ERP automation eliminates manual inefficiencies, enforces business rules, and provides a fully traceable audit trail across the revenue cycle.

# 1. Introduction

Enterprise Resource Planning (ERP) systems have fundamentally transformed the way organisations manage their business processes. Among the many processes an ERP system can support, the Order-to-Cash cycle is arguably the most revenue-critical — it directly determines how quickly and accurately a company can recognise revenue from its sales activities.

SAP ERP, and its modern successor SAP S/4HANA, provides a robust framework for executing the O2C cycle through the Sales & Distribution (SD) module, with deep integrations into Materials Management (MM) for inventory control and Financial Accounting (FI) for receivables management. This project aims to explore and document this framework through a hands-on, transaction-level walkthrough.

# 2. Literature & Concept Background

The O2C cycle, as described in standard SAP documentation, comprises a sequence of business transactions that transform a customer inquiry into a posted payment. Each transaction generates a numbered document in SAP, and these documents are linked to form an unbroken document flow — a key audit and compliance feature.

Key SAP concepts relevant to this project include:

- Organisational Structure: Sales Org → Distribution Channel → Division → Plant → Storage Location.

- Master Data: Customer Master (XD01), Material Master (MM01), Pricing Conditions.

- Document Flow: The chain of linked SAP documents from inquiry to payment clearing.

- ATP Check: Available-to-Promise check at sales order entry to confirm stock availability.

- Billing Due List: Automated listing of deliveries ready for invoicing.

- Accounts Receivable (AR): The FI sub-ledger tracking money owed by customers.

# 3. Methodology

The project followed a case-study methodology using a sandbox SAP ERP environment. A representative sales scenario was designed for TechVision Enterprises — the sale of 20 units of a high-value server product to a key reseller — and each O2C step was executed using the appropriate SAP transaction code. Screenshots were captured at every step and the generated document numbers were recorded to validate the document flow.

The execution sequence was:

- Step 1: Created Customer Master (CUST-5001) using XD01.

- Step 2: Defined Material Master (MAT-1101) with sales and accounting views using MM01.

- Step 3: Configured basic pricing condition (PR00) and customer discount (K007).

- Step 4: Executed VA11 → VA21 → VA01 → VL01N → VL02N → VF01 → F-28 in sequence.

- Step 5: Verified document flow at each stage using VA03 / VL03N / VF03.

- Step 6: Confirmed zero open AR balance after payment clearing.

# 4. Results & Analysis

All seven O2C steps were executed successfully within the SAP sandbox. The following table summarises the documents generated and the key business outcomes at each stage:

| **Step**        | **T-Code** | **Document Generated**       | **Business Outcome**             |
|-----------------|------------|------------------------------|----------------------------------|
| 1 — Inquiry     | VA11       | Inquiry 1000000021           | Customer requirement captured    |
| 2 — Quotation   | VA21       | Quotation 2000000015         | Price offer formalised           |
| 3 — Sales Order | VA01       | SO 3000001042                | Order confirmed; ATP passed      |
| 4 — Delivery    | VL01N      | Delivery 8000000273          | Goods picked; delivery confirmed |
| 5 — PGI         | VL02N      | Mat. Doc 4900000118          | Stock reduced by 20 units        |
| 6 — Invoice     | VF01       | Invoice 9000002187 (₹28.13L) | Revenue posted in FI             |
| 7 — Payment     | F-28       | Clearing Doc 1500000044      | AR cleared; cycle closed         |

The document flow verification (using VA03's document flow tab) confirmed unbroken linkage across all seven documents, demonstrating full traceability from initial inquiry to final payment. The FI balance for customer CUST-5001 showed a zero open-item balance after the payment posting, confirming complete AR clearance.

# 5. Integration Analysis

The project demonstrated three critical integration points between SAP modules:

- SD ↔ MM Integration: The PGI step (VL02N) automatically triggered a goods movement (Movement Type 601) in MM, reducing the unrestricted stock in storage location SL01 and posting the corresponding COGS entry.

- SD ↔ FI Integration: The billing step (VF01) simultaneously created a billing document in SD and an accounting document in FI, debiting the customer's AR account and crediting the Revenue GL.

- FI Payment ↔ AR Sub-ledger: The incoming payment (F-28) cleared the open item in the customer's AR sub-ledger, ensuring the receivable was removed from the ageing report.

# 6. Challenges Encountered

- Pricing configuration required precise condition type sequencing to ensure discounts applied correctly.

- The ATP check initially failed due to missing plant-level stock setup; resolved by posting initial stock.

- Output type assignment for invoice printing needed manual configuration in the output determination procedure.

# 7. Conclusion

This project successfully demonstrated the complete SAP O2C process through a realistic business scenario. The hands-on execution reinforced several key insights: the power of document flow for audit traceability, the importance of master data completeness for smooth transaction execution, and the efficiency gains achievable through automated credit checks and billing due lists.

SAP's O2C framework eliminates the manual inefficiencies that plague spreadsheet-based sales management, delivering faster billing cycles, stronger credit risk controls, and a complete real-time view of the revenue pipeline. These capabilities make SAP an indispensable tool for any organisation serious about revenue operations.

# 8. References

- SAP SE. (2024). SAP S/4HANA Sales Documentation. SAP Help Portal. https://help.sap.com

- Band, W., & Gupta, A. (2022). SAP SD Certification Guide: Sales and Distribution. Rheinwerk Publishing.

- Jawadekar, W. S. (2011). Management Information Systems: Text and Cases. Tata McGraw-Hill.

- KIIT University. (2025). SAP Order to Cash — Course Curriculum and Lab Manual. School of Computer Engineering.

*— Adyasha Pattanaik \| Roll No. 2305590 \| KIIT University \| 2025–26 —*
