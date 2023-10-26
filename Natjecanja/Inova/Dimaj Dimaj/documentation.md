# API Documentation

This API provides endpoints for managing lights and doors in a building. Users can register an account, login, and use their authentication token to update and retrieve the state of lights and doors.

## Endpoints

### GET /test

This is a test endpoint that returns a JSON response containing a string.

#### Response

```
{
 "result": "none right now"
}
```

### POST /login

This endpoint allows a user to login to their account. The user must provide their username and password in the request body. The server will respond with a JWT that can be used to authenticate future requests.

#### Request

```
POST /login
Content-Type: application/json

{
  "email": "ivan.horvat@skole.hr",
  "password": "helloworld"
}
```

#### Response

```
{
  "status": "success",
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VySWQiOiIxMjM0NTY3ODkwIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c"
}
```

### POST /register

This endpoint allows a user to register for an account. The user must provide their name, email, password, class (razred), department (odjel), and an invite code in the request body. The server will respond with a JWT that can be used to authenticate future requests.

#### Request

```
POST /register
Content-Type: application/json

{
  "name": "John Doe",
  "email": "johndoe@example.com",
  "password": "password123",
  "razred": 4,
  "odjel": "a",
  "inviteCode": "ABC123"
}
```

#### Response

```
{
  "status": "success",
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VySWQiOiIxMjM0NTY3ODkwIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c"
}
```

### GET /lights/:lightId

This endpoint retrieves the state of a specific light. The user must provide a valid JWT in the authorization header. The `lightId` parameter specifies the ID of the light to retrieve.

#### Request

```
GET /lights/1
Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VySWQiOiIxMjM0NTY3ODkwIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c
```

#### Response

```
{
  "status": "success",
  "on": 1,
  "dimness": 50
}
```

### GET /doors/:doorId

This endpoint retrieves the state of a specific door. The user must provide a valid JWT in the authorization header. The `doorId` parameter specifies the ID of the door to retrieve.

#### Request

```
GET /doors/1
Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VySWQiOiIxMjM0NTY3ODkwIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c
```

#### Response

```
{
  "status": "success",
  "locked": 1
}
```

### PUT /lights/:lightId

This endpoint updates the state of a specific light. The user must provide a valid JWT in the authorization header. The `lightId` parameter specifies the ID of the light to update. The `on` and `dimness` parameters specify the new state of the light.

#### Request

```
PUT /lights/1
Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VySWQiOiIxMjM0NTY3ODkwIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c
Content-Type: application/json

{
  "on": 1,
  "dimness": 50
}
```

#### Response

```
{
  "status": "success",
  "message": "Light state updated"
}
```

### PUT /doors/:doorId

This endpoint updates the state of a specific door. The user must provide a valid JWT in the authorization header. The `doorId` parameter specifies the ID of the door to update. The `locked` parameter specifies the new state of the door.

#### Request

```
PUT /doors/1
Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VySWQiOiIxMjM0NTY3ODkwIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c
Content-Type: application/json

{
  "locked": 1
}
```

#### Response

```
{
  "status": "success",
  "message": "Door state updated"
}
```

### GET /rooms/:roomId/lights

This endpoint retrieves all available information about all lights bound to the given room

#### Request

```
GET /rooms/qFIwoRCxR1tKc8FkkH8k7TG2/lights
Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VySWQiOiIxMjM0NTY3ODkwIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c
```

#### Response

```
{
  "status": "success",
  "lights": [
    {
      "id": "5WQmn8wVvV0dts72XwWJxLUf",
      "name": "Svijetlo 1",
      "on": 1,
      "dimness": 43
    }
  ]
}
```

### GET /rooms/:roomId/doors

This endpoint retrieves all available information about all doors bound to the given room

#### Request

```
GET /rooms/qFIwoRCxR1tKc8FkkH8k7TG2/doors
Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VySWQiOiIxMjM0NTY3ODkwIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c
```

#### Response

```
{
  "status": "success",
  "doors": [
    {
      "id": "leuAu2pxHQesl_B8mhh_Q2Jj",
      "name": "Zavod Vrata",
      "locked": 1
    }
  ]
}
```

### GET /lights

This endpoint retrieves the state of all lights. The user must provide a valid JWT in the authorization header.

#### Request

```
GET /lights
Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VySWQiOiIxMjM0NTY3ODkwIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c
```

#### Response

```
{
  "status": "success",
  "lights": [
    {
      "id": "5WQmn8wVvV0dts72XwWJxLUf",
      "name":"Svijetlo 1",
      "on": 1,
      "dimness": 43,
      "room_id": "qFIwoRCxR1tKc8FkkH8k7TG2"
    },
    {
      "id": "9TIJrTD6XLYd2iCOU1VsEEl7",
      "name":"Svijetlo 2",
      "on": 0,
      "dimness": 55,
      "room_id": "WRmG3CCfwZ_HiOlBshYbAqKe"
    },
    ...
  ]
}
```

### GET /doors

This endpoint retrieves the state of all doors. The user must provide a valid JWT in the authorization header.

#### Request

```
GET /doors
Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VySWQiOiIxMjM0NTY3ODkwIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c
```

#### Response

```
{
  "status": "success",
  "doors": [
    {
      "id": "leuAu2pxHQesl_B8mhh_Q2Jj",
      "name": "Zavod Vrata",
      "locked": 1,
      "room_id": "qFIwoRCxR1tKc8FkkH8k7TG2"
    }
    ...
  ]
}
```

### GET /rooms

This endpoint retrieves information about all rooms. The user must provide a valid JWT in the authorization header.

#### Request

```
GET /rooms
Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VySWQiOiIxMjM0NTY3ODkwIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c
```

#### Response

```
{
  "status": "success",
  "rooms": [
    {
      "id": "qFIwoRCxR1tKc8FkkH8k7TG2",
      "broj": "0301",
      "ime": "Elektronika",
      "uZavodu": 1
    },
    {
      "id": "WRmG3CCfwZ_HiOlBshYbAqKe",
      "broj": "0302",
      "ime": "Elektrotehnika",
      "uZavodu": 0
    },
    {
      "id": "F4vJim6xuG0NYpp7Q0q3l90B",
      "broj": "0303",
      "ime": "TZK",
      "uZavodu": 1
    },
    ...
  ]
}
```
