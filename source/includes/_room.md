# Rooms
## Room Object
An booking object contain all of informations of a room.

### Object Fields
| Filed    |      Type      |  <div style="width:100%">Description</div> |
|----------|---------------|------------|
| `campus_id` |    integer   |   Identify the campus of the room.|
| `image_url` | string |   Identify the url of image. |
| `capacity` |  integer | Number of seats in the room.  |
| `name` |    string   |   Name of the room. |
| `description` |    string   |   Description of the room. |
| `created_at` | timestamp with timezone | Date and time of book creation. |
| `update_at` |    timestamp with timezone  | Date and time of last update. |

## Get Rooms By Campus Id

### HTTP Rooms Request
With this request you can get all informations about the all rooms associate with specific campus. <br></br>
The <b>campus_id</b> is <b>mandatory</b>.  <br></br>
`GET https://api.talentgarden.com/v1/rooms?campus_id`

```shell
curl "https://api.talentgarden.com/v1/rooms?campus_id=53" \
      -H "Authorization: Bearer YOUR_JWT"
```
> The above command returns JSON structured like this:

```json
{
    "data": [
        {
            "id": "119",
            "campus_id": 53,
            "image_url": null,
            "capacity": 8,
            "name": "Meeting Room Mezzanine",
            "description": null,
            "created_at": "2019-06-06T11:55:40.000Z",
            "updated_at": "2021-02-12T11:02:44.496Z"
        },
        {
            "id": "120",
            "campus_id": 53,
            "image_url": null,
            "capacity": 5,
            "name": "Meeting Room Floor 2",
            "description": null,
            "created_at": "2019-06-06T12:01:44.000Z",
            "updated_at": "2021-02-12T11:02:44.496Z"
        },
        {
            "id": "121",
            "campus_id": 53,
            "image_url": null,
            "capacity": 5,
            "name": "Meeting Room Floor 3",
            "description": null,
            "created_at": "2019-06-06T12:08:11.000Z",
            "updated_at": "2021-02-12T11:02:44.496Z"
        }
    ]
}
```
### Query Parameters
You can use this parameter to filter the bookings or you can sort them.

Parameter | example | Description
--------- | ------- | --------------
|`campus_id` | 53 | Return only rooms with specified `campus_id`.|
| `capacity` | 4 | Return only rooms with capacity 4.|

## Get Room by id

### HTTP Rooms Request
With this request you can get all informations about specific book.  <br></br>
`GET https://api.talentgarden.com/v1/rooms/:id`

```shell
curl "https://api.talentgarden.com/v1/rooms/119" \
      -H "Authorization: Bearer YOUR_JWT"
```

> The above command returns JSON structured like this:

```json
{
    "id": "119",
    "campus_id": 53,
    "image_url": null,
    "capacity": 8,
    "name": "Meeting Room Mezzanine",
    "description": null,
    "created_at": "2019-06-06T11:55:40.000Z",
    "updated_at": "2021-02-12T11:02:44.496Z"
}
```

### URL Parameters

Parameter | Description
--------- | -----------
id | The id of the book to retrieve.


