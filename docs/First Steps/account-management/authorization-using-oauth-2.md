---
title: Authorization Using OAuth 2.0
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Authorization Using OAuth 2.0 | Yespo Guide
  description: >-
    The document provides a guide on integrating third-party apps with Yespo
    using OAuth 2.0, detailing how to set up authorization, manage access
    rights, register and edit apps, and obtain tokens for secure API access.
  robots: index
next:
  description: ''
---
We recommend setting up authorization using <a rel="nofollow" href="https://oauth.net/2/" target="_blank"> OAuth 2.0</a>  to integrate a third-party app with Yespo.

OAuth 2.0 is an authorization protocol that allows third-party apps to securely access certain Yespo data and capabilities without providing user credentials and API keys.

## Granting Access Rights to Your Yespo Account

You can restrict access to your resources in Yespo with OAuth 2.0. For example:

* Stripo.email allows **only** to export email templates to Yespo.
* A CRM (for example, AmoCRM) allows **only** to add and edit contacts in Yespo when they are changed in the CRM. Or CRM can **also** receive contact activity data and display it on its own.
* A CMS (for example, Wix) **only** allows the use of standard subscription forms to add subscribers directly to Yespo.

Access to Yespo resources is limited by the rights granted during app registration:

* Full access to API
* Access to events
* Access to events and contacts
* Access to messages

You can restrict access to any of the rights from this list.

## Groups of API Methods by Functions in the System

### 1. General Methods

Methods from this group do not require special permissions; only Yespo account authorization is required.

#### 1.1 Protocol version information:

* `GET version`

#### 1.2 Account information:

* `GET account/info`
* `GET balance`
* `GET subscriptions`
* `GET addressbooks`

#### 1.3 Message management

* `POST messages/email`
* `GET messages/email`
* `GET messages/email/{id}`
* `DELETE messages/email/{id}`
* `PUT messages/email/{id}`
* `DELETE messages/email/{id}/{language}`
* `PUT messages/email/{id}/{language}`
* `GET messages/email/{id}/viewLink`
* `GET messages/sms`
* `GET messages/sms/{id}`

#### 1.4 Interface management

* `GET interfaces/email`
* `GET interfaces/sms`

#### 1.5 Statistics

* `GET callouts/sms`
* `GET contact/token/activated/{app_uuid}/{token_id}`
* `PUT contact/token/activated/{app_uuid}/token_id}`
* `PUT interactions/{interaction_id}/status`

### 2. Methods for Updating Contacts and Segments

Typically, integration involves updating contacts rather than reading them. Therefore, you can limit access rights only to updating contacts to avoid data leakage.

* `POST contacts`
* `POST contacts/upload`
* `GET importstatus/{sessionId}`
* ` POST contact`
* `PUT contact/{id}`
* `DELETE contact/{id}`
* `PUT contact/{id}/subscriptions`
* `POST contact/subscribe`
* `POST emails/unsubscribed/add`
* `POST emails/unsubscribed/delete`
* `POST group/{id}/contacts/detach`

### 3. Methods for Reading Contacts and Segments

* `GET contacts`
* `GET contact/{id}`
* `GET contacts/email`
* `GET contact/{id}/subscriptions`
* `GET groups`
* `GET group/{id}/contacts`

### 4. Methods for Obtaining Contact Activity Data

* `GET contacts/activity`

### 5. Methods for Managing Events

* `POST event`
* `POST past_events`
* `DELETE past_events`

### 6. Methods for Managing Messages

* `POST message/{id}/smartsend`
* `POST message/{id}/send OLD`
* `GET message/status`
* `POST message/email`
* `GET message/email/status OLD`
* `POST message/sms`
* `GET message/sms/status OLD`
* `POST message/viber`
* `GET message/viber/status OLD`
* `POST broadcast`
* `GET broadcast/{broadcast_id}`
* `DELETE broadcast/{broadcast_id}`
* `GET broadcasts`

## Registering, Editing, and Deleting an App in Yespo

Before you start integrating using OAuth 2.0, register your app with Yespo.

### App Registration

1. Click on your organization name in the upper right corner and select the **For partners** tab.

<Image align="center" width="80% " src="https://files.readme.io/c82278cc953e051448768738ed01a5fe65fb72c919faaf1253488f4e8761026c-oauth-1.webp" />

2. Click **Register app**.

<Image align="center" width="80% " src="https://files.readme.io/73b7acadc54eba8a05c71fe08373a29b01db2f661035706d1dd1bedb091da466-oauth-2.webp" />

3. Provide app information:

* Name;
* Callback URL – the address to which the service will redirect the user after authorization or authorization refusal (you can create an app without Callback URL and specify it later); 
* Select access scopes. 

<Image align="center" width="80% " src="https://files.readme.io/f804a2c615f3cf847d39c955bb82a5b7650e8717c75648477e448eb37f0a574b-oauth-3.webp" />

4. Click **Register**. 

<Image align="center" width="80% " src="https://files.readme.io/4262f7093a277b33e76a4e4f3c9dd3d3c3eca39f6bd7ad8a3a5fcc89838b4230-oauth-4.webp" />

After registering, the app will be assigned a Client ID and Client Secret. Write them down and store them in a safe and secure storage facility.

<Image align="center" width="80% " src="https://files.readme.io/f23cd4b7b8a558117df45d977dd28d69be7ae7bef9e1c656aadf25f96bf15d90-oauth-5.webp" />

5. Customize the appearance of the authorization form:

* Click **Edit**;

<Image align="center" width="80% " src="https://files.readme.io/3a78ab7a003f1233f8c3e8ae1a952a6de93e9940f3484c1d1bb7b83bc359d50e-oauth-6.webp" />

