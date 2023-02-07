# API Vou de Estrela

## Getting started

First of all, you should ask for the x-api-key to the administrator of the system. This key will be used in every route in this api.

## Check User

The check user route will verify if the username with the phoneNumber exists on EstrelaBet database.

```
curl --location --request GET '{{VOU_DE_ESTRELA_URL}}/check-user?username=teste&phoneNumber=5531995643212' \
--header 'x-api-key: c21dd17d7f786c5d2869aae9a32ca1a3'
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

Exists is the attribute that defines if the user is stored on EstrelaBet database or not.

## Check if the user is allowed to participate of the promo

```
curl --location --request GET '{{VOU_DE_ESTRELA_URL}}/check-promo-allowed?username=userTest&value=32' \
--header 'x-api-key: c21dd17d7f786c5d2869aae9a32ca1a3'
```

Response looks like this

```
{
    "data": {
        "isValid": true
    },
    "message": null,
    "statusCode": 200
}
```

## Sale

Every sale will be saved on an EstrelaBet database. To confirm the sale, use this route

```
curl --location --request POST '{{VOU_DE_ESTRELA_URL}}/sale' \
--header 'x-api-key: c21dd17d7f786c5d2869aae9a32ca1a3' \
--header 'Content-Type: application/json' \
--data-raw '{
    "product": "teste",
    "value": 3.50,
    "username": "testeUser",
    "saleDate": "2023-01-19T19:11:49.649Z"
}'
```
