# OTIS SmartFlow IA — Plataforma Integrada de Gestão & Telemetria

Repositório oficial da plataforma **OTIS SmartFlow IA**, integrando backend Spring Boot, motor analítico FastAPI em Python e frontend React.

---

## 📁 Estrutura de Pastas

```
otis-smartflow/
├── backend/
│   ├── smartflow-api/       # Backend Java 17 + Spring Boot 3.3.4 (REST API, H2/PostgreSQL)
│   └── smartflow-reports/   # Analytics & Relatórios Python 3.12 + FastAPI (PDF & Excel)
├── frontend/                # Aplicação Frontend React 19 + Vite + TypeScript + Tailwind
├── PLANO_ARQUITETURA.md     # Documentação detalhada da arquitetura do sistema
├── Plano_Arquitetura_Backend_SmartFlow.pdf # Versão executiva em PDF da arquitetura
├── supabase_smartflow_schema.sql # Script SQL completo do banco de dados
└── package.json             # Scripts unificados de inicialização do projeto
```

---

## 📄 Documentação e Plano de Arquitetura

- 📘 **Plano de Arquitetura em Markdown:** [`PLANO_ARQUITETURA.md`](./PLANO_ARQUITETURA.md)
- 📑 **Plano de Arquitetura Oficial em PDF:** [`Plano_Arquitetura_Backend_SmartFlow.pdf`](./Plano_Arquitetura_Backend_SmartFlow.pdf)
- 🗄️ **Schema do Banco de Dados:** [`supabase_smartflow_schema.sql`](./supabase_smartflow_schema.sql)

---

## 🏛️ Visão Geral dos Serviços

1. **Backend Core (Java 17 + Spring Boot 3.3.4):**
   - Localizado em `backend/smartflow-api/`.
   - APIs REST para gestão de equipamentos, chamados, técnicos e telemetria.
   - Banco de dados em memória H2 (dev) e suporte a PostgreSQL / Supabase.
   - Swagger / OpenAPI: `http://localhost:8080/swagger-ui.html`.
   - Console H2: `http://localhost:8080/h2-console`.

2. **Reports & Analytics Engine (Python 3.12 + FastAPI):**
   - Localizado em `backend/smartflow-reports/`.
   - Geração de relatórios executivos em PDF com diagramação OTIS (ReportLab).
   - Geração de planilhas Excel avançadas com fórmulas e DRE (OpenPyXL).
   - Documentação FastAPI: `http://localhost:8000/docs`.

3. **Frontend (React + Vite + TypeScript):**
   - Localizado em `frontend/`.
   - Dashboards interativos (Presidente, Gerente, Supervisor, Técnico, Atendente) e emissão de relatórios.
   - Acesso padrão: `http://localhost:3000` ou `http://localhost:5173`.

---

## 🚀 Como Executar

### 1. Iniciar o Serviço de Relatórios Python (Porta 8000)
```powershell
cd backend/smartflow-reports
uvicorn main:app --port 8000 --reload
```

### 2. Iniciar o Backend Spring Boot (Porta 8080)
```powershell
cd backend/smartflow-api
.\mvnw.cmd spring-boot:run
```

### 3. Iniciar o Frontend React (Porta 3000 / 5173)
```powershell
cd frontend
npm run dev
```

---

## 🧪 Testes

Executar testes automatizados do Spring Boot:
```powershell
cd backend/smartflow-api
.\mvnw.cmd test
```
