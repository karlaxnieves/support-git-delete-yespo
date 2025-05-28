---
title: Guide on Delivering Email to Apple User Relay Address
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Guide on Delivering Email to Apple User Relay Address | Yespo Guide
  description: >-
    Learn how to set up your newsletters to be delivered to your subscribers'
    Apple's Private Email Relay.
  robots: index
next:
  description: ''
---
**Apple’s Private Email Relay** is a service that helps protect user privacy by assigning randomly generated relay addresses that forward emails to the user’s real email. If your business sends transactional or marketing emails to Apple users, ensuring proper email deliverability to these relay addresses is essential.

## 1. Understanding Apple User Relay Addresses

Apple assigns a unique, anonymized email address for users signing up with **"Sign in with Apple"**. These addresses use the domain `@privaterelay.appleid.com` and forward emails to the user's actual inbox while maintaining privacy.

## 2. Prerequisites for Sending Emails

Before sending emails to Apple’s relay addresses, ensure:

* You have a registered Apple Developer Account.
* Your domain is properly verified with Apple’s Private Email Relay service.
* You use authenticated email-sending methods (SPF, DKIM, DMARC).

## 3. Steps to Register and Verify Your Domain

1. Log in to <a rel="nofollow" href="https://developer.apple.com/" target="_blank">Apple Developer</a>.
2. Navigate to **Certificates, IDs & Profiles** and select **Service configuration**.

<Image align="center" width="40% " src="https://files.readme.io/dd79e1999ef4ae1014f2d582108b44e00feca8af99d85c2f33cdc3b7235b01fe-Apple_1.png" />

3. Click **+** next to *Email Sourses*.

<Image align="center" width="80% " src="https://files.readme.io/94bdf74ccd025324fd127e7dd8f188b20bb88fce3299f994ac050517e9079565-Apple_2.png" />

4. Enter **your sending domain** in the **Domains and Subdomains** section and click **Next**.

<Image align="center" width="40% " src="https://files.readme.io/38404b987cbbda9f3d766230469fb2b8574bc20c370b6e56bc1c56a269872ce8-Apple_3.png" />

5. Confirm your email sources by clicking **Register**.

<Image align="center" width="40% " src="https://files.readme.io/31bf2e40cc84d916e814a907a294774b9a6ddb1db74f525f0a7d8d169ac93b80-Apple_4.png" />

Your **verified domain** will appear in the **Email Sources** list.

<Image align="center" width="80% " src="https://files.readme.io/682bbce12d4af3c08d48f7b3d512596d39f25addfa7977dce94f3a8557706589-Apple_5.png" />
