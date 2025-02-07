# Clone a pool

Creates a duplicate pool.

An empty pool will be created with the same parameters.

## Request {#request}

{% list tabs %}

- Sandbox

  ```bash
  POST https://sandbox.toloka.yandex.com/api/v1/pools/<pool_id>/clone
  Authorization: OAuth <OAuth token>
  ```

- Production version

  ```bash
  POST https://toloka.yandex.com/api/v1/pools/<pool_id>/clone
  Authorization: OAuth <OAuth token>
  ```

{% endlist %}

## Path parameters {#path-params}

Parameter | Overview
----- | -----
**pool_id** | Pool ID.


## Headers {#headers}

Title | Overview
----- | -----
**Authorization** | A token for account authorization. Add OAuth as a prefix.


## Response {#response}

```json
{
  "id" : "7ea08f99-5e24-47b4-b61f-c177a868d801",
  "type" : "POOL.CLONE",
  "status" : "SUCCESS",
  "submitted" : "2016-04-07T16:06:15.902",
  "started" : "2016-04-07T16:06:15.902",
  "finished" : "2016-04-07T16:06:15.902",
  "progress" : 100,
  "parameters" : {
    "pool_id" : "1"
  },
  "details" : {
    "pool_id" : "2"
  }
}
```

#|
|| Parameter | Overview ||
|| **id** | **string**

User ID. ||
|| **type** | **string**

Type of operation: `POOL.CLONE` — Cloning a pool. ||
|| **status** | **string**

The status of the operation:

- `PENDING` — Not started yet.
- `RUNNING` — In progress.
- `SUCCESS` — Completed successfully.
- `FAIL` — Not completed. ||
|| **submitted** | **string**

The UTC date and time the request was sent, in ISO 8601 format: YYYY-MM-DDThh:mm:ss[.sss]. ||
|| **started** | **string**

The UTC date and time the operation started, in ISO 8601 format: YYYY-MM-DDThh:mm:ss[.sss]. ||
|| **finished** | **string**
The UTC date and time the operation was completed, in ISO 8601 format: YYYY-MM-DDThh:mm:ss[.sss]. ||
|| **progress** | **integer**
The percentage of the operation completed. ||
|| **parameters.pool_id** | **string**
Source pool ID. ||
|| **details.pool_id** | **string**
New pool ID. ||
|#
