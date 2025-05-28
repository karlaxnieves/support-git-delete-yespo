---
title: Location Enrichment for Mobile Events by IP
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Using SDK, you can enrich events with the ip parameter. This allows using the contact's location determined by IP in a workflow and updating it if it changes in the contact card.\
The following parameters are supported in the event structure:

| Parameter   | Description                       |
| :---------- | :-------------------------------- |
| ip          | IP address in IPv4 or IPv6 format |
| countryCode | Country Code in English           |
| countryId   | Country ID                        |
| regionName  | Region name in English            |
| regionId    | Region ID                         |
| cityName    | City name in English              |
| cityId      | City ID                           |

The enrichment functionality is as follows:

* If an event does not contain an IP or location parameters (countryId, countryCode, regionId, regionName, cityId, cityName), the IP parameter is added from the Mobile IP service. Based on this IP, the location parameters are determined, and the contact’s location is updated.
* If the event contains an IP address, the location parameters are added to the event based on IP, and the corresponding location is set for the contact.
* If the event contains an IP address and at least one of the parameters `countryId` - `cityName`, the event is not enriched, and the contact's location is not updated.

Also, you can use this [method](https://docs.yespo.io/docs/how-use-v1event-api-resource#enriching-contact-profile-with-location-by-ip-in-event) to enrich the contact profile with location by IP in events.
