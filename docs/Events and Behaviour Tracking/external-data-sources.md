---
title: External Data Sources
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: External Data Sources | Yespo Guide
  description: >-
    Explore our comprehensive guides on External Data Sources. Learn how to
    integrate, manage, and optimize third-party data for enhanced analytics,
    personalized marketing, and improved decision-making
  robots: index
next:
  description: ''
---
Some companies use several platforms to collect and manage customer data. Thus, sometimes you need to add to messages certain content based on customer data tracked or stored at third-party platforms, such as an external CRM, mobile application, database, etc. For example, you want to add to a message personalized product recommendations based on offline sales or orders made via calls and need access to this data.

To access data from third-party sources and use it for content substitution, use a preprocessor or connect to external data sources, such as Google Sheets, BigQuery, PostgreSQL, or HTTP request.

## Importing External Data from Google Sheets

Use [data from Google Sheets](https://docs.yespo.io/docs/how-import-external-data-google-sheets) for recommendations in messages and for contact base segmentation.

## Integration with Google BigQuery

[BigQuery integration](https://docs.yespo.io/docs/google-bigquery-integration) may be really useful in such situations:

- you have CRM where you store a lot of contact data
- you meet problems when creating multiple additional fields in the Yespo or supporting continuous updates of contact data
- you want your data to be stored in one place instead of several databases to get rid of the constant need to store the same info in different places
- you want to build custom reports

## Connecting to PostgreSQL as an External Data Source

To get access to customer data collected via third-party platforms, connect to an [external data source PostgreSQL](https://docs.yespo.io/docs/how-connect-postgresql-external-data-source). Use it to substitute promo codes in triggered campaigns or build complex segments.

## Connecting to HTTP Request as an External Data Source

[HTTP request](https://docs.yespo.io/docs/how-connect-http-request-external-data-source) allows you to automate the creation of message content. This request uploads and sends contact data from Yespo to other systems, and vice versa, transfers data from third-party systems to Yespo.