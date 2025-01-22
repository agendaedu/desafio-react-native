# Documentação da API 

## Introdução

Iremos descrever agora os dois endpoints que serão necessários para realização
do desafio de seleção do frontend.

## Base URL
`https://frontend-test.agendaedu.com/api/`

## Endpoints

#### 1. /login
- **Descrição**: Retorna um token de autenticação se o login e a senha forem válidos. Para simular um
login com sucesso, você deve utilizar os valores válidos apontados no *Requested Body*
- **Requested Body**:

| Key        | Type           | Required  | Description | Valid Value |
| :--- |:-------------:| :-----:| ---------------:| -------:|
| email| string | **true** | A valid email string | student@ae.com |
| password | string| **true** | A valid password string| 123456 |


- **Request example**: `https://frontend-test.agendaedu.com/api/login`
- **Request method**: POST
- **Request body type**: application/json
- **Response type**: application/json
- **Response example**: 
```

{
    "token": "XXXXXXXX"
}
   
```

#### 2. /events
- **Descrição**: Retorna uma listagem de eventos com seus respectivos atributos, juntamente com um objeto `metadata` que
possui todas as configurações de paginação
- **Headers**:

| Key        | Type           | Required  | Description |
| :--- |:-------------:| :-----:| ---------------:|
| token| string | **true** | Required auth token to get data from api. You can fetch auth token from login endpoint|
| Content-Type | application/json| **true** | Type of the request|

- **Query Parameters**:

| Key        | Type           | Required  | Description |
| :--- |:-------------:| :-----:| ---------------:|
| limit | Integer | **true** | The value of items retrieved from page |
| page | Integer | **true** | The page number |

- **Request example**: `https://frontend-test.agendaedu.com/api/events?limit=1;page=1`
- **Request method**: GET
- **Response type**: application/json
- **Response example**: 
```

{
   "data": [
       {
           "id": 1,
           "title": "Event 1",
           "description": "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque pretium nulla non arcu aliquam rhoncus eu sed leo. Aenean cursus nibh sit amet fringilla sodales. Vestibulum faucibus venenatis tempor. Morbi placerat ac massa id ultricies.",
           "sendAt": "2019-03-07T00:34:35.327Z",
           "image": "https://static.agendaedu.dev/schools/c5c1a933-cdef-4c9b-8a87-490f25c2538d/events/5380/attachments/1550866911-$1-original-poster-agendakids.jpeg",
           "startAt": "2019-07-22T19:01:33.476Z",
           "location": "Fake Street, 1001 - Fortaleza CE"
       }
   ],
   "metadata": {
       "page": 1,
       "limit": 2,
       "pre_page": null,
       "next_page": 2,
       "total": 100,
       "total_pages": 50
   }
}
   
   ```
   
## Considerações finais

Boa sorte no desafio! Qualquer duvida, basta entrar em contato por email!
