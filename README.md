# Go Desafio S3wf

Um simples teste para nossos integrantes da s3wf que irão trabalhar com GO.


Iremos criar uma API SERVER para ser consumida por um APP.

A api terá que ser feita usando stdlib padrão de Go.

Algumas libs para tratar cors, session, rate limit, e JWT, banco de dados são todas permitidas permitidas menos frameworks full, mas libs sim.

O banco de dados a ser utilizado é o POSTGRESQL.

## Endpoints que iremos desenvolver

| Endpoint              | Method |
|-----------------------|:------:|
| /ping                 |  POST  |
| /auth                 |  POST  |
| /user                 |  POST  |
| /user                 |  PUT   |
| /user                 | DELETE |
| /user/{:uuid}         |  GET   |


## Ping
O Ping é público, não terá controle somente para saber se nosso server está online.

## Auth

Este endpoint irá possuir um header com Authorization e irá enviar via JSON login e senha em um method [POST].
Ele irá retornar um JSON quando der erro e um JSON com for sucesso.

**HTTP/2 200**
```json
{  
   "status":"success",
   "message":"Usuario encontrado  e token gerado",
  "tokenjwt":"eyJhbGciOiJSUzI1NiIWTC17vpzeYR0I14qkna_hbMZWbOPqTaWwDsn_Ace6QEInv7dTBaz48_eom9qWcX18NGmhTvpiHekqNYMt-RkOM8Hjc5DYNJuqyEy3gvy_IMjcu2w-hl2yHilvPNP_UK0oc1ebF2pUxaKdsD5oS5fV-TYlfH_k",
   "expires":"2019-07-20",
   "tokenmsg":"use o token para acessar os endpoints!",
   "Login":{ 
      "id":4287,
      "uuiduser":"301cd1b2d60d5bd5f143c352dfdc0a4dd44517f0",
      "avatarurl":"http://mydomain.com/user/user.jpg",
      "avatartype":"image/jpeg",
      "name":"Junior S3WF",
      "datastart":"2018-11-05"
   }
}
```

**HTTP/2 500**
```json
{  
   "status":"error",
   "message":"Usuário não pode ser autenticado!"
}
```

## User

Este endpoint irá somente trazer informaçes do usurio como uuid, nome, cpf, email e sobrenome no formato JSON.
Ele irá enviar um method [GET] passando no header o token e na url o uuid do usurio e irá receber um JSON.


O que é importante neste teste:

 - Organização do código
 
 - Utilizar boas práticas
 
 - Deixar sempre a regra de negócio o mais desacoplada possível
 
 - O JWT no é obrigatório, basta simular caso no consigam
 
 - Uma lib para rotas como belt ou gorillamux é aceitável
 
 - Criar os mocks de teste
 
 - Criar o banco de dados e tabelas fazer dump e colocar no projeto para que possamos validar e testar
 
## boa sorte...




