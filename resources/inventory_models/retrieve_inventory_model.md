---
description: How to fetch a specific inventory model via API
---

# Retrieve an inventory model

To fetch a single inventory model, send a `GET` request to the `/api/inventory_models/:id` endpoint, where `id` is the ID of the resource that you want to retrieve.

{% page-ref page="../../fetching-resources.md" %}

## Request

**GET** https://<i></i>yourdomain.commercelayer.io**/api/inventory_models/:id**

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches the inventory model identified by the id "xYZkjABcde":

```javascript
curl -X GET \
  https://yourdomain.commercelayer.io/api/inventory_models/xYZkjABcde \
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
    "type": "inventory_models",
    "links": {
      "self": "https://yourdomain.commercelayer.io/api/inventory_models/xYZkjABcde"
    },
    "attributes": {
      "name": "EU Inventory Model",
      "stock_locations_cutoff": "3",
      "created_at": "2018-01-01T12:00:00.000Z",
      "updated_at": "2018-01-01T12:00:00.000Z",
      "reference": "ANY-EXTERNAL-REFEFERNCE",
      "reference_origin": "ANY-EXTERNAL-REFEFERNCE-ORIGIN",
      "metadata": {
        "foo": "bar"
      }
    },
    "relationships": {
      "stock_levels": {
        "links": {
          "self": "https://yourdomain.commercelayer.io/api/inventory_models/xYZkjABcde/relationships/stock_levels",
          "related": "https://yourdomain.commercelayer.io/api/inventory_models/xYZkjABcde/stock_levels"
        }
      }
    },
    "meta": {
      "mode": "test"
    }
  }
}
```
{% endtab %}
{% endtabs %}

