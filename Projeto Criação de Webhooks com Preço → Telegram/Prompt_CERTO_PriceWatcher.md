# Prompt C.E.R.T.O - PriceWatcher Webhook para Alerta Telegram

## 1. PAPEL E OBJETIVO (O P de C.E.R.T.O)

Você é um **Arquiteto de Notificações e Monitoramento** com expertise em **AWS Lambda (Node.js), Amazon EventBridge e Telegram Bot API** e **Alertas e Monitoramento de Dados em Tempo Real**.

Seu objetivo principal é **Criar um gatilho (Webhook) que, ao ser acionado com um valor de preço, envia uma notificação formatada para um canal do Telegram** - **Desenvolver um serviço simples onde o cliente pode enviar um POST com produto e preço, e o script envia uma mensagem formatada de alerta para um grupo/canal do Telegram (via API do Telegram Bot)**.

## 2. CONTEXTO E INFORMAÇÃO (O C de C.E.R.T.O)

### 2.1. Conhecimento Base (Sistema/Aplicação)

```yaml
# PriceWatcher - Webhook para Alerta Telegram - ESPECIFICAÇÕES TÉCNICAS
Sistema: "Webhook Simples para Alertas de Preço"
Status: "Desenvolvimento"
URL: "https://api-gateway-endpoint.amazonaws.com/prod/price-alert"
Performance: "< 1s resposta, 99.9% uptime"

# ARQUITETURA AWS
Frontend:
  - API_Gateway: "REST API simples"
  - CloudWatch: "Logs e monitoramento de alertas"
  - IAM: "Roles mínimas necessárias"

Backend:
  - Lambda: "Node.js 20.x runtime"
  - Secrets_Manager: "Token do Telegram Bot"
  - EventBridge: "Opcional para retry de mensagens"

# FUNCIONALIDADES CORE
Receber_POST:
  - Endpoint: "/price-alert"
  - Método: "POST"
  - Payload: "JSON (produto, preço, moeda)"

Formatar_Mensagem:
  - Formato: "Markdown ou HTML para Telegram"
  - Emojis: "📈📉💰🔔 para visual"
  - Template: "Estrutura padronizada de alerta"

Envio_Telegram:
  - API: "Telegram Bot API sendMessage"
  - Método: "POST /bot{token}/sendMessage"
  - Formato: "Markdown com formatação rica"

Logs_Debug:
  - CloudWatch: "Status de envio detalhado"
  - Métricas: "Sucessos, falhas, latência"
  - Alertas: "Falhas de envio para Telegram"

# DESIGN SYSTEM
Tema: "Mensagens formatadas com emojis"
Cores: "N/A (Backend)"
Animações: "N/A (Backend)"
Responsivo: "N/A (Backend)"
Mode: "Produção com debug configurável"
```

### 2.2. Ambiente e Escopo

```yaml
# STACK TECNOLÓGICO
Frontend:
  - Framework: "API Gateway REST"
  - Linguagem: "JSON Schema"
  - Estilização: "N/A"
  - Componentes: "N/A"

Backend:
  - Runtime: "Node.js 20.x"
  - API: "Webhook Simples (API Gateway)"
  - Auth: "Token do Telegram Bot"
  - Validação: "Joi para validação de payload"

AWS Services:
  - Lambda: "Função de processamento de alertas"
  - API_Gateway: "Endpoint público simples"
  - Secrets_Manager: "Token seguro do Telegram Bot"
  - CloudWatch: "Logs e métricas de performance"

# ESTRUTURA DE PASTAS
pricewatcher/
├── src/                    # Código fonte
│   ├── handlers/          # Handlers da Lambda
│   └── index.js           # Função principal
├── tests/                 # Testes unitários
│   └── test_telegram.js   # Testes do Telegram
└── infrastructure/        # Infraestrutura
    └── template.yaml      # SAM template
```

## 3. TAREFA DETALHADA E EXPECTATIVA (O T de C.E.R.T.O)

Siga estas etapas de raciocínio para executar a tarefa:

### 3.1. Raciocínio (Chain-of-Thought - CoT)

**Pense passo a passo** antes de gerar a resposta final:

1. **Analise a arquitetura AWS** - Identifique Lambda, API Gateway, Secrets Manager e configurações do Telegram Bot API
2. **Mapeie a estrutura Node.js** - Defina estrutura de pastas, handlers, formatação e sistema de alertas
3. **Implemente Receber POST** - Capturar o JSON com informações do produto e preço com validação
4. **Configure Formatar Mensagem** - Criar uma mensagem clara e formatada (Markdown ou HTML) para o Telegram
5. **Desenvolva Envio Telegram** - Usar a API do Telegram Bot para enviar a mensagem formatada
6. **Crie Logs e Debug** - Registrar o status de envio em logs da Lambda (CloudWatch)
7. **Aplique formatação rica** - Emojis, negrito e estrutura visual atrativa
8. **Configure infraestrutura** - SAM template simples e deploy rápido

### 3.2. Ação Principal

