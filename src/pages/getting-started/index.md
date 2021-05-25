---
title: Authentication
description: Page for Authentication
contributors:
  - https://github.com/khound
---
# Getting started with Photoshop API

To access the Photoshop API, you will need to be authenticated with an Authorization Token and an API Key. Let's create your credentials and make a `hello world` call.

## Get access
Here are the steps to start with our API:

1. If this is your **first time signing up** [click here](https://www.adobe-prerelease.com/sign-up/) and follow the steps on the confirmation modal.

1. If you've **already signed up** and need a new key, sign in to **[the IO Console](https://console.adobe.io/home)**.
1. Click on **Create a new project** under the **Quick Start** section in the middle of your screen.
1. Click on **Add API**.
1. Select the **Adobe Photoshop APIs (Trial)** and click on **Next**.
1. A zip file named **Config** should appear in your downloads. Open the contents of the zip and locate the file name **private.key**.
1. Open the file named **private.key** in a text editor like Atom or Sublime
1. Copy the entire contents of the file and paste it into your project page in the section labeled **Generate access token** and click on **Generate token** on the bottom right-hand corner.
1. Congrats! You've just created a JWT token.

Please note that the token expires every 24 hours and you will have to generate a new one after it expires. See [Automating your JWT token](/authentication/#automating-your-jwt-token) for information on how to automate this process for your application.

You will automatically get an API key when you create your project in Adobe I/O Console. Copy **API KEY (CLIENT ID)** from **Project Overview** page.

## Hello World

Once your token has been created, you can take the following steps  to make your first API call:

1. Open your terminal and paste the code below. Make sure to replace the variables "YOUR_ACCESS_TOKEN"  with the token you generated in the Adobe IO Console.
1. You are also going to need your **API KEY (CLIENT ID)** which can be found in the Adobe IO Console. You will need to paste your API key in the **x-api-key** field.
1. Once all variables have been replaced you can run the command.

``` shell
curl --request GET \
  --url https://image.adobe.io/pie/psdService/hello \
  --header "Authorization: Bearer <YOUR_ACCESS_TOKEN>" \
  --header "x-api-key: <YOUR_CLIENT_ID>"
  ```
Congrats! You just made your first request to the Photoshop API.

`NOTE: Your token will expire every 24 hours and will need to be refreshed after it expires.`

## Automating your JWT token#

Check out these modules for a quick path to automating your token retrieval:

- [JWT Instructions for Python](https://www.datanalyst.info/python/adobe-io-user-management/adobe-io-jwt-authentication-with-python/)
- [JWT Instructions for Node](https://www.npmjs.com/package/@adobe/jwt-auth)

## Additional Service Token and JWT Information

You can find more information on interacting with Adobe IMS API’s and authentication here:
1. [General Authentication Information](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/AuthenticationGuide.md)
2. [JWT/Service Token Authentication](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
3. [IMS API’s](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/Resources/IMS.md)
4. [JWT Sample Code](https://github.com/AdobeDocs/cis-photoshop-api-docs/tree/main/sample-code/jwt-sample-app)
