# json-server-base

Esse é o repositório com a base de JSON-Server + JSON-Server-Auth já configurada, feita para ser usada no desenvolvimento das API's nos Capstones do Q2.

## Endpoints

Assim como a documentação do JSON-Server-Auth traz (https://www.npmjs.com/package/json-server-auth), existem 3 endpoints que podem ser utilizados para cadastro e 2 endpoints que podem ser usados para login.

### Cadastro

POST /register <br/>
POST /signup <br/>
POST /users

Qualquer um desses 3 endpoints irá cadastrar o usuário na lista de "Users", sendo que os campos obrigatórios são os de email e password.
Você pode ficar a vontade para adicionar qualquer outra propriedade no corpo do cadastro dos usuários.

### Login

POST /login <br/>
POST /signin

Qualquer um desses 2 endpoints pode ser usado para realizar login com um dos usuários cadastrados na lista de "Users"

---

### Tech - Tecnologias cadastradas pelos usuários

Nessa rota da api, os usuários cadastram as tecnologias que tem conhecimento. Há get (consulta), sem necessidade de autorização e o post (envio) que cadastra as tecnologias na api, com necessidade de autorização.

#### GET /tech - Rota pública. Todos podem acessar.

Ex resposta:
[
{
"tech": "React",
"userId": 1,
"id": 1
},
{
"tech": "React",
"userId": 1,
"id": 2
}
]

#### POST /tech - Rota privada. Apenas usuários autorizados podem utilizar

post =>
{
"tech": "ReactJS",
"userId":1
}

return =>
{
"tech": "ReactJS",
"userId": 1,
"id": 3
}

---

### Work - Trabalhos cadastradas pelos usuários

Nessa rota da api, os usuários cadastram os trabalhos que realizaram. As duas requisições precisam de autorização: Get (consulta) e o Post (envio) que cadastra os trabalhos na api.

#### GET /work - Consulta

Ex resposta:
[
{
"work": "Facebook Page",
"userId": 1,
"id": 1
}
]

#### POST /tech - Cadastro

post =>

{
"work": "Facebook Page",
"userId":1
}

return =>
{
"work": "Facebook Page",
"userId": 1,
"id": 1
}
