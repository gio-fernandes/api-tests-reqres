# Bug Report -- ReqRes API

Este documento apresenta um **exemplo de registro de defeito**
identificado durante a execução dos testes da API.

![Bug Report](https://img.shields.io/badge/QA-Bug%20Report-red) ![API
Testing](https://img.shields.io/badge/API-Testing-green)
![Postman](https://img.shields.io/badge/Postman-API%20Testing-FF6C37?logo=postman&logoColor=white)

------------------------------------------------------------------------

---


## Bug ID

BUG-001

------------------------------------------------------------------------

## Título

Tempo de resposta acima do esperado no endpoint de login

------------------------------------------------------------------------

## Descrição

Durante a execução dos testes automatizados foi observado que o endpoint
de login apresentou tempo de resposta superior ao limite definido nos
testes automatizados.

------------------------------------------------------------------------

## Passos para reproduzir

1.  Enviar requisição **POST** para o endpoint:

```{=html}
<!-- -->
```
    /login

2.  Utilizar as seguintes credenciais:

``` json
{
  "email": "eve.holt@reqres.in",
  "password": "cityslicka"
}
```

3.  Executar o teste utilizando **Postman ou Newman**

------------------------------------------------------------------------

## Resultado esperado

-   Status Code **200**
-   Tempo de resposta **menor que 1000ms**
-   Token retornado no corpo da resposta

------------------------------------------------------------------------

## Resultado atual

-   Status Code **200**
-   Tempo de resposta **acima do limite definido**

------------------------------------------------------------------------

## Severidade

Média

------------------------------------------------------------------------

## Prioridade

Média

------------------------------------------------------------------------

## Ambiente

-   API: ReqRes
-   Ferramenta de teste: Postman / Newman
-   Sistema operacional: Windows
-   Node.js: Ambiente utilizado para execução do Newman

------------------------------------------------------------------------

## Evidência

O comportamento foi identificado durante a execução automatizada dos
testes via Newman.
