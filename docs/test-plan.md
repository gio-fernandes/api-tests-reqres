# Test Plan – ReqRes API Tests

O objetivo deste plano de testes é validar o comportamento da API pública ReqRes, garantindo que os endpoints respondam corretamente de acordo com as especificações esperadas.

Os testes verificam status code, estrutura da resposta, presença de campos obrigatórios e tempo de resposta.

---

![Postman](https://img.shields.io/badge/Postman-API%20Testing-FF6C37?logo=postman&logoColor=white)
![Newman](https://img.shields.io/badge/Newman-Test%20Runner-0A0A0A?logo=postman&logoColor=white)
![Newman Reporter](https://img.shields.io/badge/Newman-HTML%20Reporter-orange)
![Node.js](https://img.shields.io/badge/Node.js-Runtime-339933?logo=node.js&logoColor=white)

---


## Escopo:

Endpoints testados:

### Users
- GET /users
- GET /users/{id}
- POST /users
- PUT /users/{id}
- DELETE /users/{id}

### Authentication
- POST /login
- POST /register

---


## Tipos de teste

Serão realizados os seguintes tipos de teste:

- Testes funcionais
- Testes de API
- Testes positivos
- Testes negativos
- Smoke tests

---


## Critérios de sucesso

Um teste será considerado aprovado quando:

- o status code esperado for retornado
- o JSON de resposta estiver correto
- os campos obrigatórios estiverem presentes
- o tempo de resposta estiver dentro do limite esperado