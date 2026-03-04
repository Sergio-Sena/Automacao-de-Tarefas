# 🤖 Automação de Tarefas

[![Status](https://img.shields.io/badge/Status-📚%20Templates-blue)]()
[![AWS](https://img.shields.io/badge/AWS-Lambda-orange)](https://aws.amazon.com/lambda/)
[![Python](https://img.shields.io/badge/Python-3.11-blue)](https://python.org/)
[![Node.js](https://img.shields.io/badge/Node.js-20-green)](https://nodejs.org/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

> Templates mestres de microsserviços serverless para automação de integrações.

---

## ✨ Templates Disponíveis

### 🛒 **E-commerce → E-mail Marketing**
Microsserviço que recebe webhooks de e-commerce e integra com plataformas de e-mail marketing.

**Funcionalidades:**
- Recebe webhooks de Shopify, Nuvemshop, WooCommerce
- Valida assinatura HMAC SHA256
- Integra com Mailchimp, ActiveCampaign, ConvertKit
- Verifica duplicatas antes de adicionar
- Retry automático em caso de falha

**Stack:**
- AWS Lambda (Python 3.11)
- API Gateway (Webhook endpoint)
- Secrets Manager (API keys)
- CloudWatch (Logs e métricas)

**Arquivos:**
- `Plano_Mestre.md` - Especificações técnicas completas
- `Prompt_CERTO_NewClientFlow.md` - Prompt para geração do código

---

### 📝 **Formulários → Google Sheets**
Microsserviço que recebe dados de formulários web e registra em Google Sheets.

**Funcionalidades:**
- Endpoint POST com CORS habilitado
- Validação de email RFC 5322
- Sanitização de dados de entrada
- Autenticação via Google Service Account
- Append automático na planilha

**Stack:**
- AWS Lambda (Node.js 20.x)
- API Gateway (REST API)
- Google Sheets API
- Secrets Manager (Credenciais Google)
- CloudWatch (Logs)

**Arquivos:**
- `Plano_Mestre.md` - Especificações técnicas completas
- `Prompt_CERTO_LeadBridge.md` - Prompt para geração do código

---

### 💰 **Webhooks de Preço → Telegram**
Microsserviço que monitora mudanças de preço e envia notificações via Telegram.

**Funcionalidades:**
- Webhook para receber atualizações de preço
- Comparação com preço anterior
- Notificação via Telegram Bot API
- Formatação de mensagens personalizadas
- Histórico de mudanças

**Stack:**
- AWS Lambda (Python 3.11)
- API Gateway (Webhook endpoint)
- DynamoDB (Histórico de preços)
- Telegram Bot API
- CloudWatch (Logs)

**Arquivos:**
- `Plano mestre.md` - Especificações técnicas completas
- `Prompt_CERTO_PriceWatcher.md` - Prompt para geração do código

---

## 🛠️ Tech Stack

### **AWS Services**
- **Lambda** - Execução serverless
- **API Gateway** - Endpoints REST
- **Secrets Manager** - Credenciais seguras
- **CloudWatch** - Logs e monitoramento
- **DynamoDB** - Armazenamento NoSQL (quando necessário)

### **Runtimes**
- **Python 3.11** - E-commerce, Webhooks
- **Node.js 20.x** - Formulários, Integrações web

### **Integrações**
- **E-commerce**: Shopify, Nuvemshop, WooCommerce
- **Marketing**: Mailchimp, ActiveCampaign, ConvertKit
- **Produtividade**: Google Sheets
- **Mensageria**: Telegram Bot API

---

## 🚀 Como Usar

### **1. Escolha o Template**
Navegue até a pasta do template desejado:
- `E-commerce → E-mail Marketing/`
- `Formulários → Google Sheets/`
- `Projeto Criação de Webhooks com Preço → Telegram/`

### **2. Leia o Plano Mestre**
Cada template possui um `Plano_Mestre.md` com:
- Especificações técnicas completas
- Arquitetura AWS detalhada
- Stack tecnológico
- Funcionalidades core
- Regras e restrições

### **3. Use o Prompt**
Cada template possui um `Prompt_CERTO_*.md` otimizado para:
- Amazon Q Developer
- ChatGPT
- Claude
- Outros LLMs

### **4. Gere o Código**
Cole o prompt no LLM de sua escolha para gerar:
- `template.yaml` (AWS SAM)
- Código da função Lambda
- `README.md` com instruções de deploy
- Exemplos de payload

### **5. Deploy**
```bash
sam build
sam deploy --guided
```

---

## 📁 Estrutura do Projeto

```
Automacao-de-Tarefas/
├── E-commerce → E-mail Marketing/
│   ├── Plano_Mestre.md
│   └── Prompt_CERTO_NewClientFlow.md
├── Formulários → Google Sheets/
│   ├── Plano_Mestre.md
│   └── Prompt_CERTO_LeadBridge.md
├── Projeto Criação de Webhooks com Preço → Telegram/
│   ├── Plano mestre.md
│   └── Prompt_CERTO_PriceWatcher.md
├── scripts/
│   └── utils/
└── docs/
    └── DEPLOY_PASSO_A_PASSO.md
```

---

## 🎯 Casos de Uso

### **E-commerce → Marketing**
- Loja online adiciona cliente automaticamente à lista de email
- Nutrição de leads pós-compra
- Segmentação automática por produto comprado

### **Formulários → Sheets**
- Formulário de contato → Planilha de leads
- Cadastro de newsletter → Planilha de assinantes
- Pesquisa de satisfação → Planilha de feedback

### **Preço → Telegram**
- Monitoramento de concorrência
- Alertas de promoção
- Notificações de mudança de preço

---

## 🔒 Segurança

### **Boas Práticas Implementadas**
- ✅ Credenciais via AWS Secrets Manager
- ✅ Validação HMAC para webhooks
- ✅ Sanitização de dados de entrada
- ✅ CORS configurado corretamente
- ✅ Logs estruturados no CloudWatch
- ✅ Retry automático em falhas

---

## 📊 Performance

- **Latência**: < 3s por execução
- **Retry**: Automático em caso de falha
- **Escalabilidade**: Serverless (auto-scaling)
- **Custo**: Pay-per-use (AWS Lambda)

---

## 🗺️ Roadmap

- [ ] Template: CRM → WhatsApp Business
- [ ] Template: Pagamento → Nota Fiscal
- [ ] Template: Estoque → Notificação
- [ ] Template: Agenda → Google Calendar
- [ ] Dashboard de monitoramento
- [ ] Testes automatizados

---

## 🤝 Contribuição

1. Fork o projeto
2. Crie uma branch (`git checkout -b feature/novo-template`)
3. Commit suas mudanças (`git commit -m 'feat: novo template'`)
4. Push para a branch (`git push origin feature/novo-template`)
5. Abra um Pull Request

---

## 📄 Licença

MIT License - veja [LICENSE](LICENSE) para detalhes.

---

## 👨💻 Autor

**Sergio Sena**
- GitHub: [@Sergio-Sena](https://github.com/Sergio-Sena)
- LinkedIn: [Sergio Sena](https://linkedin.com/in/sergio-sena)
- Portfolio: [dev-cloud.sstechnologies-cloud.com](https://dev-cloud.sstechnologies-cloud.com)

---

<div align="center">

**⭐ Se este projeto foi útil, deixe uma estrela!**

[🐛 Issues](../../issues) • [📖 Docs](docs/)

</div>
