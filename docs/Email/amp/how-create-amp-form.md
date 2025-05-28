---
title: Creating an AMP Form
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: How to Create an AMP Form | Yespo Guide
  description: >-
    Learn how to add a ready block with an AMP form to the email template in the
    drag-n-drop editor. An AMP form can help you collect customer feedback
    straight in the email without using external sources.
  robots: index
next:
  description: ''
---
You can add a ready block _Form_ to the email template to conduct surveys and collect reviews and feedback straight in the email.

> 📘 Note
> 
> To send AMP emails, you need to [register with Google](https://yespo.io/blog/how-apply-sending-amp-powered-emails-within-gmail) as a dynamic sender.

## Step 1. Create a new data service.

A data service is where your users' feedback and responses will be stored.

So far, the service can be created in two ways:

- In <a rel="nofollow" href="https://stripo.email/blog/stripo-data-service/" target="_blank"> Stripo</a>;
- In Zapier.

As an example, let's see how to create a service in Stripo.

1. Create an account in Stripo and enter it.
2. In the toolbar on the left, click _Data → Create your service_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/715eaffebde859d36eaedfc873729719acef6b00435a8d7155127fc09a7907e2-image8.webp",
        "Stripo data service",
        "Data service in Stripo"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3. Enter the service name and description.
4. _Identifier_ and _URL address_ will be filled automatically.
5. _Stripo storage_ is enabled by default. This means that the data collected will be stored on Stripo servers, and you can download the data as a CSV file.
6. If you plan to use external resources for data storage, enable _External storage resources_ and add a link to the resource. This will allow you to store the data in Zapier, Google Sheets or any other data storage assigned to emails via Zapier.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/22f537849b4ca632d95b7dd05f525c01350eb455250fc5b4e2f9071050c88457-service-conf.webp",
        "Service configuration",
        "Service configuration"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Step 2. Create an AMP form in the email.

1. Go to _Messages → Messages_ and click the necessary email or create a new one.
2. In the settings on the left, click Blocks and drag _Form_ to the necessary place in the template. Click _ϟHTML_ to open the general settings.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8ad177697f05b30eb5dbe961c761086657cb2eaca9f04830c3f1c57f35d3a7cf-image17.gif",
        "Add an AMP form to the email template",
        "AMP form in email"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3. In _Service for data collection_, enter the corresponding URL.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a20a901716125e7717fa1bbb30396970591adae1d9938c2b92fd89961ab6bb75-creating-an-amp-form-001.webp",
        "Data service URL",
        "Data service URL"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


4. Click _Add form element_ and select one of the options:

- text input;
- hidden field (used to transmit data without user's input, for example, send the email address or name of the respondent which are already in the database and need no new request);
- switcher;
- multiple choices;
- dropdown select.

We select _Text input_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d2d3f853139652f7819291709cfca57cad64b457c515fb8c7a6a30d3e72c49ac-image18.gif",
        "Select Text input",
        "Text input"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### Configure general settings of the structure.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/427b47d8492f997da625dcaaf0de6adec548eb749c82c5314d96af265d3e472a-creating-an-amp-form-002.webp",
        "General settings of the structure",
        "General settings "
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


- Hide form after submission;

By default, the form in the email will be hidden after the data is successfully submitted. A notification about successful submission will be displayed instead (for example, Thanks for your answer). You can disable the option.

- Background color;

Choose the color in the box menu or enter your code.

- Border;

By default, you configure common settings. Slide a toggle to configure each side separately. You can also choose the type of lines.

- Padding;

By default, you configure common settings. Slide a toggle to configure each side separately.

- Hide element.

This feature is disabled by default. You can enable it to hide the structure on desktop or mobile.

### Edit block elements.

**Input field**

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8580ada56ca8b59b67f882f6ba7a7e7902e4d6777bcf3cc03922459107214888-creating-an-amp-form-003.webp",
        "Input field",
        "Input settings"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


- Click _Label name_ to start editing.
- In _Show label_, enter the main form text. Characters are unlimited. If you only need an input line, slide the toggle left.
- Apply _Required input_ if you use several questions and some of them are required.
- In _Placeholder name_, enter an example of the answer.
- In _Variable_, enter a variable that will help find this particular data faster, for example, in a CSV file. The field supports Latin characters (uppercase/lowercase), numbers and underscore.

> 📘 Important
> 
> To find out which subscriber has submitted a review, go to the structure settings by clicking the _ϟHTML_:

- In _Add form element_, select _Hidden field_.
- Enter the value in _Default value_. We enter %EMAIL% (the responded email address will be inserted).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/17ca4dc5a890516c801997440ef83efd4fce531bc834a6c41ef580afd4536dab-image9.webp",
        "Hidden field",
        "Hidden field settings"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


This field will be hidden for email recipients.

**Button**

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6377031a72c5d5216093739c71852e210737b4a8be721198a633296ee561d46a-creating-an-amp-form-004.webp",
        "Button ",
        "Button in the form"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Click the button and configure its parameters:

- Label;
- Text style;
- Color;
- Highlighted button color;
- Text color;
- Highlighted text color;
- Background color;
- Border radius;
- Alignment;
- Button with icon;
- Adjust to width;
- Border;
- Padding.

The difference between a regular CTA is that this button doesn’t require a link. When clicked, it will show a notification about successful/unsuccessful submission.

**Response to submission**

There are two types of response notifications:

- Green for successful submission;
- Red for failed submission.

Click each container to configure its settings.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4a6768602eab4d9c5a9a2c5b321c8014455ff7469aefeccb87684bc8c4bcd11b-image1.gif",
        "Response to submission",
        "Responses"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### Add an alternative form.

You can add an alternative form so that recipients whose email clients don’t support AMP can also leave feedback.

The easiest way is to create a Google Form or survey in SurveyMonkey. [See how to do it](https://yespo.io/blog/survey-forms-making-how-learn-more-about-your-client).

You can add a link to the created form to any element in the email. As an example, we'll add a link to the button.

- Drag a _Button_ block to the template;
- Edit it and add the link.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/79fa5b9faf57bf34d0bcf78d920b2e9f3ae93b8d7486bfded563d18ea44c6d25-image2.gif",
        "Alternative button",
        "Alternative form"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Important
> 
> Enable _HTML_ for this block to make sure the button is displayed only if the AMP form is not supported.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b5bbc177cc865beec2a1853ed4a228374dfcf88ae23fe73f5720b968d9a1c43c-creating-an-amp-form-005.webp",
        "Enable HTML for alternative button",
        "Enable HTML"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Step 3. Test your form.

After all editing is done, click View message to see how the form is displayed on desktop and mobile in both HTML and AMP HTML.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b2be5a807381a33abe3a40f476994615068e67f7bf56b25108adf6d124366b3c-email-preview.gif",
        "",
        "Email preview"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


In case of any errors, you will see an error notification. Click it to see the error description and fix it. If there is at least one error in the code, the AMP content will not be displayed.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/00a02f3c8193f8d5b09810e03fa258afe91cdfe20a9c2fdb58c5da3bdd9ccb50-image15.webp",
        "Error notification",
        "Error message"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Send a test message to a @gmail or @mail.ru address. If you aren’t whitelisted by Gmail as a dynamic sender, allow dynamic emails from your address in the inbox settings.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/62502e67552b4cda9fc6e6849c8e61d2ed0092eebfa0fe5d70e8498af3743ab6-allow-from-this-sender.webp",
        "Allow dynamic content in Gmail settings",
        "Allow dynamic content in Gmail settings"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


You can also copy the code and send it as a test via <a rel="nofollow" href="https://amp.gmail.dev/playground/" target="_blank"> Gmail AMP for Email Playground</a>.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2980db0ab26e3278a86d584397db856775816564e2ac6aa5146b2f09fee80f0c-creating-an-amp-form-006.webp",
        "Copy email code",
        "Copy the code"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


In the Inbox, the email with AMP content will be marked with a thunder icon at the top.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5fcf0807131ad802a54f3c17ceaf765c4510fc58fea75f0a2940d1f688e3524e-creating-an-amp-form-007.png",
        "AMP email in the Inbox",
        "Amp email in Gmail"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Step 4. Check whether reviews are recorded.

Once you've sent the test, go to your Stripo account → _Data_, click the necessary service and see the statistics. You can also download this report as a CSV file.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9f409455b277aa920f462c8b81e83d20cddac1a93a8c2e47c179e0ab71947548-image3.webp",
        "Data statistics",
        "Stripo statistics"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


When you start sending AMP campaigns, you can see separate analytics on AMP in the general report. Go to _Campaigns → Reports_ and click the right email. The report will show how many recipients opened the AMP version. More on [AMP campaign reports](https://docs.yespo.io/docs/amp-campaign-reports).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f513990be569940b3ec515466b688fa6593d3e2c7a1b974a3f45e295789ed98f-image5.webp",
        "AMP report",
        "AMP email report"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]