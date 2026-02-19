# Errors

List of common errors returned by the passport API.

All passport API errors are returned in the following format:

```json
{
  "errorReport": {
    "protocol_id": 0,
    "error_msg": "<error_key>",
    "error_no": 7
  }
}
```

## errorReport Fields

| Field       | Type   | Description                 |
|-------------|--------|-----------------------------|
| protocol_id | int    | Protocol ID                 |
| error_msg   | string | Error key (see table below) |
| error_no    | int    | Numeric error code          |

## Error Keys

| Key                                  | Message                                                                              |
|--------------------------------------|--------------------------------------------------------------------------------------|
| `common_network_connect_failed`      | Network connection failed. Please try again.                                         |
| `common_network_data_cant_analysis`  | Network error. Data analysis failed.                                                 |
| `sunborn_error_email`                | You must enter an Email                                                              |
| `sunborn_error_phone_number`         | Incorrect phone number                                                               |
| `sunborn_error_password_format`      | Enter a password between 6-20 alphanumeric characters and symbols                    |
| `sunborn_error_password`             | Incorrect password                                                                   |
| `sunborn_error_non_existent_account` | The account does not exist                                                           |
| `sunborn_error_non_existent_email`   | The account does not exist                                                           |
| `sunborn_error_password_or_account`  | Login failed. Incorrect Username or Password. Please try again.                      |
| `sunborn_error_password_or_email`    | Login failed. Incorrect Email or Password. Please try again.                         |
| `sunborn_error_email_existent`       | The account already exists. Please log in to your account.                           |
| `sunborn_error_account_existent`     | The account already exists. Please log in to your account.                           |
| `sunborn_error_account_inactive`     | Unactivated account. Please activate your account via the link sent to your mailbox. |
| `sunborn_error_email_inactive`       | Unactivated account. Please activate your account via the link sent to your mailbox. |
| `sunborn_error_account_ban`          | Your account has been locked. Please contact our Customer Service Center.            |
| `sunborn_error_authenticating`       | Authentication server is busy. Please try again.                                     |
| `sunborn_error_reg_number`           | Too many submissions. Please try again after %d m.                                   |
| `sunborn_error_use_number`           | Too many attempts. Please try again after %d m.                                      |

> **Note:** `%d` in error messages is a placeholder for a number of minutes returned by the server.

> **Note:** `error_no` numeric codes are not yet fully mapped. Values observed so far: `2` = unknown error, `7` =
> incorrect credentials. This section will be updated as more values are captured.