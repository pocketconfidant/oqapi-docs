---
tags: [readme, index, oqapi, api, guide]
---

# Getting-started with Open Question API (oqapi)

## Prerequisites

> Request access by writitng us about your use-case via [https://pocketconfidant.com/oqapi/](https://pocketconfidant.com/oqapi/)

-   You have an application exposed to Internet able to make POST request to a third-party APIs
-   Your application works with conversational data
-   You have obtained the valid API Subscription Key `oqapi-subscription-key` to access OQAPI.

## Integrating-OQAPI

Integration of OQAPI is a two-step process:

1.  Understand your user's journey and define places where coaching questions should be asked. PocketConfidant customer success team will help you to analyze your application/software value process and spot the best places to integrate questioning.
2.  Send request(s), containting textual message to which questions should be posed. Examples below explain request and response structure.

## Request-structure

This is the method to send requests to a REST API endpoint.

-   **method**: POST
-   **endpoint URL**: <https://oqapi.io/v1/sentences>
-   **request body**
    -   `story`: A text (_string_), typically a size of a paragraph, containing 1-5 sentences of user's story to which questioning should be applied.

```json json_schema
{
  "type": "object",
  "properties": {
    "story": {
      "type": "string"
    }
  }
}
```

-   **headers**
    -   `oqapi-subscription-key`: [required] A key (_string_), to authenticate API client application, provided by PocketConfidant.
    -   `oqapi-app-id`: [required] A key (_string_), allowing to contextualize API behavior and further improve the system.

```json http
{
  "method": "post",
  "url": "https://oqapi.io/v1/sentences",
  "headers": {
    "oqapi-app-id": "",
    "oqapi-subscription-key": "",
    "Content-Type": "application/json"
  },
  "body": "{\n  \"story\": \"At PocketConfidant, our mission is to empower students and learners so that they can develop the best version of themselves and make sense of their academic, professional and personal journey in their own way in order to find study-work-life balance and develop their inner coaching capacity to handle the constant change of our modern world.\"\n}"
}
```

## Best-practices-for-securely-using-API-keys

When you use API keys in your applications, take care to keep them secure. Publicly exposing your credentials can result in your account being compromised, which could lead to unexpected charges on your account. To keep your API keys secure, follow these best practices:

-   Do not embed API keys directly in code: API keys that are embedded in code can be accidentally exposed to the public, for example, if you forget to remove the keys from code that you share. Instead of embedding your API keys in your applications, store them in environment variables or in files outside of your application's source tree.
-   Do not store API keys in files inside your application's source tree: If you store API keys in files, keep the files outside your application's source tree to help ensure your keys do not end up in your source code control system. This is particularly important if you use a public source code management system such as GitHub.
