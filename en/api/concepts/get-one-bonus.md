# Get reward properties

Gets the properties of the reward issued.

## Request {#request}

{% list tabs %}

- Production version

  ```bash
  GET https://toloka.yandex.com/api/v1/user-bonuses/<bonus_id>
  Authorization: OAuth <OAuth token>
  ```

- Sandbox

  ```bash
  GET https://sandbox.toloka.yandex.com/api/v1/user-bonuses/<bonus_id>
  Authorization: OAuth <OAuth token>
  ```
{% endlist %}

## Path parameters {#path-params}

Parameter | Overview
----- | -----
**bonus_id** | ID of the reward issued.


## Headers {#headers}

Title | Overview
----- | -----
**Authorization** | A token for account authorization. Add OAuth as a prefix.


## Response {#response}

Information about a reward.

```json
{
  "user_id": "21c4f092ebad180cf56b9babe0ef9f19",
  "amount": 1.5,
  "assignment_id": "6946cefa-32af-4f62-b530-8d2c71fa2966",
  "private_comment": "Good job!",
  "public_title": {
    "EN": "Completed tasks"
  },
  "public_message": {
    "EN": "10 tasks successfully completed"
  },
  "without_message": false,
  "id": "2092",
  "created": "2021-02-12T10:37:36.631"
}
```

#|
|| Parameter | Overview ||
|| **user_id** | **string**

Toloker ID. ||
|| **amount** | **float**

The dollar amount of the reward. ||
|| **assignment_id** | **string**

ID of the Toloker's response to the task a reward is issued for. ||
|| **private_comment** | **string**

Comments that are only visible to the requester. ||
|| **public_title** | **object**

The subject of the message for the Toloker. You can enter it in multiple languages (the message will be sent in the Toloker's language). Format: "`"<language RU/EN/TR/ID/FR>": "<title text>"`. ||
|| **public_message** | **object**

Message text for the Toloker. You can enter it in multiple languages (the message will be sent in the Toloker's language). Format: `"<language RU/EN/TR/ID/FR>": "<message text>"`. ||
|| **without_message** | **boolean**

Allows you not to send a reward message to the Toloker. The default value is `false`.

To issue a reward without a message, specify `null` for `public_title` and `public_message` and `true` for `without_message`. ||
|| **id** | **string**

Reward ID. ||
|| **created** | **string**

Date the reward was awarded, in UTC using ISO 8601 format: YYYY-MM-DDThh:mm:ss[.sss] ||
|#
