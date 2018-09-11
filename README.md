# customer-leads

**Run SalesLeadFunction as a Lambda function. This function creates a lead in Salesforce.**

* Import SalesLeadsFunction.json as a Flogo app. 
* Configure AWS connection and Salesforce connection
* Push the app to AWS Lambda


**Run EmailNotification app on TIBCO Cloud. This app subscribes to TCM and sends email notification.**

* Import EmailNotification.json as a Flogo app.
* Configure TCM connection. Update email id.
* Deploy app on TIBCO Cloud


**Run CustomerLeads app on TIBCO Cloud. This app exposes REST API (CreateLeads) as well as has a Kafka consumer(LeadSubscriber) to create customers leads and send email notification. Both CreateLeads and LeadSubscriber flows invoke SalesLeadFunction lambda function to create lead in salesfoce and publish message on TCM which is consumed by the EmailNotification flow to send email notification.**
   
* Import CustomerLeads.json as a Flogo app.
* Configure Salesforce connection in GET flow, TCM connection for SendLeadNotification activity and update AWS Lamnda function ARN for CreateSFLead activity in both CreateLeads and LeadSubscriber flows.
* Deploy app on TIBCO Cloud
