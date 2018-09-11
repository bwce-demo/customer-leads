# customer-leads

1. Run SalesLeadFunction as a Lambda function which creates a lead in Salesforce.

a. Import SalesLeadsFunction.json as a Flogo app. 
b. Configure AWS connection and Salesforce connection
c. Push the app to AWS Lambda


2. Run EmailNotification app on TIBCO Cloud which subsribes to TCM and sends email

a. Import EmailNotification.json as a Flogo app.
b. Configure TCM connection
c. Deploy app on TIBCO Cloud


3. Run CustomerLeads app on TIBCO Cloud which exposes REST API as well as has a Kafka consumer to create customers leads and send email notification.
   This is main flow which invokes SalesLeadFunction lambda function to create lead in salesfoce and publishes message on TCM which is consumed by EmailNotification flow to send email notification.
   
a. Import CustomerLeads.json as a Flogo app.
b. Configure Salesforce connection in GET flow, TCM connection for SendLeadNotification activity and update AWS Lamnda function ARN for CreateSFLead activity in both CreateLeads and Lead Subscriber flows.
c. Deploy app on TIBCO Cloud
