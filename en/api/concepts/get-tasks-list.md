# Get the list of tasks

Gets the list of tasks in the pool.

## Request {#request}

{% list tabs %}

- Production version

  ```bash
  GET https://toloka.yandex.com/api/v1/tasks
  Authorization: OAuth <OAuth token>
  ```

- Sandbox

  ```bash
  GET https://sandbox.toloka.yandex.com/api/v1/tasks
  Authorization: OAuth <OAuth token>
  ```

{% endlist %}

## Headers {#headers}

Title | Overview
----- | -----
**Authorization** | A token for account authorization. Add OAuth as a prefix.


## Query parameters {#query-params}

Specified in the link after the question mark; separated by `&`.

#|
|| Parameter | Overview ||
|| **pool_id** | **string \| required**

ID of the pool to get tasks from. ||
|| **sort** | **string**

Parameters to sort by:

- `id` — Task ID.

- `created` — The task creation date in UTC using ISO 8601 format: YYYY-MM-DDThh:mm:ss[.sss].


To learn how to configure sorting, see [Sorting the list of objects](sorting.md). ||
|| **overlap** | **integer**

Tasks with an overlap equal to the specified value. ||
|| **Standard query parameters** |
[limit](./standard-query-parameters.md#limit), [id_gt](./standard-query-parameters.md#id_gt), [id_gte](./standard-query-parameters.md#id_gte), [id_lt](./standard-query-parameters.md#id_lt), [id_lte](./standard-query-parameters.md#id_lte), [created_gt](./standard-query-parameters.md#created_gt), [created_gte](./standard-query-parameters.md#created_gte), [created_lt](./standard-query-parameters.md#created_lt), [created_lte](./standard-query-parameters.md#created_lte), [overlap_gt](./standard-query-parameters.md#overlap_gt), [overlap_gte](./standard-query-parameters.md#overlap_gte) [overlap_lt](./standard-query-parameters.md#overlap_lt), [overlap_lte](./standard-query-parameters.md#overlap_lte). ||
|#

## Query example {#request-example}

You can set up the display of the list of tasks in parts (for example, 10 tasks at a time):
1. Show the first 10 tasks, starting with the task with the lowest ID.
1. Show the remaining tasks (10 at a time) in ascending order.

**Show the first 10 tasks**

{% list tabs %}

- Production version

  ```bash
  GET https://toloka.yandex.com/api/v1/tasks?sort=id&limit=10
  Authorization: OAuth <OAuth token>
  ```

- Sandbox

  ```bash
  GET https://sandbox.toloka.yandex.com/api/v1/tasks?sort=id&limit=10
  Authorization: OAuth <OAuth token>
  ```
{% endlist %}

**Show the remaining tasks sorted by ascending ID**

{% list tabs %}

- Production version

  ```bash
  GET https://toloka.yandex.com/api/v1/tasks?sort=id&limit=10&id_gt=<ID of the last task from the previous response>
  Authorization: OAuth <OAuth token>
  ```

- Sandbox

  ```bash
  GET https://sandbox.toloka.yandex.com/api/v1/tasks?sort=id&limit=10&id_gt=<ID of the last task from the previous response>
  Authorization: OAuth <OAuth token>
  ```
{% endlist %}

## Response {#response}

Contains task data in the `items` array.

```json
{"items" : [{task 1}, {task 2}, ... {task n}], "has_more": true}
```
