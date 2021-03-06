---
description: How to fetch a specific webhook via API
---

# Retrieve a webhook

To fetch a single webhook, send a `GET` request to the `/api/webhooks/:id` endpoint, where `id` is the ID of the resource that you want to retrieve.

{% page-ref page="../../fetching-resources.md" %}

## Request

**GET** https://<i></i>yourdomain.commercelayer.io**/api/webhooks/:id**

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches the webhook identified by the id "xYZkjABcde":

```javascript
curl -X GET \
  https://yourdomain.commercelayer.io/api/webhooks/xYZkjABcde \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `200 OK` status code, returning a single resource object:

```javascript
{
  "data": {
    "id": "xYZkjABcde",
    "type": "webhooks",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/webhooks/xYZkjABcde"
    },
    "attributes": {
      "topic": "orders.place",
      "callback_url": "https://yourapp.com/webhooks",
      "include_resources": "[customer, shipping_address, billing_address]",
      "circuit_state": "closed",
      "circuit_failure_count": "5",
      "created_at": "2018-01-01T12:00:00.000Z",
      "updated_at": "2018-01-01T12:00:00.000Z",
      "reference": "ANY-EXTERNAL-REFEFERNCE",
      "reference_origin": "ANY-EXTERNAL-REFEFERNCE-ORIGIN",
      "metadata": {
        "foo": "bar"
      }
    },
    "relationships": {},
    "meta": {
      "mode": "test"
    }
  }
}
```
{% endtab %}
{% endtabs %}

