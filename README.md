# Agente de IA - Agendamento de Consultorias

Sistema automatizado de atendimento e agendamento de consultorias desenvolvido por **Robson Rodrigues** utilizando n8n, LangChain e integração com Google Workspace.

## 📋 Descrição

O Agente de IA é um sistema inteligente que automatiza o processo de atendimento e agendamento de consultorias da **Consulta Tech**. O agente utiliza inteligência artificial para interagir com clientes via WhatsApp, fornecer informações sobre serviços e realizar agendamentos automaticamente.

## 🚀 Funcionalidades

### 🤖 Atendimento Inteligente

- **Apresentação automática** da empresa e serviços
- **Coleta de informações** do cliente (nome, email)
- **Respostas contextuais** baseadas em documentos da empresa
- **Processamento de linguagem natural** para entender intenções do cliente

### 📅 Agendamento Automático

- **Integração com Google Calendar** via MCP (Model Context Protocol)
- **Consulta de disponibilidade** em tempo real
- **Agendamento automático** de consultorias
- **Confirmação via email** para o cliente

### 📊 Gestão de Serviços

- **Integração com Google Sheets** para catálogo de serviços
- **Preços e descrições** atualizados automaticamente
- **Validação de serviços** disponíveis

### 📚 Base de Conhecimento Inteligente

- **Leitura de documentos** (PDFs, DOCX, etc.)
- **RAG (Retrieval-Augmented Generation)** para respostas precisas
- **Vector Store** com Supabase para busca semântica
- **Embeddings** com Google Gemini

## 🏗️ Arquitetura

### Componentes Principais

```
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   WhatsApp      │    │      n8n        │    │   Google AI     │
│   (Twilio)      │◄──►│   Workflow      │◄──►│   (Gemini)      │
└─────────────────┘    └─────────────────┘    └─────────────────┘
                              │
                              ▼
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   PostgreSQL    │    │    Supabase     │    │   Google Workspace │
│   (Memory)      │◄──►│  Vector Store   │◄──►│  (Calendar/Sheets) │
└─────────────────┘    └─────────────────┘    └─────────────────┘
```

### Tecnologias Utilizadas

- **n8n**: Automação de workflow
- **LangChain**: Framework de IA
- **Google Gemini**: Modelo de linguagem
- **PostgreSQL**: Memória de conversas
- **Supabase**: Vector store para RAG
- **Twilio**: Integração WhatsApp
- **Google Workspace**: Calendar e Sheets
- **MCP**: Model Context Protocol

## ⚙️ Configuração

### Pré-requisitos

1. **Conta n8n** (self-hosted ou cloud)
2. **Google Cloud Project** com APIs habilitadas
3. **Conta Twilio** para WhatsApp Business
4. **Banco PostgreSQL** (pode ser Supabase)
5. **Conta Supabase** para vector store

### Credenciais Necessárias

```json
{
	"googlePalmApi": "CREDENTIAL_ID_PLACEHOLDER",
	"postgres": "CREDENTIAL_ID_PLACEHOLDER",
	"supabaseApi": "CREDENTIAL_ID_PLACEHOLDER",
	"httpBasicAuth": "CREDENTIAL_ID_PLACEHOLDER"
}
```

### Configuração do Workflow

1. **Importar o workflow** `AGENTE de IA - Agendamento de consultorias.json`
2. **Configurar credenciais** para cada serviço
3. **Ajustar endpoints MCP** para Google Sheets e Calendar
4. **Configurar webhook** para receber mensagens do WhatsApp
5. **Ativar o workflow**

### Configuração MCP

#### Google Sheets

```bash
# Endpoint para catálogo de serviços
MCP_ENDPOINT_PLACEHOLDER
```

#### Google Calendar

```bash
# Endpoint para agendamentos
MCP_ENDPOINT_PLACEHOLDER
```

## 🔧 Estrutura do Projeto

```
atendente-de-agendamento-para-consultoria/
├── AGENTE de IA - Agendamento de consultorias.json  # Workflow n8n
└── README.md                                        # Documentação
```

## 📱 Fluxo de Atendimento

1. **Cliente envia mensagem** via WhatsApp
2. **Agente se apresenta** e apresenta a empresa
3. **Solicita nome** do cliente
4. **Lista serviços** disponíveis com preços
5. **Coleta email** do cliente
6. **Consulta disponibilidade** no calendário
7. **Agenda consultoria** automaticamente
8. **Envia confirmação** para o cliente

## 🎯 Características do Agente

- **Nome**: Ianis
- **Empresa**: Consulta Tech
- **Duração das consultorias**: 1 hora
- **Formato do título**: "Consultoria - Nome do cliente (nome do serviço)"
- **Participantes**: Cliente adicionado via email

## 🔒 Segurança

- **Credenciais protegidas** com placeholders
- **Webhooks seguros** para comunicação
- **Autenticação** via HTTP Basic Auth
- **Dados sensíveis** não expostos no código

## 📈 Monitoramento

- **Logs de conversas** no PostgreSQL
- **Histórico de agendamentos** no Google Calendar
- **Métricas de atendimento** via n8n
- **Rastreamento de erros** integrado

---

**Desenvolvido com ❤️ por Robson Rodrigues**
