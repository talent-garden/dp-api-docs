# Bookings
## Booking Object
An booking object contain all of informations of a book.

### Object Fields
| Filed    |      Type      |  <div style="width:100%">Description</div> |
|----------|---------------|------------|
| `room_id` |    integer   |   Identify the room of the book.|
| `user_id` | integer |   Identify the user that book a room. |
| `from` |  timestamp with timezone | Date and time of star of book.  |
| `to` |    timestamp with timezone   |   Date and time of finish book. |
| `created_at` | timestamp with timezone | Date and time of book creation. |
| `update_at` |    timestamp with timezone  | Date and time of last update. |
## Get All Bookings

### HTTP Request
With this request you can get all informations about the all booking. <br></br>
`GET https://api.talentgarden.com/v1/bookings`

```shell
curl "https://api.talentgarden.com/v1/bookings" \
      -H "Authorization: Bearer YOUR_JWT"
```
> The above command returns JSON structured like this:

```json
{
    "data": [
        {
            "id": 64,
            "room_id": "24",
            "user_id": "11152",
            "from": "2021-02-26T08:30:00.000Z",
            "to": "2021-02-26T09:30:00.000Z",
            "created_at": "2021-02-15T16:14:19.000Z",
            "updated_at": "2021-02-15T16:14:19.000Z"
        },
        {
            "id": 75,
            "room_id": "24",
            "user_id": "11152",
            "from": "2021-03-09T08:30:00.000Z",
            "to": "2021-03-09T09:30:00.000Z",
            "created_at": "2021-02-15T17:31:26.000Z",
            "updated_at": "2021-02-15T17:31:26.000Z"
        }
    ]
}
```
### Query Parameters
You can use this parameter to filter the bookings or you can sort them.

Parameter | example | Description
--------- | ------- | --------------
`room_id` | 24 | Return only bookings with specified `room_id`.|
`user_id` | 1 | Return only bookings with speecified `user_id`.|
`sortby` | from | Return all bookings sorted by the fields of object.|

## Get Booking by id

### HTTP Request
With this request you can get all informations about specific book.  <br></br>
`GET https://api.talentgarden.com/v1/bookings/:id`

```shell
curl "https://api.talentgarden.com/v1/bookings/64" \
      -H "Authorization: Bearer YOUR_JWT"
```

> The above command returns JSON structured like this:

```json
{
    "data": [
        {
            "id": 64,
            "room_id": "24",
            "user_id": "11152",
            "from": "2021-02-26T08:30:00.000Z",
            "to": "2021-02-26T09:30:00.000Z",
            "created_at": "2021-02-15T16:14:19.000Z",
            "updated_at": "2021-02-15T16:14:19.000Z"
        }
    ]
}
```

### URL Parameters

Parameter | Description
--------- | -----------
id | The id of the book to retrieve.



## Create new Book

### HTTP Request
With this request you can create a new book.  <br></br>
`POST https://api.talentgarden.com/v1/bookings`

```shell
curl "https://api.talentgarden.com/v1/bookings" \
      -X POST \
      -d {"room_id": "24","from": "2021-03-09T08:30:00.000Z","to": "2021-03-09T09:30:00.000Z"} \
      -H "Authorization: Bearer YOUR_JWT"
```
```json
{
        "id": 75,
        "room_id": "24",
        "user_id": "11152",
        "from": "2021-03-09T08:30:00.000Z",
        "to": "2021-03-09T09:30:00.000Z",
        "created_at": "2021-02-15T17:31:26.000Z",
        "updated_at": "2021-02-15T17:31:26.000Z"
}
```

### Body Parameters
Parameter | Description
--------- | -----------
room_id | The id of the room to book.
from | booking start date and time.
to | booking finish date and time.


## Delete a Specific Booking

### HTTP Request
With this request you can delete a book witth specific id.  <br></br>

`DELETE https://api.talentgarden.com/v1/bookings/:id`

```shell
curl "https://api.talentgarden.com/v1/bookings/64" \
      -X DELETE \
      -H "Authorization: Bearer YOUR_JWT"
```
### URL Parameters

Parameter | Description
--------- | -----------
id | The id of the book to delete.

