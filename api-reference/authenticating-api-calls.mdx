---
id: authenticating-api-calls
title: Authenticating API calls
sidebar_label: Authenticating API calls
description: An article instructing how to authenticate API calls for two versions of an API
toc_max_heading_level: 4
tags: [Developer, Task, Reference]
---

## About this article

A user guide for authenticating calls made to one of my past company’s API. I included this sample in particular because of a few nuances:

1. The API key could only be generated from a user account from the company’s platform, which developers typically would not have. So, I included instructions on how to get this key, but also included links to customer documentation for general users to reference.
2. The authentication method for the API this article documented, the v2 API, was different from v1. However, it was possible at the time that users would still use both APIs at once. Therefore, I had to include the recommended method for authenticating requests in both cases.

This article has been edited to remove proprietary information. 

<hr></hr>

## Authentication 

Acme uses API keys to authenticate requests. To use the Acme v2 API, you **must** authenticate every request you make. Requests without authentication will fail.

### Getting an API key

To get your API key, you must have an Acme platform account.

1. Log in to your Acme account and navigate to Account Settings.
2. Find the Acme API Integration and select Generate Token.
3. Copy your API Key.

:::warning
Your API key is unique to your account and carry many privileges, so keep it secure! Do not share your key with others or store it in publicly accessible areas.
:::

For further details, review our [customer documentation.](https://help.acme.co/docs/integrating-with-the-acme-api)

### Authenticating requests

You can authenticate using your API key as the token with `--header 'X-API-key: <YOUR_API_TOKEN>'`. You do **not** need to provide a password.

For example, to authorize a request to get a list of conversions:

```markup
curl --request GET \
  --url https://app.acme.co/v2/ipsum/ \
  --header 'X-API-key: <YOUR_API_TOKEN>' \
  --header 'Accept: application/json'
```

### Authenticating requests with the v1 API

Authenticating requests with Acme’s v1 API (https://api.acme.co/v1/) is different from authenticating requests with the our v2 API. When authenticating with API v1, you must authenticate with your API key as the bearer token using `--header 'Authorization: Bearer <YOUR_API_TOKEN>'` instead.

If you are using both APIs, then we recommend using both authorization headers in your requests to either domain.

```markup
curl --request GET \
  --url https://app.acme.co/v2/ipsum/ \
  --header 'X-API-key: <YOUR_API_TOKEN>' \
  --header 'Authorization: Bearer <YOUR_API_TOKEN>' \
  --header 'Accept: application/json'
```