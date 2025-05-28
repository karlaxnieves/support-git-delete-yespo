---
title: Rate Limits
excerpt: The number of requests the API consumer can make in a second
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
A rate limit is the number of API requests (calls) an app or user can make within a defined time. 

If the number of requests exceeds the limits described in the table below, requests are temporarily blocked (throttled) until the rate limit window resets; the responses return an error with status code `429`.

The methods not listed in this table share a total default rate limit of 200 requests per second.

| Method                        | Request type | Endpoint                                                  | Max requests per second |
| :---------------------------- | :----------- | :-------------------------------------------------------- | :---------------------- |
| Get contact ID by token       | GET          | /api/v1/contact/token/\{app\_uuid}/\{token\_id}/contactId | 150                     |
| Search for contacts           | GET          | /api/v1/contacts                                          | 50                      |
| Generate events v1            | POST         | /api/v1/event                                             | 350                     |
| Generate past events V1       | POST         | /api/v1/past\_events                                      | 100                     |
| Delete events                 | DELETE       | /api/v1/past\_events                                      | 5                       |
| Update interaction status     | PUT          | /api/v1/interactions/\{interaction\_id}/status            | 300                     |
| Get contact's message history | GET          | /api/v2/contacts/messages                                 | 10                      |
| Generate event v2             | POST         | /api/v2/event                                             | 350                     |
| Generate past events V2       | POST         | /api/v2/past\_events                                      | 100                     |
| Get email message             | GET          | /api/v1/messages/email/\{id}                              | 10                      |