**Gere a estrutura completa do projeto PriceWatcher** incluindo:
- Configuração AWS completa (SAM template)
- Código Node.js com axios/fetch
- Função Lambda modular
- Sistema de formatação de mensagens
- Receber POST com validação de produto e preço
- Formatação de Mensagem com emojis e Markdown
- Envio Telegram com tratamento de erros
- Logs e Debug estruturados
- Scripts de deploy e configuração

## 4. REGRAS E RESTRIÇÕES DE SAÍDA (O R de C.E.R.T.O)

O resultado DEVE aderir estritamente às seguintes regras:

1. **Arquitetura:** Use **exatamente** a stack definida: Node.js 20.x, AWS Lambda, API Gateway, Telegram Bot API
2. **Estrutura:** Mantenha a **estrutura de pastas** conforme especificado
3. **Funcionalidades:** Implemente **todas as funcionalidades** listadas no contexto
4. **Design:** Replique o **mensagens formatadas com emojis** e Markdown
5. **Performance:** Garanta **< 1s resposta, 99.9% uptime** e otimizações necessárias
6. **Segurança:** Implemente **Token seguro do Telegram**, validação e sanitização
7. **Código:** Use **Node.js strict**, ESLint, Prettier e padrões enterprise
8. **Deploy:** Inclua **scripts completos** de configuração e deploy automatizado
9. **Documentação:** Forneça **README detalhado** com setup, configuração e troubleshooting
10. **Idioma:** Todo código, comentários e documentação em **Português do Brasil**

## 5. ENTREGA (O E de C.E.R.T.O)

Após a etapa de **Raciocínio**, forneça:

### 5.1. Estrutura Completa do Projeto
- Todos os arquivos e pastas necessários
- Configurações AWS (SAM template)
- package.json com dependências exatas

### 5.2. Código Fonte Completo
- Função Lambda Node.js 20.x
- Handlers de webhook
- Integração Telegram Bot API
- Configurações de build e deploy

### 5.3. Documentação Técnica
- README.md detalhado
- Guia de setup AWS e Telegram Bot
- Instruções de deploy
- Troubleshooting comum

### 5.4. Scripts de Automação
- Deploy automatizado
- Configuração de ambiente
- Backup e restore
- Monitoramento

---

## 📋 CHECKLIST DE VALIDAÇÃO

Antes de entregar, verifique se o sistema possui:

- [ ] ✅ Receber POST com validação de produto e preço
- [ ] ✅ Formatar Mensagem com emojis e Markdown
- [ ] ✅ Envio Telegram com API Bot robusta
- [ ] ✅ Logs e Debug estruturados CloudWatch
- [ ] ✅ Tratamento de erros completo
- [ ] ✅ Lambda configurada
- [ ] ✅ API Gateway simples
- [ ] ✅ Secrets Manager para Token Bot
- [ ] ✅ Mensagens formatadas visualmente
- [ ] ✅ Performance < 1s resposta
- [ ] ✅ Monitoramento de alertas
- [ ] ✅ Deploy automatizado SAM
- [ ] ✅ Documentação completa em português

### **📋 CHECKLIST VERSÃO PREMIUM (Instagram):**
- [ ] ✅ Meta API configurada (Instagram Graph API)
- [ ] ✅ OAuth 2.0 implementado
- [ ] ✅ Chatbot logic com fluxogramas
- [ ] ✅ Agendamento de posts funcional
- [ ] ✅ Dashboard/Planilha integration
- [ ] ✅ DynamoDB para persistência
- [ ] ✅ Webhooks bidirecionais
- [ ] ✅ Documentação premium completa

---

**🎯 OBJETIVO FINAL:** Sistema PriceWatcher 100% funcional, implementando webhook simples para alertas de preço via Telegram, com performance e formatação especificados.

---

## 🚀 **VERSÃO PREMIUM - INSTAGRAM INTEGRATION**

### **Serviços Premium Disponíveis:**

#### **1. 🤖 Chatbot de Vendas para Instagram Direct**
- **Tecnologia:** Python/Node.js + Meta API de Mensagens
- **Funcionalidade:** Lógica completa de chatbot com fluxogramas e tratamento de respostas
- **Valor:** R$ 3.000 a R$ 6.000
- **Diferencial:** Automação completa de vendas via Direct Messages

#### **2. 📅 Agendamento Automático de Posts Instagram**
- **Tecnologia:** Script + Meta API de Mídia + Dashboard/Planilha
- **Funcionalidade:** Agendamento de posts via planilha ou interface web
- **Valor:** Alto - Resolve dor de agências e pequenos empreendedores
- **Diferencial:** Gestão de conteúdo automatizada

### **Como Implementar:**
- Use o **template base do PriceWatcher** como fundação
- Adicione **Meta for Developers API** integration
- Implemente **autenticação OAuth** para Instagram Business
- Configure **webhooks bidirecionais** para interação em tempo real

### **Arquitetura Premium:**
```yaml
Instagram_Premium:
  - Meta_API: "Instagram Basic Display + Instagram Graph API"
  - Auth: "OAuth 2.0 + Long-lived Access Tokens"
  - Webhook: "Bidirecional para mensagens e posts"
  - Database: "DynamoDB para histórico de conversas"
```