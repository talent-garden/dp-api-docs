# Users
## User Object
An user object contain all of informations of a user.

### Object Fields
| Filed    |      Type      |  <div style="width:100%">Description</div> |
|----------|---------------|------------|
| `id` |    integer   |   Identify the user. |
| `auth0_id` | string |   Identify the user into auth0 system. |
| `first_name` |  string | The firstname of the user. |
| `last_name` |    string   |   The lastname of the user. |
| `full_name` |    string   |   The fullname of the user. |
| `email` |   string   |   The email of the user. |
| `phone_prefix` |   string   |   The phone prefix of the user's number. |
| `phone_number` |   integer   |   The phone number of th euser. |
| `created_at` | timestamp with timezone | Date and time of user creation. |
| `update_at` |    timestamp with timezone  | Date and time of last update data user. |
| `date_of_birth` | date | Date of birthday of the user. |
| `deleted` | boolean | True if the user was deleted. |
## Get All Users

### HTTP Users Request
With this request you can get all informations about the all users.<br></br> **Only admin can use this endpoint** <br></br>
`GET https://api.talentgarden.com/v1/users`

```shell
curl "https://api.talentgarden.com/v1/bookings" \
      -H "Authorization: Bearer YOUR_JWT"
```
> The above command returns JSON structured like this:

```json
{
    "data": [
      {
        "id":"22",
        "auth0_id":"auth0|123456789012345667",
        "first_name":"Mario",
        "last_name":"Rossi",
        "full_name":"Mario Rossi",
        "email":"mariorossi@tag.com",
        "phone_prefix":"+39",
        "phone_number":"2235641240",
        "created_at":"2014-10-08T10:20:10.000Z",
        "updated_at":"2020-11-16T12:15:42.889Z",
        "date_of_birth":"1984-08-28T00:00:00.000Z",
        "deleted":false
      },
      ...
    ]
}
```
### Query Users Parameters
You can use this parameter to filter the users or you can sort them.

Parameter | example | Description
--------- | ------- | --------------
`id` | 24 | Return only users with specified `id`.|
`email` | mariorossi@tag.it | Return only user with speecified `email`.|
`full_name` | mario rossi| Return only user with speecified `full_name`.|
`only_with_phone` | true | return only users with phone_numebr different from null.|
`sortby` | from | Return all bookings sorted by the fields of object.|

## Get Own User Information

### HTTP Users Request
With this request you can get all informations about own user.  <br></br>
`GET https://api.talentgarden.com/v1/users/me`

```shell
curl "https://api.talentgarden.com/v1/users/me" \
      -H "Authorization: Bearer YOUR_JWT"
```

> The above command returns JSON structured like this:

```json
{
        "id":"22",
        "auth0_id":"auth0|123456789012345667",
        "first_name":"Mario",
        "last_name":"Rossi",
        "full_name":"Mario Rossi",
        "email":"mariorossi@tag.com",
        "phone_prefix":"+39",
        "phone_number":"2235641240",
        "created_at":"2014-10-08T10:20:10.000Z",
        "updated_at":"2020-11-16T12:15:42.889Z",
        "date_of_birth":"1984-08-28T00:00:00.000Z",
        "deleted":false
      }
```

## Update User Information

### HTTP Users Request
With this request you can get all information about specific user.
  <br></br>
`PATCH https://api.talentgarden.com/v1/users/:id`

```shell
curl "https://api.talentgarden.com/v1/users/:id" \
      -H "Authorization: Bearer YOUR_JWT"
```

### Body Users Parameters
You can use this parameter to update data of specific user.

Parameter | example | 
--------- | ------- |
`first_name` | mario | 
`last_name` | rossi |
`email` | mariorossi@tag.it| 
`prefix_number` | +39 | 
`phone_number` | 3391029463 | 
`password` | 123456#„«#“‘#789 |

### *Attention*:
to update user's passwords it is necessary that the email field is not present.


## Insert new User's Device Information

### HTTP Users Request
With this request you can insert new user's device.
  <br></br>
`POST https://api.talentgarden.com/v1/users/devices`

```shell
curl "https://api.talentgarden.com/v1/users/devices" \
      -H "Authorization: Bearer YOUR_JWT"
      --data "token": "sdkalsfkhalsfhjalncaukeab","manufacturer": "OnePlus","mac_address": "P1:28:57:13:J2:C4","model": "ONEPLUS A5000","product": "OnePlus5", "platform": "Android"}
```

### Body Device Parameters
You can use this parameter to insert data of specific device.

Parameter | example | 
--------- | ------- |
`token`| sdkalsfkhalsfhjalncaukeabkcjabfkauevbaevkauefkaubvclaevbleaivbalv,
`manufacturer`| OnePlus|
`mac_address`| XX:XS:11:11:X1:X1|
`model`| ONEPLUS A5000|
`product`| OnePlus5|
`platform`| Android |

The **mac_address** parameter is **mandatory**

## Get Own Devices Information

### HTTP Devices Request
With this request you can get all information about own devices.  <br></br>
`GET https://api.talentgarden.com/v1/users/devices`

```shell
curl "https://api.talentgarden.com/v1/users/devices" \
      -H "Authorization: Bearer YOUR_JWT"
```

> The above command returns JSON structured like this:

```json
{
        "id": 1,
        "user_id": "11152",
        "token": "sdkalsfkhalsfhjalncaukeabkcjv",
        "manufacturer": "Iphone XX",
        "mac_address": "c6:00:00:00:f2:c4",
        "model": "XX",
        "product": "OnePlus5",
        "platform": "IOS",
        "created_at": "2021-04-28T07:59:04.146Z"
    }
```