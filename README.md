# API Vou de Estrela

## Getting started

First of all, you should ask for the x-api-key to the administrator of the system. This key will be used in every route in this api.

## Check User

The check user route will verify if the username with the phoneNumber exists on EstrelaBet database.

```
curl --location --request POST '{{API_URL}}/check-user' \
--header 'x-api-key: c21dd17d7f786c5d2869aae9a32ca1a3' \
--header 'Content-Type: application/json' \
--data-raw '{
    "username": "teste",
    "phoneNumber": "5531995643212"
}'
```

This is the response on Postman app

```
{
    "data": {
        "username": "teste",
        "phoneNumber": "5531995643212",
        "exists": false,
        "_id": "63c9945dd065d58486e79a00",
        "createdAt": "2023-01-19T19:05:01.675Z",
        "updatedAt": "2023-01-19T19:05:01.675Z",
        "__v": 0
    },
    "message": null,
    "statusCode": 200
}
```

"exists" is the attribute that defines if the user is stored on EstrelaBet database or not.

## Sale

Every sale will be saved on an EstrelaBet database. To confirm the sale, use this route

```
curl --location --request POST 'localhost/sale' \
--header 'x-api-key: c21dd17d7f786c5d2869aae9a32ca1a3' \
--header 'Content-Type: application/json' \
--data-raw '{
    "product": "teste",
    "value": 3.50,
    "username": "testeUser",
    "saleDate": "2023-01-19T19:11:49.649Z"
}'
```
