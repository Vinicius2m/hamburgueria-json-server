# JSON-server-animes

A api tem um total de 5 endpoints.

URL base: https://json-server-animes.herokuapp.com

## Endpoints:

### Cadastro

`POST/register`

Para fazer uma conta, no corpo da requisição são obrigatórios os três campos abaixo

```json
{
    "email": "exemplo@email.com",
    "password": "123456",
	"name": "Exemplo"
}
```
Caso a operação for bem sucedida a resposta será parecida com esta:

```json
{
  "accessToken": token,
  "user": {
    "email": "exemplo@email.com",
    "name": "Exemplo",
    "id": 3
  }
}
```



### Login

`POST /login`

Na requisição de login será necessário estes campos:

```json
{
  "email": "exe@email.com",
  "password": "123456"
}
```
E a resposta será 

```json
{
  "accessToken": token,
  "user": {
    "email": "exemplo@email.com",
    "name": "Exemplo",
    "id": 3
  }
}
```


### Animes

`GET /animes`

Este end-point irá retornar todos os animes da API, para usá-lo não precisa de nenhum tipo de autorização e também de nenhum corpo na requisição.


### Lista de animes

`POST /myAnimes`

Para cadastrar um novo anime na sua lista pessoal, use este endpoint e passe o token dessa forma:

```json
{
    "Authorization": { "Bearer token"}
}
```

E como próxima informação, passe os dados do anime seguindo o modelo abaixo

```json
{
	"category": "Shonen",
	"anime": "Bleach",
	"userId": 2
}
```

`GET /myAnimes`

Para ver a lista de animes cadastrados, use esse endpoint e passe o token com autorização

```json
{
    "Authorization": { "Bearer token"}
}
```