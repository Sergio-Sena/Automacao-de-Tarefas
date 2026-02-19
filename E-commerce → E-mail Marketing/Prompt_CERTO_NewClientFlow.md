# Prompt C.E.R.T.O - NewClientFlow E-commerce para Mailchimp

## 1. PAPEL E OBJETIVO (O P de C.E.R.T.O)

Você é um **Engenheiro de Integração de Sistemas de Vendas** com expertise em **AWS Lambda (Python), Nuvemshop/Tiny Webhook API e Mailchimp/ActiveCampaign API** e **Fluxos de Vendas e Marketing Digital**.

Seu objetivo principal é **Criar uma função para receber notificações de novo pedido e adicionar o cliente à lista de e-mail marketing** - **Desenvolver um endpoint seguro (Webhook) que seja acionado a cada novo pedido (ou cadastro) na plataforma de e-commerce e envie o nome e e-mail do cliente para a API do serviço de e-mail marketing**.

## 2. CONTEXTO E INFORMAÇÃO (O C de C.E.R.T.O)

### 2.1. Conhecimento Base (Sistema/Aplicação)

```yaml
# NewClientFlow - E-commerce para Mailchimp - ESPECIFICAÇÕES TÉCNICAS
Sistema: "Webhook Receiver para Integração E-commerce"
Status: "Desenvolvimento"
URL: "https://api-gateway-endpoint.amazonaws.com/prod/webhook"
Performance: "< 3s resposta, 99.9% uptime"

# ARQUITETURA AWS
Frontend:
  - API_Gateway: "REST API com autenticação por chave"
  - CloudWatch: "Logs e monitoramento"
  - IAM: "Roles e políticas de segurança"

Backend:
  - Lambda: "Python 3.11 runtime"
  - Secrets_Manager: "Armazenamento seguro de API keys"
  - EventBridge: "Opcional para retry de falhas"

# FUNCIONALIDADES CORE
Receber_Webhook:
  - Endpoint: "/webhook"
  - Método: "POST"
  - Validação: "Assinatura HMAC SHA256"

Validação_Segurança:
  - Verificação: "Assinatura secreta do webhook"
  - Headers: "X-Signature ou similar"
  - Timeout: "30 segundos máximo"

Integração_Marketing:
  - API: "Mailchimp ou ActiveCampaign"
  - Método: "POST /lists/{list_id}/members"
  - Duplicatas: "Verificação antes de adicionar"

Filtragem_Dados:
  - Validação: "Email válido e nome presente"
  - Deduplicação: "Verificar se já existe na lista"
  - Sanitização: "Limpeza de dados de entrada"

# DESIGN SYSTEM
Tema: "Logs estruturados JSON"
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
  - Runtime: "Python 3.11"
  - API: "Webhook Receiver (usando API Gateway)"
  - Auth: "HMAC SHA256 signature validation"
  - Validação: "Pydantic ou jsonschema"

AWS Services:
  - Lambda: "Função principal de processamento"
  - API_Gateway: "Endpoint público para webhooks"
  - Secrets_Manager: "Armazenamento de API keys"
  - CloudWatch: "Logs e métricas"

# ESTRUTURA DE PASTAS
newclientflow/
├── src/                      # Código fonte
│   ├── handlers/            # Handlers da Lambda
│   └── lambda_function.py   # Função principal
├── tests/                   # Testes unitários
│   └── test_webhook.py      # Testes do webhook
└── infrastructure/          # Infraestrutura
    └── template.yaml        # SAM template
```

## 3. TAREFA DETALHADA E EXPECTATIVA (O T de C.E.R.T.O)

Siga estas etapas de raciocínio para executar a tarefa:

### 3.1. Raciocínio (Chain-of-Thought - CoT)

**Pense passo a passo** antes de gerar a resposta final:

1. **Analise a arquitetura AWS** - Identifique Lambda, API Gateway, Secrets Manager e configurações de segurança necessárias
2. **Mapeie a estrutura Python** - Defina estrutura de pastas, handlers, validações e sistema de processamento de webhooks
3. **Implemente Receber Webhook** - Configurar Lambda para receber e validar o JSON do webhook do E-commerce (ex: order/create)
4. **Configure Validação de Assinatura** - Incluir lógica para verificar a assinatura secreta do Webhook (segurança essencial)
5. **Desenvolva Integração de Marketing** - Usar requests para enviar dados (nome e email) para Mailchimp/ActiveCampaign
6. **Crie Filtragem de Dados** - Garantir que o cliente não seja adicionado se já estiver na lista
7. **Aplique logs estruturados** - CloudWatch logs com JSON estruturado e monitoramento
8. **Configure infraestrutura** - SAM template e deploy automatizado

### 3.2. Ação Principal

**Gere a estrutura completa do projeto NewClientFlow** incluindo:
- Configuração AWS completa (SAM template)
- Código Python com requests
- Função Lambda modular
- Sistema de validação de webhooks
- Receber Webhook com validação de assinatura HMAC
- Integração Mailchimp/ActiveCampaign com verificação de duplicatas
- Filtragem de dados com sanitização
- Logs estruturados JSON
- Scripts de deploy e configuração

## 4. REGRAS E RESTRIÇÕES DE SAÍDA (O R de C.E.R.T.O)

O resultado DEVE aderir estritamente às seguintes regras:

1. **Arquitetura:** Use **exatamente** a stack definida: Python 3.11, AWS Lambda, API Gateway, Secrets Manager
2. **Estrutura:** Mantenha a **estrutura de pastas** conforme especificado
3. **Funcionalidades:** Implemente **todas as funcionalidades** listadas no contexto
4. **Design:** Replique o **logs estruturados JSON** com CloudWatch integration
5. **Performance:** Garanta **< 3s resposta, 99.9% uptime** e otimizações necessárias
6. **Segurança:** Implemente **validação HMAC SHA256**, validação e sanitização
7. **Código:** Use **Python strict**, pylint, black e padrões enterprise
8. **Deploy:** Inclua **scripts completos** de configuração e deploy automatizado
9. **Documentação:** Forneça **README detalhado** com setup, configuração e troubleshooting
10. **Idioma:** Todo código, comentários e documentação em **Português do Brasil**

## 5. ENTREGA (O E de C.E.R.T.O)

Após a etapa de **Raciocínio**, forneça:

### 5.1. Estrutura Completa do Projeto
- Todos os arquivos e pastas necessários
- Configurações AWS (SAM template)
- requirements.txt com dependências exatas

### 5.2. Código Fonte Completo
- Função Lambda Python 3.11
- Handlers de webhook
- Integrações Mailchimp/ActiveCampaign
- Configurações de build e deploy

### 5.3. Documentação Técnica
- README.md detalhado
- Guia de setup AWS
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

- [ ] ✅ Receber Webhook com validação de assinatura HMAC
- [ ] ✅ Validação de Segurança robusta
- [ ] ✅ Integração de Marketing com verificação de duplicatas
- [ ] ✅ Filtragem de Dados com sanitização
- [ ] ✅ Tratamento de erros completo
- [ ] ✅ Lambda configurada
- [ ] ✅ API Gateway e endpoint público
- [ ] ✅ Secrets Manager para API keys
- [ ] ✅ Logs estruturados JSON
- [ ] ✅ Performance < 3s resposta
- [ ] ✅ Monitoramento CloudWatch
- [ ] ✅ Deploy automatizado SAM
- [ ] ✅ Documentação completa em português

---

**🎯 OBJETIVO FINAL:** Sistema NewClientFlow 100% funcional, implementando webhook seguro para integração E-commerce com E-mail Marketing, com performance e segurança especificados.