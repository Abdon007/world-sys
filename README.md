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
