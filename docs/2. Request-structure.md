# Request-structure

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
  "body": "{\n  \"story\": \"string\"\n}"
}
```