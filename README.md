# Pleny-Task
- Link to your n8n workflow:
    https://salah1234.app.n8n.cloud/workflow/qzmqfqVtkKMPqYn2
- Link to your demo video:
- Brief explanation of your approach:
    I approached this workflow by creating a robust data pipeline that handles the complete ETL process with proper error handling. The workflow fetches user data from an API, transforms     it using custom JavaScript to filter specific email domains and restructure the data format, then applies multiple quality controls including limiting records, filtering unwanted         domains, and removing duplicates. The key decision point uses a conditional branch to classify users as VIP or Regular based on blood type O-, routing them to separate Google Sheets      operations. Error handling is built in at the critical fetch stage, sending email notifications if the API call fails, ensuring reliability and monitoring capabilities for the            automated process.
-Any challenges you faced and how you solved them:
    I didn't face any challenge
- Instructions to test/run your workflow:
    No something specific just run the workflow
- Screenshots of your workflow


- Sample output data

- Description of your bonus feature and why you chose it:
#Retry Logic with Failure Handling: Implemented automatic retry mechanism on the Fetch Data node with a 3-second wait between attempts. This ensures transient network issues or temporary API unavailability don't cause workflow failures, improving overall reliability.

#Error Notification System: Configured the Fetch Data node to trigger a Gmail notification on errors, sending alerts to my email when the API call fails. This proactive monitoring ensures I'm immediately aware of critical issues requiring attention.

#Geographic Data Enrichment: Enhanced the dataset by extracting and preserving latitude/longitude coordinates from the address data during transformation. This geographic enrichment enables potential location-based analytics and mapping capabilities.

#Conditional Routing Logic: Implemented an If node to intelligently route users based on blood type (O- = VIP, others = Regular). This business logic automation ensures proper categorization and differentiated handling of records in the Google Sheets destination.

#Data Deduplication: Added a Remove Duplicates node that checks email addresses to prevent duplicate records from being processed. This maintains data integrity and prevents redundant entries in the final dataset.

#Rate Limiting Protection: Applied a Limit node capping processing to 15 records per execution. This throttling mechanism prevents overwhelming downstream systems and manages API quotas effectively during scheduled runs.
