# Test Cases | API Tests ReqRes

- **Projeto:** API Tests - ReqRes
- **Tipo de teste:** Testes automatizados de API
- **Ferramentas:** Postman, Newman, Node.js
- **Objetivo:** Validar o comportamento da API pública ReqRes garantindo status codes corretos, estrutura JSON válida, autenticação funcional e tempo de resposta dentro do esperado.

---

# Users — Positive

## TC001 — GET List Users

**Objetivo:** Validar que a API retorna corretamente a lista de usuários.

**Endpoint:** `GET /api/users?page=2`

**Passos:**
1. Enviar requisição GET para `/api/users?page=2`.
2. Verificar o status code.
3. Validar a estrutura do JSON retornado.

**Resultado esperado:**
- Status code `200`
- Lista de usuários retornada
- Estrutura JSON válida

---

## TC002 — GET Single User

**Objetivo:** Validar a consulta de um usuário existente.

**Endpoint:** `GET /api/users/2`

**Passos:**
1. Enviar requisição GET para `/api/users/2`.
2. Verificar status code.
3. Validar dados do usuário retornados.

**Resultado esperado:**
- Status code `200`
- Dados do usuário presentes na resposta

---

## TC003 — POST Create User

**Objetivo:** Validar a criação de um usuário.

**Endpoint:** `POST /api/users`

**Payload exemplo:**

```json
{
  "name": "Gio",
  "job": "QA"
}
```

**Passos:**
1. Enviar requisição POST com payload válido.
2. Verificar status code.
3. Validar os campos retornados.

**Resultado esperado:**
- Status code `201`
- ID do usuário criado
- Data de criação retornada

---

## TC004 — PUT Update User

**Objetivo:** Validar atualização de usuário.

**Endpoint:** `PUT /api/users/2`

**Passos:**
1. Enviar requisição PUT com payload válido.
2. Verificar status code.
3. Validar campo `updatedAt`.

**Resultado esperado:**
- Status code `200`
- Dados atualizados retornados

---

## TC005 — DELETE User

**Objetivo:** Validar exclusão de usuário.

**Endpoint:** `DELETE /api/users/2`

**Passos:**
1. Enviar requisição DELETE.
2. Verificar status code.

**Resultado esperado:**
- Status code `204`
- Corpo da resposta vazio

---

# Users — Negative

## TC006 — GET User Not Found

**Objetivo:** Validar comportamento ao buscar usuário inexistente.

**Endpoint:** `GET /api/users/23`

**Passos:**
1. Enviar requisição GET para `/api/users/23`.
2. Verificar status code.

**Resultado esperado:**
- Status code `404`

---

# Authentication — Positive

## TC007 — POST Login Success

**Objetivo:** Validar login com credenciais válidas.

**Endpoint:** `POST /api/login`

**Payload exemplo:**

```json
{
  "email": "eve.holt@reqres.in",
  "password": "cityslicka"
}
```

**Passos:**
1. Enviar requisição POST com credenciais válidas.
2. Verificar status code.
3. Validar token retornado.

**Resultado esperado:**
- Status code `200`
- Token presente na resposta

---

## TC008 — POST Register Success

**Objetivo:** Validar registro de usuário.

**Endpoint:** `POST /api/register`

**Payload exemplo:**

```json
{
  "email": "eve.holt@reqres.in",
  "password": "pistol"
}
```

**Passos:**
1. Enviar requisição POST para `/api/register`.
2. Verificar status code.
3. Validar ID e token retornados.

**Resultado esperado:**
- Status code `200`
- ID e token presentes na resposta

---

# Authentication — Negative

## TC009 — POST Login Missing Password

**Objetivo:** Validar erro quando senha não é enviada.

**Endpoint:** `POST /api/login`

**Payload exemplo:**

```json
{
  "email": "peter@klaven"
}
```

**Passos:**
1. Enviar requisição POST sem senha.
2. Verificar status code.
3. Validar mensagem de erro.

**Resultado esperado:**
- Status code `400`
- Mensagem de erro retornada

---

## TC010 — POST Register Missing Password

**Objetivo:** Validar erro quando senha não é enviada no registro.

**Endpoint:** `POST /api/register`

**Payload exemplo:**

```json
{
  "email": "sydney@fife"
}
```

**Passos:**
1. Enviar requisição POST sem senha.
2. Verificar status code.
3. Validar mensagem de erro.

**Resultado esperado:**
- Status code `400`
- Mensagem de erro retornada

---

# Smoke Tests

Testes rápidos para validar funcionamento básico da API.

## TC011 — Validação básica da API

**Objetivo:** Garantir que endpoints principais respondem corretamente.

**Passos:**
1. Executar a collection via Newman.
2. Validar que todos os testes principais executam sem falha crítica.

**Resultado esperado:**
- Execução concluída com sucesso
- Endpoints principais respondendo corretamente

---

# Critérios de aprovação

Os testes serão considerados aprovados quando:

- Status codes retornarem conforme esperado
- Estrutura JSON estiver correta
- Campos obrigatórios estiverem presentes
- Fluxos de autenticação funcionarem corretamente
- Tempo de resposta estiver dentro do limite definido
