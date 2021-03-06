---
description: How to fetch a collection of merchants via API
---

# List all merchants

To fetch a collection of merchants, send a `GET` request to the `/api/merchants` endpoint.

{% page-ref page="../../fetching-resources.md" %}

## Request

**GET** https://<i></i>yourdomain.commercelayer.io**/api/merchants**

### **Example**

{% tabs %}
{% tab title="Request" %}
The following request fetches a collection of merchants:

```javascript
curl -X GET \
  https://yourdomain.commercelayer.io/api/merchants/ \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `200 OK` status code, returning a paginated collection of resource objects:

```javascript
{
  "data": [
    {
      "id": "xYZkjABcde",
      "type": "merchants",
      "links": {
        "self": "https://yourdomain.commercelayer.io/api/merchants/xYZkjABcde"
      },
      "attributes": {
        "name": "The Brand Inc.",
        "created_at": "2018-01-01T12:00:00.000Z",
        "updated_at": "2018-01-01T12:00:00.000Z",
        "reference": "ANY-EXTERNAL-REFEFERNCE",
        "reference_origin": "ANY-EXTERNAL-REFEFERNCE-ORIGIN",
        "metadata": {
          "foo": "bar"
        }
      },
      "relationships": {
        "address": {
          "links": {
            "self": "https://yourdomain.commercelayer.io/api/merchants/xYZkjABcde/relationships/address",
            "related": "https://yourdomain.commercelayer.io/api/merchants/xYZkjABcde/address"
          }
        }
      },
      "meta": {
        "mode": "test"
      }
    },
    {
      "other": "... 9 merchants (first page)"
    }
  ],
  "meta": {
    "record_count": 140,
    "page_count": 14
  },
  "links": {
    "first": "https://yourdomain.commercelayer.io/api/merchants?page[number]=1&page[size]=10",
    "next": "https://yourdomain.commercelayer.io/api/merchants?page[number]=2&page[size]=10",
    "last": "https://yourdomain.commercelayer.io/api/merchants?page[number]=14&page[size]=10"
  }
}
```
{% endtab %}
{% endtabs %}

{% page-ref page="../../pagination.md" %}

### Sortable attributes

The list of merchants can be sorted by the following attributes:

* `id`
* `created_at`
* `updated_at`
* `reference`
* `reference_origin`

{% page-ref page="../../sorting-results.md" %}

