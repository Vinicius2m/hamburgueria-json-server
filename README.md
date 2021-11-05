# JSON-server-hamburgueria

A api tem um total de 5 endpoints.

URL base:

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
    "email": "exemplo@email.com",
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

### Produtos

`GET /products`

Este end-point irá retornar todos os produtos da API, para usá-lo não precisa de nenhum tipo de autorização e também de nenhum corpo na requisição.

### Carrinho de compras

`POST /cart`

Para adicionar um produto ao carrinho, use este endpoint e passe o token dessa forma:

```json
{
    "Authorization": { "Bearer token"}
}
```

E como próxima informação, passe os dados do produto seguindo o modelo abaixo

```json
{
    "name": "Mc Sundae",
    "category": "Sobremesas",
    "price": 5,
    "img": "link",
    "userId": 2
}
```

`GET /cart?userId=id`

Para ver o carrinho com os produtos, use esse endpoint, nele é passado o userId do usuário logado como Query Params. Passe o token com autorização

```json
{
    "Authorization": { "Bearer token"}
}
```

`DEL /cart/productId`

Para excluir um produto, use esse endpoint, nele é passado o productId do produto a ser excluído como Query Params. Passe o token com autorização dessa forma:

```json
{
    "Authorization": { "Bearer token"}
}
```