* Go to the **Authorization form** tab;
* Enter the app name if needed;
* Upload logo: maximum `JPG`, `GIF`, or `PNG` size is **1 MB**; recommended aspect ratio is 1:1 (96×96px); larger images will be cropped to 100% width and center-aligned (you can create an app without a logo and upload it later).

<Image align="center" width="80% " src="https://files.readme.io/4c14e7e3e5748e7bceb4c140d388114d9ce0076eb6730bf81c9360d66ccf7acf-oauth-7.webp" />

After registering the app, a window with information about it will appear on the *Partner apps* tab.

Click on the three dots to preview the authorization form or delete the app. Once deleted, all keys/tokens/integrations will become invalid.

<Image align="center" width="80% " src="https://files.readme.io/5dbf5c259f0faacceeb6a098e99d48dfb04c69c7ce05b858585350ba6e539d67-oauth-8.webp" />

## Integrating with OAuth 2.0

> 📘 Note
>
> The implementation is supported only for apps with a server part, i.e., `response_type=code`.

### 1. Authorization

Send a GET request to the authorization URL `https://uaa.yespo.io/uaa/oauth/authorize`.

The request must contain the Client ID received when registering the app in Yespo.

Request format:

`https://uaa.yespo.io/uaa/oauth/authorize/oauth/authorize?response_type=code&client_id=YOUR_CLIENT_ID&redirect_uri=YOUR_CALLBACK_URL`

As a result, an authorization window will appear.

Enter your Yespo login and password, and confirm access.

The request will be redirected to the Callback URL with the code used to obtain tokens.

> `HTTP/1.1 302 Found  
> Location: http://awesome_host/callback?code=YOUR_CODE`

### 2. Obtaining Access and Refresh Tokens

Send a POST request to the Access Token URL `https://uaa.yespo.io/uaa/oauth/token`.

The request must contain:

* **Client ID** and **Client Secret** that you received when registering the app in Yespo
* **a code** you received during the authorization

Request format:

`https://yespo.io/uaa/oauth/token?grant_type=authorization_code&client_id=YOUR_CLIENT_ID&client_secret=YOUR_CLIENT_SECRET&code=YOUR_CODE&redirect_uri=YOUR_CALLBACK_URL`

In the response, you will receive an Access Token for accessing the Yespo API and a Refresh Token for updating the Access Token.

Response format:

```json
{
  "access_token": "YOUR_TOKEN",
  "token_type": "bearer",
  "refresh_token": "YOUR_REFRESH_TOKEN",
  "scope": "UseRestApi",
  "expires_in": 172541
}
```

> 📘 Note
>
> The validity period of a token starts from the moment of its creation. The default is 172,800 seconds for an Access Token and 2,592,000 seconds for a Refresh Token.

### 3. Refreshing Token

Send a POST request to the Access Token URL `https://uaa.yespo.io/uaa/oauth/token`.

The request must contain:

* **Client ID** and **Client Secret** received when registering the app in Yespo
* **a code** you received during authorization
* **the last refresh token** you received

Request format:

`https://yespo.io/uaa/oauth/token?grant_type=refresh_token&refresh_token=YOUR_REFRESH_TOKEN&client_id=YOUR_CLIENT_ID&client_secret=YOUR_CLIENT_SECRET&code=YOUR_CODE&redirect_uri=YOUR_CALLBACK_URL`

The response contains a new Access Token and a new Refresh Token that should be used the next time the Access Token is refreshed.

### 4. Authorization Testing

Send a GET request to the `https://yespo.io/api/v2/version` URL with authorization in the form of the `Authorization: Bearer <YOUR_ACCESS_TOKEN>` header.

You should see the current API version and API protocol version in the response.

### Example of Authorization Using Python

```python
import requests, json
import subprocess
import sys
authorize_url = "https://uaa.yespo.io/uaa/oauth/authorize"
token_url = "https://uaa.yespo.io/uaa/oauth/token"
callback_uri = "http://my_host:8081/test/callback"
protected_api_contacts = "https://yespo.io/api/v1/contacts"
test_api_url = protected_api_contacts
client_id = 'daf4ba310fe44961fabc80ce2d1f67cd'
client_secret = '6c573654f43bc05c13c6b0d0bc65d6a65fe38a09f84e84ac37c3210e78b06b3e'
#step A - simulate a request from a browser on the authorize_url - will return an authorization code after the user is
# prompted for credentials.
authorization_redirect_url = authorize_url + '?response_type=code&client_id=' + client_id + '&redirect_uri=' + callback_uri
print("go to the following url on the browser and enter the code from the returned url: ")
print("---  " + authorization_redirect_url + "  ---")
authorization_code = input('code: ')
# step I, J - turn the authorization code into a access token, etc
data = {'grant_type': 'authorization_code', 'code': authorization_code, 'redirect_uri': callback_uri}
print("requesting access token")
access_token_response = requests.post(token_url, data=data, verify=False, allow_redirects=False, auth=(client_id, client_secret))
print("response")
print(access_token_response.headers)
print('body: ' + access_token_response.text)
# we can now use the access_token as much as we want to access protected resources.
tokens = json.loads(access_token_response.text)
access_token = tokens['access_token']
print("access token: " + access_token)
api_call_headers = {'Authorization': 'Bearer ' + access_token}
#api_call_response = requests.post(test_api_url, headers=api_call_headers, verify=False, json=json)
api_call_response = requests.get(test_api_url, headers=api_call_headers, verify=False)
print(api_call_response.text)
```

## Connected Apps

Integrated apps are displayed on the *Connected apps* tab in your organization settings. To disconnect an app, click on three dots opposite its name and select the appropriate option.

<Image align="center" width="80% " src="https://files.readme.io/a2b9ae497fb31835ad31dc5b26df66170ad2669f8679df83c7e766c5926eb7bf-connected-apps.webp" />