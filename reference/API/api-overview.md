---
title: API Overview
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
We provide you with a wide range of  API methods designed to transfer data from the backend and frontend of your mobile app to Reteno.

What can you use this data for:

## 1. Adding New Users To Reteno and Updating Their Data
##
Each method from this set has its features for creating and updating users' profiles. Read more to choose those that suit your business goals the best.

## 2. Using Dynamic Content in Messages
##You can send personilized messages with dynamic content via two methods:
1. Use the API resource v1/event (/registerEvent) to insert the dynamic data  from the request body into the message body (in Apache Velocity language). These messages should participate in a workflow.
2. To send dynamic messages without a workflow, use the API resource /v1/message/{id}/smartsend (/sendExtendedPreparedMessage/{id}/). This method can generate personalized content for each recipient too. 

## 3. Creating Workflows Triggered by Events
Use the API resource /v1/event (/registerEvent) to create triggers based on events. Each trigger could launch its own workflow with different message chains, so you always can timely respond to each user's action in your app.

## 4. Streaming Orders 
To stream orders to Reteno, use the resource /v1/orders (/ordersBulkInsert). Streaming orders allows you to collect order data in users' profiles for 
further segmentation, 
personal recommendations generation,
transactional messaging.   

## 5. Getting a Sent Status for a Message
Single messages sent via the resources /v1/message/{id}/smartsend  (/sendExtendedPreparedMessage/{id}/), /v1/message/email (/sendEmail), /v1/message/sms (/sendSms), /v1/message/viber (/sendViber) are sent in the asynchronous mode. To get the status of these messages on your side, call a GET-request of the resource /api/v1/message/status (/getInstantMessagesStatus).