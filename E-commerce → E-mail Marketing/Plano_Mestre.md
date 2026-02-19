Roteiro para o Amazon Q: Template Mestre de Integração E-commerce (E-mail Marketing)
O foco deste roteiro é gerar um microsserviço que recebe webhooks de e-commerce e integra com plataformas de e-mail marketing.

1. PAPEL E OBJETIVO
   Placeholder Valor
   [ESPECIALISTA_DEFINIR] Desenvolvedor de Integrações Serverless e APIs de Vendas
   [TECNOLOGIAS_DEFINIR] AWS Lambda, Python 3.11, API Gateway, Amazon SAM, Mailchimp/ActiveCampaign API
   [DOMINIO_DEFINIR] Automação de Vendas, Nutrição de Leads e Marketing Digital
   [OBJETIVO_PRINCIPAL_DEFINIR] Gerar o Template Mestre de Microsserviço que recebe webhooks de e-commerce e adiciona clientes ao e-mail marketing.
   [DESCRICAO_DETALHADA_OBJETIVO] Criar código e infraestrutura que permite a replicação rápida para clientes de diferentes plataformas de e-commerce (Nuvemshop, Shopify, WooCommerce).

2. CONTEXTO E INFORMAÇÃO
O Amazon Q precisa de uma definição clara de como o projeto será.

```yaml
# NewClientFlow - ESPECIFICAÇÕES TÉCNICAS

Sistema: "Microsserviço de Webhook E-commerce e Integração Marketing"
Status: "Novo Projeto - Template Mestre"
Performance: "Latência máxima de 3s na execução da Lambda com retry automático."

# ARQUITETURA AWS

Backend:
  - AWS Lambda: "Função única para processamento do Webhook e integração."
  - AWS API Gateway: "Endpoint POST configurado para receber webhooks."
  - AWS Secrets Manager: "Armazenamento seguro de API keys das plataformas."

# FUNCIONALIDADES CORE

Receber Webhook E-commerce:
  - Atributo: "Método POST com validação HMAC SHA256"
  - Corpo: "JSON genérico contendo 'customer', 'order', 'event_type'"
  
Validar Assinatura:
  - Atributo: "Verificação de assinatura secreta do webhook"
  - Atributo: "Suporte para diferentes formatos (Shopify, Nuvemshop, WooCommerce)"
  
Integrar E-mail Marketing:
  - Atributo: "Requisição HTTPS para APIs de marketing"
  - Atributo: "Verificação de duplicatas antes de adicionar"
  - Atributo: "Uso de variáveis de ambiente para API_KEY e LIST_ID"
```

```yaml
# STACK TECNOLÓGICO

Backend:
  - Runtime: "Python 3.11"
  - API: "Webhook Receiver (API Gateway)"
  - Auth: "HMAC SHA256 signature validation"
  - Validação: "Pydantic para validação de payload e email"

AWS Services:
  - AWS Lambda: "Código de integração e lógica de negócio."
  - AWS API Gateway: "Exposição do Webhook (Endpoint)."
  - AWS Secrets Manager: "API keys das plataformas de marketing."
  - Amazon CloudWatch: "Logs de execução, erro e métricas de conversão."
```

3. TAREFA DETALHADA E EXPECTATIVA
Siga estas etapas de raciocínio para executar a tarefa:

3.1. Raciocínio (Chain-of-Thought - CoT)
Defina o Contrato de Dados (Payload) - Garanta que a função Lambda esteja pronta para receber diferentes formatos de webhook de e-commerce.

Mapeie a Infraestrutura (IaC) - Gere o arquivo SAM (template.yaml) completo para criar a Lambda, Secrets Manager e o API Gateway com o endpoint /ecommerce-webhook.

Implemente a Lógica de Validação - Desenvolva o código Python para validar assinaturas HMAC de diferentes plataformas e extrair dados do cliente.

Configure Integração Marketing - Inclua a lógica para conectar com Mailchimp/ActiveCampaign, verificar duplicatas e adicionar à lista.

Crie o README para o Cliente - Descreva claramente como configurar webhooks nas plataformas de e-commerce e obter as API keys necessárias.

3.2. Ação Principal
Gere o template de projeto completo "NewClientFlow-Marketing" incluindo:

Configuração AWS SAM (template.yaml) completa.

Código Python da função Lambda com requests e validação.

Exemplos de Payload de diferentes plataformas (Shopify, Nuvemshop, WooCommerce).

Documentação README.md com instruções de deploy e configuração.

4. REGRAS E RESTRIÇÕES DE SAÍDA
O resultado DEVE aderir estritamente às seguintes regras:

Arquitetura: Use exatamente a stack definida: AWS Lambda, API Gateway, Python 3.11, Secrets Manager.

Configuração: As API keys das plataformas de marketing DEVEM ser configuradas via AWS Secrets Manager.

Código: O código Python deve ser conciso e limpo, utilizando async/await quando necessário.

Segurança: Implementar validação HMAC obrigatória para todos os webhooks recebidos.

Entrega: Forneça a saída em formato de blocos de código nomeados (ex: template.yaml, lambda_function.py, README.md).

Idioma: Todo código, comentários e documentação em Português do Brasil.

### Diferencial do Template Mestre:
Este projeto serve como **template replicável** para diferentes tipos de integrações e-commerce:
- Nuvemshop → Mailchimp
- Shopify → ActiveCampaign  
- WooCommerce → ConvertKit
- Outras plataformas de e-commerce e marketing