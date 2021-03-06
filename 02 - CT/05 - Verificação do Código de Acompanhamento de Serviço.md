---
title: Verificação do Código de Acompanhamento de Serviço
method: GET
url: "{{API_URL}}/api/{servico-x}/{hash}"
---


Quando o cartório recebe o código de solicitação do serviço, o cartório se autentica e valida a veracidade da autorização através de um Endpoint junto ao CT. 

* O campo "updates" são as atualizações que o cartório manda,sobre o status do andamento do serviço.
Aqui o "updates" retorna vazio,porém nas próximas requisições o cartório atualiza essa mensagem e então é possivel consultar um novo status do serviço.


```request:cURL
curl --location --request GET "{{API_URL}}/api/servico-25o0/tGS7SjsQEH" \
  --header "Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJodHRwOlwvXC8xMjcuMC4wLjE6ODAwMFwvYXBpXC9hdXRlbnRpY2FjYW8iLCJpYXQiOjE1OTEzNzMxNzcsImV4cCI6MTU5MTM3Njc3NywibmJmIjoxNTkxMzczMTc3LCJqdGkiOiJQVVQ5enJ4TFpKS29zNW9ZIiwic3ViIjoiNjgyNjI5YWEtZWM1OS00NTg0LWI3NDgtZjQzNWFmOGQzZjE4IiwicHJ2IjoiYzAxMGM4OGUxMWY0MWM0Njc5YTNmMzVlMmQwYWQ3YTVlOWFiOWNkMCJ9.Uc9XiaPDeWW5riFZFUBuqJoGuyCV6UZNoHr81ZGiU9k"
```


```response:200
{
    "token_service": {
        "id": "96cc69f0-e2ad-40c4-83b0-9a824a8f4cb4",
        "token": "5QRgsxc8PG",
        "updates": [],
        "company": {
            "id": "c155d909-b74c-4c3a-92c8-5a6f7057407d",
            "title": "RAZÃO SOCIAL S.A.",
            "cnpj": "12.345.678/0000-01",
            "tel": "(11) 1111-1111",
            "cel": "(22) 22222-2222",
            "email": "empresa1@teste.com",
            "status": "APROVADO",
            "operator": 1,
            "waiting": 0
        },
        "office": {
            "id": "13c130ac-9f9c-4d18-98cf-a6b46b572e93",
            "cns": "123456",
            "cnpj": null,
            "title": "1º CARTÓRIO DE TESTE",
            "email": "cartorio1@teste.com.br",
            "iugu_account_id": null,
            "status": "APROVADO",
            "waiting": 0
        },
        "service": {
            "id": "20c5fdcb-35d4-4a7e-8fed-65da4e7a801d",
            "type": "NOTARIAL_REGISTRAL",
            "title": "Serviço SWMr",
            "slug": "servico-swmr",
            "description": null,
            "amount": "3.00",
            "amount_funcivil": "1.00",
            "amount_funjuris": "1.00",
            "amount_fse": "2.00"
        }
    }
}
```


```response:401
{
  "mensagem": "Token Inválido"
}

```


```response:404
{
  "mensagem": "Serviço não existe"
}

```


```response:404
{
  "mensagem": "Informe um token de serviço válido"
}

```
