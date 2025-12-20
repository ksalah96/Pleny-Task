# AI Agent Engineer Technical Assessment

##  Project Links
- **n8n Workflow:** https://salah1234.app.n8n.cloud/workflow/qzmqfqVtkKMPqYn2
- **Demo Video:** https://drive.google.com/file/d/1wU4CsJNQsYna8v4n9Jv16wfxfjhTdzvF/view?usp=drive_link

---

##  Approach Overview

This workflow implements a production-ready ETL (Extract, Transform, Load) pipeline with comprehensive error handling and data quality controls. The system fetches user data from the DummyJSON API, applies custom JavaScript transformations to filter and restructure records, then routes data through multiple validation layers including record limiting, domain filtering, and duplicate removal. A conditional branching system classifies users as VIP or Regular based on blood type (O-), directing each category to the appropriate Google Sheets destination. Built-in error handling at the API fetch stage triggers email notifications for any failures, ensuring reliable monitoring and operational visibility.

---

##  Challenges & Solutions

No significant challenges were encountered during development. The workflow architecture was designed with clarity and maintainability in mind, leveraging n8n's native nodes and straightforward JavaScript transformations.

---

##  Testing Instructions

**Simple Execution:**
1. Open the workflow in your n8n instance
2. Click the "Execute Workflow" button
3. Monitor the execution flow as data moves through each node
4. Verify results in the connected Google Sheet

---

## Bonus Features Implementation

###  Retry Logic with Failure Handling
Automatic retry mechanism configured on the Fetch Data node with a 3-second interval between attempts. This resilience feature handles transient network issues and temporary API unavailability, significantly improving workflow reliability.

###  Error Notification System
Email alerting integrated directly into the Fetch Data node's error output. When API failures occur, the system automatically sends detailed notifications to k.salah0610@gmail.com, enabling immediate issue awareness and rapid response.

###  Geographic Data Enrichment
Latitude and longitude coordinates extracted and preserved during data transformation. This geographic enrichment layer adds spatial intelligence to the dataset, enabling location-based analytics, mapping visualizations, and proximity calculations.

###  Conditional Routing Logic
Smart classification system using the If node to evaluate blood type criteria. Users with O- blood type are automatically flagged as VIP and routed to a dedicated processing path, while all others follow the Regular customer flow—ensuring differentiated service levels.

###  Data Deduplication
Email-based duplicate detection prevents redundant record processing. The Remove Duplicates node maintains data integrity by ensuring each unique email address appears only once, protecting against duplicate entries in the destination Google Sheet.

###  Rate Limiting Protection
Processing throttled to 15 records per execution cycle via the Limit node. This safeguard prevents system overload, manages API quota consumption, and ensures controlled data throughput during scheduled automation runs.

---
