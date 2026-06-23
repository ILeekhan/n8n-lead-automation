\# 🤖 Automação de Cadastro de Leads com n8n



Projeto desenvolvido como primeiro trabalho prático de automação, voltado para portfólio e aplicação de conceitos de Análise e Desenvolvimento de Sistemas.



\---



\## 🎯 Objetivo

Criar um fluxo automático que:

\- Recebe dados externos via requisição HTTP/Webhook

\- Valida as informações recebidas

\- Adiciona dados complementares (ID único e data/hora)

\- Converte os dados para formato CSV

\- Retorna uma resposta estruturada em JSON



\---



\## 🚀 Tecnologias e Conceitos Utilizados

\- \*\*n8n\*\*: Plataforma de automação visual

\- \*\*Webhook\*\*: Ponto de entrada para integração com sistemas externos

\- \*\*JSON\*\*: Formato de troca de dados

\- \*\*JavaScript\*\*: Lógica simples de validação e processamento

\- \*\*HTTP POST\*\*: Método de envio de informações

\- \*\*CSV\*\*: Formato de armazenamento estruturado



\---



\## ⚙️ Como Testar

Com o n8n rodando localmente, execute no PowerShell:



```powershell

Invoke-RestMethod -Uri "http://localhost:5678/webhook/cadastro-lead" -Method POST -ContentType "application/json" -Body '{"nome":"Seu Nome","email":"seu@email.com"}' | Format-Table -AutoSize

