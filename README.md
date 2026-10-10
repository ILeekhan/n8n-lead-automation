<div align="center">

# 🤖 Automação de Cadastro de Leads com n8n

*Primeiro trabalho prático de automação — Portfólio de Análise e Desenvolvimento de Sistemas*

![Status](https://img.shields.io/badge/Status-Concluído-brightgreen?style=for-the-badge)
![Tipo](https://img.shields.io/badge/Tipo-Automação%20%7C%20Webhook-blue?style=for-the-badge)
![Automação](https://img.shields.io/badge/n8n-Workflow-EA3323?style=for-the-badge)

---

### 🛠️ Tecnologias e Conceitos Utilizados

![n8n](https://img.shields.io/badge/n8n-EA3323?style=for-the-badge&logo=n8n&logoColor=white)
![Webhook](https://img.shields.io/badge/Webhook-000000?style=for-the-badge&logo=webhooks&logoColor=white)
![JSON](https://img.shields.io/badge/JSON-000000?style=for-the-badge&logo=json&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![HTTP](https://img.shields.io/badge/HTTP%20POST-005571?style=for-the-badge&logo=httpie&logoColor=white)
![CSV](https://img.shields.io/badge/CSV-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)
![PowerShell](https://img.shields.io/badge/PowerShell-5391FE?style=for-the-badge&logo=powershell&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=node.js&logoColor=white)

</div>

---

## 🎯 Objetivo

Criar um **fluxo automático** que recebe, processa e armazena dados de leads de forma estruturada:

| Etapa | Descrição |
| :---: | :--- |
| 📥 **Recebe** | Dados externos via requisição HTTP / Webhook |
| ✅ **Valida** | As informações recebidas |
| ➕ **Complementa** | Adiciona ID único e data/hora do cadastro |
| 📄 **Converte** | Os dados para formato CSV |
| 📤 **Responde** | Retorna uma resposta estruturada em JSON |

---

## 🔄 Fluxo do Workflow

```
Webhook (POST)
      │
      ▼
  Validação dos dados (JavaScript)
      │
      ▼
  Adiciona ID único + timestamp
      │
      ▼
  Converte para CSV
      │
      ▼
  Resposta JSON estruturada ✅
```

---

## 📡 Endpoint

| Método | Endpoint | Content-Type |
| :---: | :--- | :--- |
| `POST` | `http://localhost:5678/webhook/cadastro-lead` | `application/json` |

### 📝 Corpo da requisição (JSON)

```json
{
  "nome": "Seu Nome",
  "email": "seu@email.com"
}
```

---

## ⚙️ Como Testar

Com o **n8n rodando localmente**, execute no PowerShell:

```powershell
Invoke-RestMethod -Uri "http://localhost:5678/webhook/cadastro-lead" `
  -Method POST `
  -ContentType "application/json" `
  -Body '{"nome":"Seu Nome","email":"seu@email.com"}' |
  Format-Table -AutoSize
```

### ✅ Resposta esperada

A API retorna uma resposta **estruturada em JSON** com os dados processados, incluindo o ID único gerado e o timestamp do cadastro.

---

## 🧩 Nós Utilizados no Fluxo

| Nó | Função |
| :--- | :--- |
| 🪝 **Webhook** | Ponto de entrada — recebe a requisição POST externa |
| 🧠 **Code (JavaScript)** | Valida os campos e aplica regras de negócio |
| 🔢 **Set / ID** | Gera ID único e adiciona data/hora do registro |
| 📄 **Spreadsheet / CSV** | Converte os dados para o formato CSV |
| 📤 **Respond to Webhook** | Retorna a resposta JSON ao solicitante |

---

## 💡 Conceitos Aplicados

- 🔗 **Integração entre sistemas** via Webhook
- 🧪 **Validação de entrada** de dados
- 🆔 **Geração de identificador único** (UUID)
- ⏰ **Registro de timestamp** automático
- 🔄 **Transformação de formato** (JSON → CSV)
- 📬 **Padrão request/response** em APIs

---

<div align="center">

Feito com 💙 por **Leekhan**

</div>
