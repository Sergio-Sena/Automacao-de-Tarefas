# Prompt C.E.R.T.O - LeadBridge Formulário para Sheets

## 1. PAPEL E OBJETIVO (O P de C.E.R.T.O)

Você é um **Desenvolvedor de Automações Serverless** com expertise em **AWS Lambda, Node.js, API Gateway e Google Sheets API** e **Integração de Dados e Automação de Fluxos de Trabalho (Workflow Automation)**.

Seu objetivo principal é **Criar um endpoint HTTP para receber dados de formulário e registrar instantaneamente em uma planilha do Google Sheets** - **Desenvolver uma função Lambda, acessível via API Gateway, que receba um POST com dados de um formulário web e insira uma nova linha na planilha, com tratamento de erro e validação de dados**.

## 2. CONTEXTO E INFORMAÇÃO (O C de C.E.R.T.O)

### 2.1. Conhecimento Base (Sistema/Aplicação)

```yaml
# LeadBridge - Formulário para Sheets - ESPECIFICAÇÕES TÉCNICAS
Sistema: "RESTful API para Integração Formulário-Sheets"
Status: "Desenvolvimento"
URL: "https://api-gateway-endpoint.amazonaws.com/prod/form-submit"
Performance: "< 2s resposta, 99.9% uptime"

# ARQUITETURA AWS
Frontend:
  - API_Gateway: "REST API com CORS habilitado"
  - CloudWatch: "Logs e monitoramento de performance"
  - IAM: "Roles para Google Sheets API"

Backend:
  - Lambda: "Node.js 20.x runtime"
  - Secrets_Manager: "Credenciais Google Service Account"
  - EventBridge: "Opcional para processamento assíncrono"

# FUNCIONALIDADES CORE
Receber_POST_Formulário:
  - Endpoint: "/form-submit"
  - Método: "POST"
  - Payload: "JSON (nome, email, telefone)"

Validar_Dados:
  - Email: "Formato válido RFC 5322"
  - Nome: "Mínimo 2 caracteres, sem números"
  - Telefone: "Formato brasileiro opcional"

Integração_Sheets_API:
  - Biblioteca: "googleapis"
  - Autenticação: "Service Account Key"
  - Operação: "Append values to sheet"

Resposta_Cliente:
  - Sucesso: "HTTP 200 com mensagem"
  - Erro: "HTTP 400/500 com detalhes"
  - CORS: "Habilitado para domínios web"

# DESIGN SYSTEM
Tema: "API responses estruturadas"
Cores: "N/A (Backend)"
Animações: "N/A (Backend)"
Responsivo: "N/A (Backend)"
Mode: "Produção com logs detalhados"
```

### 2.2. Ambiente e Escopo

```yaml
# STACK TECNOLÓGICO
Frontend:
  - Framework: "API Gateway REST"
  - Linguagem: "JSON Schema validation"
  - Estilização: "N/A"
  - Componentes: "N/A"

Backend:
  - Runtime: "Node.js 20.x"
  - API: "RESTful (usando API Gateway)"
  - Auth: "Google Service Account"
  - Validação: "Joi ou express-validator"

AWS Services:
  - Lambda: "Função de processamento principal"
  - API_Gateway: "Endpoint público REST"
  - Secrets_Manager: "Google Service Account JSON"
  - CloudWatch: "Logs e métricas de performance"

# ESTRUTURA DE PASTAS
leadbridge/
├── src/                     # Código fonte
│   ├── handlers/           # Handlers da Lambda
│   └── index.js            # Função principal
├── tests/                  # Testes unitários
│   └── test_form.js        # Testes do formulário
└── infrastructure/         # Infraestrutura
    └── template.yaml       # SAM template
```

## 3. TAREFA DETALHADA E EXPECTATIVA (O T de C.E.R.T.O)

Siga estas etapas de raciocínio para executar a tarefa:

### 3.1. Raciocínio (Chain-of-Thought - CoT)

**Pense passo a passo** antes de gerar a resposta final:

1. **Analise a arquitetura AWS** - Identifique Lambda, API Gateway, Secrets Manager e configurações do Google Sheets API
2. **Mapeie a estrutura Node.js** - Defina estrutura de pastas, handlers, validações e sistema de processamento de formulários
3. **Implemente Receber POST de Formulário** - Aceitar dados JSON (nome, email, telefone) com validação de payload
4. **Configure Validar Dados** - Verificar se os campos obrigatórios estão preenchidos e formatados corretamente
5. **Desenvolva Integração Sheets API** - Usar googleapis para autenticar e escrever os dados na planilha
6. **Crie Resposta ao Cliente** - Retornar HTTP 200 (Sucesso) ou 400/500 (Erro) com mensagem de feedback
7. **Aplique tratamento de erros** - Logs estruturados e respostas padronizadas
8. **Configure infraestrutura** - SAM template com CORS e monitoramento

### 3.2. Ação Principal

**Gere a estrutura completa do projeto LeadBridge** incluindo:
- Configuração AWS completa (SAM template)
- Código Node.js com googleapis
- Função Lambda modular
- Sistema de validação de formulários
- Receber POST de Formulário com validação robusta
- Integração Google Sheets API com autenticação Service Account
- Validação de dados com sanitização
- Resposta estruturada ao cliente
- Scripts de deploy e configuração

## 4. REGRAS E RESTRIÇÕES DE SAÍDA (O R de C.E.R.T.O)

O resultado DEVE aderir estritamente às seguintes regras:

1. **Arquitetura:** Use **exatamente** a stack definida: Node.js 20.x, AWS Lambda, API Gateway, Google Sheets API
2. **Estrutura:** Mantenha a **estrutura de pastas** conforme especificado
3. **Funcionalidades:** Implemente **todas as funcionalidades** listadas no contexto
4. **Design:** Replique o **API responses estruturadas** com tratamento de erros
5. **Performance:** Garanta **< 2s resposta, 99.9% uptime** e otimizações necessárias
6. **Segurança:** Implemente **Google Service Account auth**, validação e sanitização
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
- Handlers de formulário
- Integração Google Sheets API
- Configurações de build e deploy

### 5.3. Documentação Técnica
- README.md detalhado
- Guia de setup AWS e Google Sheets
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

- [ ] ✅ Receber POST de Formulário com validação completa
- [ ] ✅ Validar Dados com sanitização robusta
- [ ] ✅ Integração Sheets API com Service Account
- [ ] ✅ Resposta ao Cliente estruturada
- [ ] ✅ Tratamento de erros completo
- [ ] ✅ Lambda configurada
- [ ] ✅ API Gateway com CORS
- [ ] ✅ Secrets Manager para credenciais Google
- [ ] ✅ Logs estruturados CloudWatch
- [ ] ✅ Performance < 2s resposta
- [ ] ✅ Monitoramento e alertas
- [ ] ✅ Deploy automatizado SAM
- [ ] ✅ Documentação completa em português

---

**🎯 OBJETIVO FINAL:** Sistema LeadBridge 100% funcional, implementando integração segura de formulários web com Google Sheets, com performance e validação especificados.