Roteiro para o Amazon Q: Template Mestre de Integração Formulários (Google Sheets)
O foco deste roteiro é gerar um microsserviço que recebe dados de formulários web e os registra automaticamente em planilhas Google Sheets.

1. PAPEL E OBJETIVO
   Placeholder Valor
   [ESPECIALISTA_DEFINIR] Desenvolvedor de Automações Serverless e Integração de Dados
   [TECNOLOGIAS_DEFINIR] AWS Lambda, Node.js 20.x, API Gateway, Amazon SAM, Google Sheets API
   [DOMINIO_DEFINIR] Captura de Leads, Automação de Formulários e Gestão de Dados
   [OBJETIVO_PRINCIPAL_DEFINIR] Gerar o Template Mestre de Microsserviço que recebe dados de formulários e os registra instantaneamente em Google Sheets.
   [DESCRICAO_DETALHADA_OBJETIVO] Criar código e infraestrutura que permite a replicação rápida para clientes com diferentes tipos de formulários (contato, cadastro, pesquisa).

2. CONTEXTO E INFORMAÇÃO
O Amazon Q precisa de uma definição clara de como o projeto será.

```yaml
# LeadBridge - ESPECIFICAÇÕES TÉCNICAS

Sistema: "Microsserviço de Formulário Web e Integração Google Sheets"
Status: "Novo Projeto - Template Mestre"
Performance: "Latência máxima de 2s na execução da Lambda com validação completa."

# ARQUITETURA AWS

Backend:
  - AWS Lambda: "Função única para processamento de formulários e integração."
  - AWS API Gateway: "Endpoint POST configurado com CORS habilitado."
  - AWS Secrets Manager: "Armazenamento seguro das credenciais Google Service Account."

# FUNCIONALIDADES CORE

Receber Formulário Web:
  - Atributo: "Método POST com CORS configurado"
  - Corpo: "JSON genérico contendo campos personalizáveis (nome, email, telefone, mensagem)"
  
Validar Dados:
  - Atributo: "Validação de email RFC 5322"
  - Atributo: "Sanitização de dados de entrada"
  - Atributo: "Campos obrigatórios configuráveis"
  
Integrar Google Sheets:
  - Atributo: "Autenticação via Google Service Account"
  - Atributo: "Append automático de nova linha na planilha"
  - Atributo: "Uso de variáveis de ambiente para SPREADSHEET_ID e SHEET_NAME"
```

```yaml
# STACK TECNOLÓGICO

Backend:
  - Runtime: "Node.js 20.x"
  - API: "RESTful (API Gateway com CORS)"
  - Auth: "Google Service Account JSON"
  - Validação: "Joi para validação robusta de formulários"

AWS Services:
  - AWS Lambda: "Código de integração e lógica de validação."
  - AWS API Gateway: "Exposição do endpoint com CORS habilitado."
  - AWS Secrets Manager: "Credenciais Google Service Account."
  - Amazon CloudWatch: "Logs de execução, erro e métricas de conversão."
```

3. TAREFA DETALHADA E EXPECTATIVA
Siga estas etapas de raciocínio para executar a tarefa:

3.1. Raciocínio (Chain-of-Thought - CoT)
Defina o Contrato de Dados (Payload) - Garanta que a função Lambda esteja pronta para receber diferentes estruturas de formulários web.

Mapeie a Infraestrutura (IaC) - Gere o arquivo SAM (template.yaml) completo para criar a Lambda, Secrets Manager e o API Gateway com o endpoint /form-submit.

Implemente a Lógica de Validação - Desenvolva o código Node.js para validar campos obrigatórios, formatos de email e sanitizar dados.

Configure Integração Google Sheets - Inclua a lógica para autenticar com Service Account e adicionar dados à planilha especificada.

Crie o README para o Cliente - Descreva claramente como configurar o Google Service Account, obter credenciais e configurar a planilha.

3.2. Ação Principal
Gere o template de projeto completo "LeadBridge-Sheets" incluindo:

Configuração AWS SAM (template.yaml) completa.

Código Node.js da função Lambda com googleapis e validação.

Exemplos de Payload de diferentes tipos de formulários (contato, cadastro, newsletter).

Documentação README.md com instruções de deploy e configuração Google.

4. REGRAS E RESTRIÇÕES DE SAÍDA
O resultado DEVE aderir estritamente às seguintes regras:

Arquitetura: Use exatamente a stack definida: AWS Lambda, API Gateway, Node.js 20.x, Google Sheets API.

Configuração: As credenciais Google Service Account DEVEM ser configuradas via AWS Secrets Manager.

Código: O código Node.js deve ser conciso e limpo, utilizando async/await e tratamento de erros robusto.

CORS: Implementar CORS completo para permitir chamadas de diferentes domínios web.

Entrega: Forneça a saída em formato de blocos de código nomeados (ex: template.yaml, index.js, README.md).

Idioma: Todo código, comentários e documentação em Português do Brasil.

### Diferencial do Template Mestre:
Este projeto serve como **template replicável** para diferentes tipos de formulários:
- Formulário de Contato → Planilha de Leads
- Formulário de Cadastro → Planilha de Clientes  
- Formulário de Pesquisa → Planilha de Feedback
- Newsletter → Planilha de Assinantes
- Outras integrações formulário-planilha