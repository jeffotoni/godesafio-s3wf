# Go S3wf Challenge

A simple test for our s3wf members who will work with GO remotely.

We will create a SERVER API to be consumed by an APP.

The api will have to be made using standard Go stdlib.

Some libs to handle cors, session, rate limit, and JWT, database are all allowed except for full frameworks, but libs are.

The database to be used is POSTGRESQL and Mongo

## Endpoints that we will develop using mongo

| Endpoint              | Method |
|-----------------------|:------:|
| /ping                 |  POST  |
| /auth                 |  POST  |
| /user                 |  POST  |
| /user                 |  PUT   |
| /user                 | DELETE |
| /user/{:uuid}         |  GET   |


## Endpoints that we will develop using Postgres

| Endpoint              | Method |
|-----------------------|:------:|
| /order                |  POST  |
| /order/{:id}          |  GET   |

## Ping
Ping is public, you will not have control just to know if our server is online.

## Auth

This endpoint will have a header with Authorization and will send via JSON login and password in a method [POST].
It will return a JSON when it fails and a successful JSON with the jwt token.

All Auth is to be done in Mongo, users must be in Mongo.

**HTTP/2 200**
```json
{  
   "status":"success",
   "msg":"User found and generated token",
  "tokenjwt":"eyJhbGciOi-RkOM8Hjc5DYNJuqyEy3gvy_IMjcu2w-hl2yHilvPNP_UK0ocUxaKdsD5oS5fV-TYlfH_k",
   "expires":"2020-03-20",
   "tokenmsg":"use the token to access the endpoints!",
   "Login":{ 
      "id":4287,
      "uuiduser":"301cd1b2d60d5bd5f143c352dfdc0a4dd44517f0",
      "avatarurl":"http://mydomain.com/user/user.jpg",
      "avatartype":"image/jpeg",
      "name":"Junior S3WF",
      "datastart":"2020-03-20"
   }
}
```

**HTTP/2 500**
```json
{  
   "status":"error",
   "message":"User cannot be authenticated!"
}
```

## User

This endpoint will only bring user information such as uuid, name, cpf, email and surname in JSON format.
It will send a method [GET] passing in the header the token and in the url the user's uuid and will receive a JSON.

## Order

This endpoint will create an order with the following fields

idorder, uuiduser, product name, product id, price, payment type, discount coupon, shipping delivery, record date and time of recording.


What is important in this test:

  - Code organization
 
  - Use good practices
 
  - Always leave the business rule as uncoupled as possible
 
  - JWT is not mandatory, just simulate if you can't
 
  - A lib for routes like belt or gorillamux is acceptable
 
  - Create the test mocks
 
  - Create the database and tables to dump and put in the project so that we can validate and test
 
## good luck...



