# USER API Spec

## Register User API

Endpoint : POST /api/users

Request Body :

```json
{
  "username" : "husni",
  "password" : "rahasia",
  "name" : "Husni Mubarok"
}
```
Response Body Success :

```json
{
  "data" : {
    "username" : "husni",
    "name" : "Husni Mubarok"
  }
}
```
Response Body Error :

```json
{
  "errors" : "Username already registered"
}
```
## Login User API

Endpoint : POST /api/users/login

Request Body : 

```json
{
  "username" : "husni",
  "password" : "rahasia"
}
```
Response Body Success :

```json
{
  "data" : {
    "token" : "unique-token"
  }
}
```
Response Body Error :

```json
{
  "errors" : "Username or Password wrong"
}
```

## Update User API

Endpoint : PATCH /api/users/current

Headers : 
- Authorization : token

Request Body : 

```json
{
  "name" : "Husni Mubarok lagi", //optional
  "password" : "new password" //optional
}
```
Request Body Success :

```json
{
  "data" : {
    "username" : "husni",
    "name" : "Husni Mubarok lagi"
  }
}
```
Response Body Error :

```json
{
  "errors" : "Name length max 1000"
}
```
## Get User API

Endpoint : GET /api/users/current

Headers :
- Authorization : token

Response Body Success :

```json
{
  "data" : {
    "username" : "husni",
    "name" : "Husni Mubarok"
  }
}
```
Response Body Error :

```json
{
  "errors" : "Unauthorized"
}
```
## Logout User API

Endpoint : DELETE /api/users/logout

Headers :
- Authorization : token

Response Body Success : 

```json
{
  "data" : "OK"
}
```
Response Body Error : 

```json
{
  "errors" : "Unauthorized"
}
```