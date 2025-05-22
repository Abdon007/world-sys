
# World System API

A **World System API** fornece acesso a dados geográficos e linguísticos baseados no banco de dados `world` do MySQL.  
É possível consultar, cadastrar, atualizar e excluir informações de países, cidades e idiomas.

---

## 🔐 Autenticação

Esta API utiliza o mecanismo de **Client ID Enforcement** para autenticação.  
Cada requisição deve conter os headers `client_id` e `client_secret`, fornecidos no momento do registro da aplicação no API Manager.

### Exemplo de headers:
```http
client_id: seu-client-id
client_secret: seu-client-secret
Content-Type: application/json
```

---

## 📦 Formato das Respostas

Todas as respostas são no formato `application/json`.

### Exemplo de erro:
```json
{
  "error": "Recurso não encontrado",
  "code": 404
}
```

---

## 📃 Padrões de Paginação

Você pode usar os parâmetros `limit` e `offset` para controlar o volume de dados retornados nos endpoints de listagem.

### Exemplo:
```http
GET /countries?limit=10&offset=20
```

---

## 🔧 Como testar a API

Você pode testar os endpoints com **Postman**, **Insomnia** ou pelo **API Console da Anypoint Platform**.

### Exemplo de GET:
```http
GET https://api.evermind.com/world-sys/v1/countries?limit=10&offset=0
```

### Exemplo de POST:
```http
POST /cities
Content-Type: application/json

{
  "name": "São Paulo",
  "countryCode": "BRA",
  "district": "São Paulo",
  "population": 12300000
}
```

---

## ✅ Boas Práticas

- Use **paginação** para evitar sobrecarga nos resultados.
- Envie sempre os **headers obrigatórios**.
- Trate corretamente os **códigos de resposta**:
  - `200` – Sucesso
  - `201` – Criado
  - `400` – Requisição inválida
  - `404` – Recurso não encontrado
  - `500` – Erro no servidor
- Utilize os **métodos HTTP corretos**:
  - `GET` para buscar dados
  - `POST` para criar novos dados
  - `PUT` para atualizações
  - `DELETE` para exclusão

---

## 📌 Recursos Disponíveis

- `/countries` – Gerenciamento de países
- `/cities` – Gerenciamento de cidades
- `/languages` – Gerenciamento de idiomas por país

---

## 🧑‍💻 Suporte

Para dúvidas, melhorias ou bugs, entre em contato com a equipe responsável por essa API.
