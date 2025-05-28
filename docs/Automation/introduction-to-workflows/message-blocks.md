---
title: Message Blocks
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Message Blocks | Yespo Guide
  description: >-
    Discover the Message Blocks in marketing automation workflows. Learn how to
    use blocks like Email, SMS, Push Notifications, and more to communicate
    effectively with your audience and drive engagement.
  robots: index
next:
  description: ''
---
The system contains eight *Message blocks*.

<Image align="center" width="80% " src="https://files.readme.io/233e565fd55f6496391603c18e86e341604b0976b6c2da3cb424e5645f8354b7-blocks01.webp" />

A separate article describes [*The One from many block*](https://docs.yespo.io/docs/using-one-many-block) configurations in detail. Next, we will review the parameters of blocks that send one message to one contact.

Each block includes basic and advanced parameters.

## Basic Parameters

<Image align="center" width="80% " src="https://files.readme.io/acb1694ca1ec21c776e0310ae6dfbb7cb7e7483092494ed0b2261708a4e1ecce-message-blocks-301.webp" />

List of Basic Parameters:

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th>
        Parameter
      </th>

      <th>
        Configuration
      </th>

      <th>
        Blocks
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Message
      </td>

      <td>
        Select a pre-created message that will be sent.
      </td>

      <td>
        All
      </td>
    </tr>

    <tr>
      <td>
        Send only in specified hours
      </td>

      <td>
        Activate the toggle to send the message only in specified hours. The option is disabled by default.  

        [See more detailed information >](https://docs.yespo.io/docs/allowed-send-time-messages-workflows)
      </td>

      <td>
        All
      </td>
    </tr>

    <tr>
      <td>
        TTL 
      </td>

      <td>
        Set the period after which the message will not be displayed if it has not been delivered to the contact by that time.\
        By default, 1 day is set. The minimum value is 2 minutes, and the maximum is 28 days.
      </td>

      <td>
        Viber
      </td>
    </tr>

    <tr>
      <td>
        Application  
      </td>

      <td>
        Select the name of the mobile app. If only one app is connected, it will be selected automatically.
      </td>

      <td>
        Mob Push
      </td>
    </tr>

    <tr>
      <td>
        Telegram bot
      </td>

      <td>
        Specify the name of the Telegram bot. It will be selected automatically if only one bot is registered in the account
      </td>

      <td>
        Telegram
      </td>
    </tr>
  </tbody>
</Table>

## Advanced Parameters

You must fill in advanced parameters when using custom event parameters, sending messages to an additional contact, and inserting dynamic content.

<Image align="center" width="80% " src="https://files.readme.io/6bc395ca5fcdcd0da20a005f7a202756568a6ff01e22aa5031793f058a71f7a8-message-blocks-302.webp" />

[More about advanced workflow block parameters >](https://docs.yespo.io/docs/advanced-workflow-block-parameters)
