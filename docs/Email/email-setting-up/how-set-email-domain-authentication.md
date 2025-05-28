---
title: Setting Up Email Domain Authentication
excerpt: Learn how to protect your emails from scammers and spammers.
deprecated: false
hidden: false
metadata:
  title: How to Set Up Email Domain Authentication | Yespo Guide
  description: >-
    Email domain authentication is essential for deliverability of your emails.
    It shows email clients that you're a trustworthy sender, and your content
    can be allowed into the Inbox. In the CDP, you can configure domain
    authentication in several easy steps.
  robots: index
next:
  description: ''
---
We offer three options for domain authentication – Full, Full+ and Subdomain – for each of the below DNS (Domain Name System).

[Read more on these options](https://docs.yespo.io/docs/email-domain-configuration).

## <a rel="nofollow" href="https://www.cloudflare.com/" target="_blank"> Cloudflare</a>

Log in to your Cloudflare account, go to the DNS app and click _Add record_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/88b0716c328fe9402d6476ff10e830cac5c1f164b4ad808279bfec428e36b945-DA5.webp",
        "In Cloudflare account, click Add record",
        "How to Set Up Email Domain Authentication"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### Full

To verify your domain within the Full option, add the following records:

#### CNAME

1. In _Type_, select _CNAME_.
2. In _Name_, enter **esputnik.\_domainkey**
3. In _Target_, enter **dkim.esputnik.com.**
4. Click _Save_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5df86323bfc4623044378bdba54fe248ced9e4f7755b41bd9af20514094e642d-DA3.webp",
        "CNAME records",
        "Domain Authentication"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


#### TXT

1. In _Type_, select _TXT_.
2. In _Name_, enter your domain name.
3. In _TTL_, select 1 hour.
4. In Content, enter **v=spf1 include:spf2.esputnik.com ~all**
5. Click _Save_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2e579d117e56ddb22abe2955f4da694289c95c06425c106323f86f0b5ca550aa-DA6.webp",
        "TXT records",
        "Email Domain Authentication"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### Full+

To verify your domain within the Full+ option, add the following records:

#### TXT

1. In _Type_, select _TXT_.
2. In _Name_, enter your subdomain name.
3. In _TTL_, select 1 hour.
4. In _Content_, enter **v=spf1 include:spf2.esputnik.com ~all**
5. Click _Save_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9513d47c43761a65d2ff8f3cc066e3d0c08cb3fa07a9c159eeda63228e5ecfac-DA7.webp",
        "TXT records",
        "Full+"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


#### MX

1. In _Type_, select _MX_.
2. In _Name_, enter your subdomain name.
3. In _Mail server_, enter **trap.esputnik.com.**
4. In _TTL_, select 1 hour.
5. In _Priority_, select 10.
6. Click _Save_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3d06898ce97881e322840cadf885a2014a2439fa1d1cead427a0194376054108-DA1.webp",
        "MX records",
        "How to Configure Email Domain Authentication"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The ready record would look as follows:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c8713faeaebc23b6e6affeb80b259011347e1aaa100d125c063fef9a9df5426c-DA2.webp",
        "",
        "MX record"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/17195652cf6bd275a411a505a9ab1a8864b086dc97e8faabda9d831e950e9882-DA2.webp",
        "The ready MX record",
        "How to Set Up Email Domain Authentication for Full+"
      ],
      "align": "center",
      "sizing": "0px"
    }
  ]
}
[/block]


### Subdomain

The ready record within the Subdomain option would look as follows:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/08c450d2869c514acedc33927a11d6aa11b0ffacb6436743cd734310391d170b-DA4.webp",
        "MX records",
        "Subdomain"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]