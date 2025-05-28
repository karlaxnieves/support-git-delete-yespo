---
title: Digital Signature Configuration
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Digital Signature Configuration | Yespo Guide
  description: >-
    This article outlines the steps for configuring DNS records and verifying
    your domain to ensure secure email delivery and enhance the trustworthiness
    of your messages
  robots: index
next:
  description: ''
---
Domain digital signatures are a technology that ensures a message has not been altered or tampered with during transmission. Two main mechanisms are used for this:

- **DKIM** (DomainKeys Identified Mail) allows senders to sign emails with a private key and recipients — to verify the authenticity of the signatures using a public key stored in the DNS.
- **SPF** (Sender Policy Framework) checks whether the email comes from an authorized server specified in the domain's DNS record.

Both mechanisms increase the trust of email services in your messages and reduce the likelihood of them being identified as spam.

[Follow this link](https://docs.yespo.io/docs/faq-launching-first-campaign) to find answers to frequently asked questions about digital signatures.

## Configuration Methods

Yespo offers three configuration methods:

1. **Full**: The signature is applied to all emails sent from any mailbox of the main domain (for example, @yourdomain.com).
2. **Full +**: This option adds the ability to sign emails sent from subdomains (for example, @sub.yourdomain.com), providing the highest level of protection, including subdomains.
3. **Subdomain**: The digital signature is applied only to emails sent from a specific subdomain (for example, @sub.yourdomain.com), which is convenient when protecting only certain subdomains.

> 📘 Note
> 
> We recommend setting up the _Full +_ method. If this is impossible due to certain restrictions, choose the _Subdomain_ method.

Next, we will review each configuration option.

### Full

1. Go to _Settings  → Domain verification_ and click the _New domain_ button.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/353be84a34bd5a3c5e8a744523ddd6d6a7ad7669d9c2c1199d2969f8f3fb32ee-digital-signatures-001.webp",
        "New domain",
        "New domain"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. Click _Complex server configuration_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/56f1749d230c7ea62117178e626a40ba73ead2d5c47704e97540c1f0421d5cf0-digital-signatures-002.webp",
        "Complex server configuration",
        "Complex server configuration"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The _Full_ configuration method is selected by default.

3. Click _Next_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/fdf63de38f786c941f51bdb3af9916579b225c429a0a9332ff6c901530dcd7e7-digital-signatures-003.webp",
        "Full configuration",
        "Full configuration"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


4. Specify a domain and click _Start verification_.

> 📘 Note
> 
> Use your domain name instead of **yourdomain.com**.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/17357ad2b42507c28d930ebf4ccdf536dadadae36eebf66e6d016c11148bf7e9-digital-signatures-004.webp",
        "Start verification",
        "Start verification"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Next, the system will check your domain's DNS records and suggest creating new ones or modifying the existing ones.

5. Copy and paste each value from the _Name_ and _Data_ fields into the corresponding record types for your domain.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e4851c2e1202d8ad908c070fdcacaced863872192b23920c76e9f9cf27ad3987-digital-signatures-005.webp",
        "Copy and paste each value",
        "Copy and paste each value"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


6. Set up automatic forwarding for all emails sent to the **bounce+\*** address in your domain to our `bounce@trap.esputnik.com` address.

The“asterisk”  term indicates that any number of valid characters can be placed in its position.

The easiest way to set up such redirection is if your domain's mail is located on Google servers — this service discards the suffix following the plus sign in the address bar. In this case, you just need to create a “bounce” mailbox and configure the forwarding of all incoming emails to `bounce@trap.esputnik.com`.

If your mail is on any service that does not support dropping the suffix after the “plus” symbol, set up a mailbox to store all mail coming to your domain for all non-existent mailboxes. In this mailbox, set up a filter — if the email comes to an address starting with “**bounce+**”, send it to `bounce@trap.esputnik.com`; otherwise, delete it.

The functionality of the forwarding mechanism is checked during the verification stage.

> 📘 Note
> 
> We also recommend that you set up forwarding copies of emails sent to the **abuse** address in your domain to our`abuse@trap.esputnik.com` address. Then we will be able to respond to complaints promptly.

7. Return to your Yespo account and click _Verify domain_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1d799dd8629a84c81de9e865f9344324ffac4f8f495a349dfedfc6d7963acab8-digital-signatures-006.webp",
        "Verify domain",
        "Verify domain"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


After this, the domain status should change to _Domain verified_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6c48fb351739777b620e7f8245aabfd66bcfe6231db4de1392da694b9b4962e6-digital-signatures-007.webp",
        null,
        "Domain verified"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Note
> 
> Some DNS servers need up to 48 hours to apply all changes.

Example of email headers in Gmail after domain verification:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a332a0c4fced70b76c7430cbc7635d3b6163ca25c39c760109dea092d10b5aeb-digital-signatures-008.webp",
        "Example of email headers",
        "Example of email headers"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The email is signed using the DKIM of both our domain and your domain.

### Full +

1. Go to _Settings  → Domain verification_ and click the _New domain_ button.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/91d00f32f344883d70d289e2f2b342210f0ce60ecf1692a245ec40b9d4b5bf0c-digital-signatures-001.webp",
        "New domain",
        "New domain"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. Specify the domain name and an unused name for the technical domain. For example, email, promo, support, or any other. For clarity, let's assume you chose the name **sub**.
3. Click _Start verification_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7024b9192165b86b3f7f6fa10d41a6468ee9ed0d2e58357a430b9559eadf0775-digital-signatures-009.webp",
        "Start verification",
        "Start verification"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Next, the system will check your domain's DNS records and suggest creating new ones or modifying the existing ones.

4. Copy and paste each value from the _Name_ and _Data_ fields into the corresponding record types for your domain.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c00c4810208c78e3406795aed5935b45ebbc8e376890661041fbe26f56beb298-digital-signatures-010.webp",
        "Copy and paste each value",
        "Copy and paste each value"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


5. Return to your Yespo account and click _Verify domain_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e05164318bd2ea0bd9f62e34ce885e34dab3427558f14d81098bcdf44df62f62-digital-signatures-006.webp",
        "Verify domain",
        "Verify domain"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


After this, the domain status should change to _Domain verified_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/bed66658c3e3d3c8bba2929ea324e9099a3281bbf524671d987652c2305833c4-digital-signatures-011.webp",
        "Domain verified",
        "Domain verified"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Example of email headers in Gmail after domain verification:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ee273b45c73d0e283a4055343c591d851f01f08cd5a4fc3172364246e9de4ad4-digital-signatures-012.webp",
        "Example of email headers",
        "Example of email headers"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The email is signed using the DKIM of both our domain and your domain.

### Subdomain

Essentially, this is the same option as _Full_, but on a dedicated subdomain with automatic handling of spam complaints and errors.

This option is also suitable for situations where you want to separate the reputation of your marketing campaigns from transactional and other communications.

1. Go to _Settings  → Domain verification_ and click the _New domain_ button.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1561bc28a60b8871dfb4930a2001c5cd056221305e21a183fe6e413008fedcda-digital-signatures-001.webp",
        " New domain",
        " New domain"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. Click _Complex server configuration_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4dd9777dbec6d3883b2835f240d633726767df1350f4b22ca54b153dd9812b02-digital-signatures-002.webp",
        "Complex server configuration",
        "Complex server configuration"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3. Select _Subdomain_ and click _Next._

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/79d7985932cec344a987bd41fb56a7094db6096781caf88fa23b744a64249000-digital-signatures-013.webp",
        "Select Subdomain",
        "Select Subdomain"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


4. Specify a subdomain and click _Start configuration_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d9fcebe4446508af1da6c26230c30eb5f6a532e93b3544be969bae448f9d0722-digital-signatures-014.webp",
        "Start configuration",
        "Start configuration"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Next, the system will check your domain's DNS records and suggest creating new ones or modifying the existing ones.

5. Copy and paste each value from the _Name_ and _Data_ fields into the corresponding record types for your domain.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/14d4ea25d7ccb314132211119c4e980205563cb32d8a9e24de62b93cb2637e1e-digital-signatures-015.webp",
        "Copy and paste each value",
        "Copy and paste each value"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


6. Return to your Yespo account and click _Verify domain_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/78dacd84a1ae17020006f0b74096194ae9f96eedd30e1c4632a91ede9801d39f-digital-signatures-016.webp",
        "Verify domain",
        "Verify domain"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


After this, the domain status should change to _Domain verified_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e962260d928af825d380ee5339b6cd7bf1bde96bf390a77411ba9845ba564a36-digital-signatures-017.webp",
        "Domain verified",
        "Domain verified"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Example of email headers in Gmail after domain verification:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/46e9269388f7389b770dc689d004b1b95c36cd3d817688f9a2092729ce9fd495-digital-signatures-018.webp",
        "Example of email headers",
        "Example of email headers"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The email is signed using the DKIM of our domain and your subdomain.

> 📘 Note
> 
> - In this option, all mail for the subdomain you select will arrive at our mail servers and be forwarded to your address, which must be specified in the reply field.
> - Your address indicated in the reply field must be valid; you must regularly review it and respond to emails arriving at it. 
> - Recipients can respond to emails and express their desire to unsubscribe from your campaigns. You must immediately unsubscribe such recipients.

See the example of how to set up digital signatures [on Cloudflare >](https://docs.yespo.io/docs/how-set-email-domain-authentication#cloudflare)

## Additional DNS Settings

If necessary, you can grant us access to Postmaster Tools analytics. To do this, we will provide a TXT or CNAME record that needs to be added to the DNS. <a rel="nofollow" href="https://support.google.com/a/answer/183895?hl=en" target="_blank"> More details > </a>

## Checking the Settings Correctness

Yespo has a built-in tool for checking domain settings. If the records are entered in a way that does not meet our recommendations, a warning will appear next to the verification status.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/dbd24d3d78390cdced371e36406ad46d3c11225504d56afb4a7ce6afd260dec0-digital-signatures-019.webp",
        "Warning",
        "Warning"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Click on the warning, and you will see a list of recommendations in the pop-up window.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/fb7ee3f0b9eeadb911600601f01bb846a934dd21429bf8c71e366abe70a4fd2e-digital-signatures-020.webp",
        "List of recommendations",
        "List of recommendations"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Make the recommended changes, and then click _Refresh_.

Any service that allows DNS queries, such as <a rel="nofollow" href="https://dnsquery.org/dnsquery/" target="_blank"> DNS Record Query</a>, can check the availability of your published DNS records to mail servers.

We recommend a free online tool, <a rel="nofollow" href="https://vamsoft.com/support/tools/spf-policy-tester" target="_blank"> SPF Policy Tester</a>, to check that your SPF record is generated correctly and meets the standard's limitations.

## Checking Settings During Operation

Yespo regularly checks to make sure your DNS settings are ok. 

If the settings break, we will notify you by email. Until the issue is resolved, key signing for your domain will be suspended.

Please carefully read emails automatically generated by our service for you. If you receive at least one message about any problem, do not put off solving it for later; immediately contact our support team for help.

## Deleting Domains

Click the trash can icon in the right column to delete a domain and confirm the action.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/32f3167213476cf94de9ba0a4cc2add86e20fb6657aa9ea5c1686a439bbca20c-digital-signatures-021.webp",
        "Deleting domains",
        "Deleting domains"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]