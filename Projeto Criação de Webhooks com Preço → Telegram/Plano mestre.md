Roteiro para o Amazon Q: Template Mestre de Alerta (Telegram)
O foco deste roteiro é gerar um microsserviço que recebe dados via Webhook e os envia ao Telegram.

1. PAPEL E OBJETIVO
   Placeholder Valor
   [ESPECIALISTA_DEFINIR] Desenvolvedor de Automações Serverless e Cloud AWS
   [TECNOLOGIAS_DEFINIR] AWS Lambda, Node.js, API Gateway, Amazon SAM (Serverless Application Model), Telegram Bot API
   [DOMINIO_DEFINIR] Integração de Dados, Alertas Críticos e Monitoramento
   [OBJETIVO_PRINCIPAL_DEFINIR] Gerar o Template Mestre de Microsserviço que recebe JSON e envia notificação formatada para o Telegram.
   [DESCRICAO_DETALHADA_OBJETIVO] Criar código e infraestrutura que permite a replicação rápida para clientes de Alerta de Preço, Estoque ou Novo Lead.

2. CONTEXTO E INFORMAÇÃO
O Amazon Q precisa de uma definição clara de como o projeto será.

```yaml
# PriceWatcher - ESPECIFICAÇÕES TÉCNICAS

Sistema: "Microsserviço de Webhook e Notificação"
Status: "Novo Projeto - Template Mestre"
Performance: "Latência máxima de 200ms na execução da Lambda."

# ARQUITETURA AWS

Backend:
  - AWS Lambda: "Função única para processamento do Webhook."
  - AWS API Gateway: "Endpoint POST configurado para acionar a Lambda."

# FUNCIONALIDADES CORE

Receber Webhook:
  - Atributo: "Método POST"
  - Corpo: "JSON genérico contendo 'title', 'value', 'link'"
Formatar Mensagem Telegram:
  - Atributo: "Usar sintaxe Markdown ou HTML"
  - Atributo: "Inclusão de emojis relevantes (ex: ⚠️, ✅)"
Envio Telegram:
  - Atributo: "Requisição HTTPS para api.telegram.org"
  - Atributo: "Uso de variáveis de ambiente para o BOT_TOKEN e CHAT_ID"
```

```yaml
# STACK TECNOLÓGICO

Backend:
  - Runtime: "Node.js 20.x"
  - API: "API REST (API Gateway)"
  - Auth: "Chave API (simples, via 'x-api-key' no API Gateway)"
  - Validação: "Validação básica de presença dos campos 'title' e 'value' no corpo da requisição."

AWS Services:
  - AWS Lambda: "Código de integração e lógica."
  - AWS API Gateway: "Exposição do Webhook (Endpoint)."
  - Amazon CloudWatch: "Logs de execução e erro."
```

3. TAREFA DETALHADA E EXPECTATIVA
Siga estas etapas de raciocínio para executar a tarefa:

3.1. Raciocínio (Chain-of-Thought - CoT)
Defina o Contrato de Dados (Payload) - Garanta que a função Lambda esteja pronta para receber o JSON genérico.

Mapeie a Infraestrutura (IaC) - Gere o arquivo SAM (template.yaml) completo para criar a Lambda, a política de permissão básica e o API Gateway com o endpoint /webhook-telegram.

Implemente a Lógica de Notificação - Desenvolva o código Node.js para extrair os dados, formatar a mensagem em Markdown e fazer a chamada axios (ou fetch) para a API do Telegram.

Configure Segurança Básica - Inclua a lógica de checagem das variáveis de ambiente (BOT_TOKEN e CHAT_ID) e a validação básica do payload de entrada.

Crie o README para o Cliente - Descreva claramente como o cliente deve configurar o Bot no Telegram para extrair o BOT_TOKEN e o CHAT_ID.

3.2. Ação Principal
Gere o template de projeto completo "PriceWatcher-Telegram" incluindo:

Configuração AWS SAM (template.yaml) completa.

Código Node.js da função Lambda.

Um Exemplo de Payload de entrada (JSON) para teste.

Documentação README.md com instruções de deploy e uso.

4. REGRAS E RESTRIÇÕES DE SAÍDA
O resultado DEVE aderir estritamente às seguintes regras:

Arquitetura: Use exatamente a stack definida: AWS Lambda, API Gateway, Node.js.

Configuração: O token do Telegram e o ID do chat DEVEM ser configurados via Variáveis de Ambiente da Lambda.

Código: O código Node.js deve ser conciso e limpo, utilizando async/await.

Entrega: Forneça a saída em formato de blocos de código nomeados (ex: template.yaml, index.js, README.md).

Idioma: Todo código, comentários e documentação em Português do Brasil.

---

## 🚀 VERSÃO PREMIUM - INSTAGRAM INTEGRATION

### Serviços Premium Disponíveis:

#### 1. 🤖 Chatbot de Vendas para Instagram Direct
```yaml
Chatbot_Instagram:
  - API: "Meta Instagram Messaging API"
  - Linguagem: "Python 3.11 ou Node.js 20.x"
  - Funcionalidades:
    - Fluxogramas de conversa automatizados
    - Tratamento de respostas inteligente
    - Integração com CRM/E-commerce
    - Métricas de conversão
  - Valor: "R$ 3.000 a R$ 6.000"
  - Complexidade: "Alta - Requer OAuth e Business Account"
```

#### 2. 📅 Agendamento Automático de Posts
```yaml
Post_Scheduler:
  - API: "Meta Instagram Graph API"
  - Interface: "Dashboard Web ou Google Sheets"
  - Funcionalidades:
    - Upload e agendamento via planilha
    - Preview de posts antes da publicação
    - Métricas de engajamento
    - Gestão de múltiplas contas
  - Valor: "Alto - Resolve dor de agências"
  - Target: "Agências e pequenos empreendedores"
```

### Arquitetura Premium Expandida:
```yaml
# STACK PREMIUM INSTAGRAM

Backend_Premium:
  - Runtime: "Python 3.11 (para IA) ou Node.js 20.x"
  - APIs: "Meta Graph API + Instagram Basic Display"
  - Auth: "OAuth 2.0 + Long-lived Access Tokens"
  - Database: "DynamoDB para conversas e agendamentos"

AWS_Services_Premium:
  - Lambda: "Múltiplas funções especializadas"
  - DynamoDB: "Persistência de dados"
  - EventBridge: "Agendamento de posts"
  - S3: "Armazenamento de mídia"
  - Secrets Manager: "Tokens OAuth seguros"
```

### Implementação Premium:
1. **Base do PriceWatcher** como fundação
2. **Meta for Developers** setup completo
3. **Business Account** Instagram obrigatório
4. **Webhooks bidirecionais** para interação real-time
5. **Dashboard personalizado** para gestão

### Diferencial de Preço:
- **MVP (Telegram):** R$ 500 - R$ 1.500 (entrega em 3 dias)
- **Premium (Instagram):** R$ 3.000 - R$ 6.000 (entrega em 2-3 semanas)
- **Complexidade:** 10x maior devido às políticas da Meta

### Diferencial do Template Mestre:
Este projeto serve como **template replicável** para diferentes tipos de alertas:
- Alerta de Preço
- Alerta de Estoque  
- Novo Lead
- Outros tipos de notificações críticas
- **PREMIUM:** Chatbot Instagram + Agendamento de Posts