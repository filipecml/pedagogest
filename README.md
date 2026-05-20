# PedagoGest (em desenvolvimento)

> Sistema de gestão pedagógica inteligente para espaços de reforço escolar com foco em crianças atípicas.

![Status](https://img.shields.io/badge/status-em%20desenvolvimento-yellow)
![Java](https://img.shields.io/badge/Java-17-orange)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.x-green)
![React](https://img.shields.io/badge/React-18-blue)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-15-316192)
![License](https://img.shields.io/badge/license-MIT-lightgrey)

---

## Sobre o projeto

O PedagoGest nasceu da necessidade real de um espaço de reforço escolar especializado em crianças com perfil atípico (TEA, TDAH, dislexia, entre outros). O sistema substitui planilhas e controles manuais por uma plataforma centralizada que une gestão pedagógica, financeira e de comunicação.

O diferencial está no módulo pedagógico: cada aluno possui um **Plano de Desenvolvimento Individual (PDI)** com acompanhamento de evolução ao longo do tempo, permitindo que orientadores registrem laudos, metas e progressos de forma estruturada.

---

## Funcionalidades

### Gestão de alunos
- Cadastro completo com diagnóstico, ano escolar e perfil de atendimento
- Vínculo com responsável financeiro (pai, mãe, avó, responsável legal)
- Histórico de presença e evolução por semestre

### Relatórios pedagógicos
- Criação e gestão de PDIs individuais por aluno
- Registro de laudos com anexo de documentos
- Timeline de evolução com visualização progressiva
- Exportação de relatórios em PDF

### Gestão financeira
- Controle de mensalidades com status (pago, pendente, inadimplente)
- Suporte a múltiplos meios de pagamento: dinheiro, PIX, transferência
- Dashboard com receita prevista vs. recebida e indicador de inadimplência

### Agenda e turmas
- Organização de turmas por horário (slots fixos de 1h, das 8h às 20h)
- Controle de capacidade por turma e por orientador
- Registro de presença com visualização semanal

### Notificações
- Integração com WhatsApp via API para comunicação com responsáveis
- Alertas automáticos de cobranças pendentes e confirmação de horários

---

## Stack técnica

| Camada | Tecnologia |
|---|---|
| Back-end | Java 17, Spring Boot 3, Spring Security, JWT |
| Front-end | React 18, TypeScript, React Router, TanStack Query |
| Banco de dados | PostgreSQL 15 |
| ORM | JPA / Hibernate, Liquibase |
| Mensageria | Kafka |
| Cache | Redis |
| Infra | Docker, Kubernetes, Maven |
| Scaffold | JHipster 8 |
| Testes | JUnit 5, Mockito |
| CI/CD | GitHub Actions |

---

## Arquitetura

O sistema adota arquitetura de microsserviços com os seguintes módulos principais:

```
pedagogest/
├── pedagogest-gateway/        # API Gateway (Spring Cloud Gateway)
├── pedagogest-alunos/         # Serviço de gestão de alunos e turmas
├── pedagogest-pedagogico/     # Serviço de PDIs, laudos e relatórios
├── pedagogest-financeiro/     # Serviço de mensalidades e pagamentos
├── pedagogest-notificacoes/   # Serviço de notificações (WhatsApp/e-mail)
└── pedagogest-frontend/       # SPA em React + TypeScript
```

---

## Modelo de dados (resumo)

As entidades principais do sistema:

- `Aluno` — dados pessoais, diagnóstico, ano escolar, status de matrícula
- `Responsavel` — responsável financeiro vinculado ao aluno
- `Turma` — slot de horário, orientador responsável, capacidade
- `Presenca` — registro de presença por aluno por aula
- `PDI` — Plano de Desenvolvimento Individual por aluno/semestre
- `Laudo` — documentos e registros clínicos/pedagógicos
- `Mensalidade` — controle financeiro mensal por aluno
- `Pagamento` — registros de pagamentos com meio e data

O modelo completo está documentado em [`espaco-pedagogico.jdl`](./espaco-pedagogico.jdl).

---

## Como executar (em breve)

> Esta seção será atualizada conforme o projeto avança.

```bash
# Pré-requisitos: Java 17+, Node 18+, Docker

git clone https://github.com/filipecml/pedagogest.git
cd pedagogest
docker-compose up -d        # sobe PostgreSQL + Redis + Kafka
./mvnw spring-boot:run      # back-end na porta 8080
cd pedagogest-frontend
npm install && npm start    # front-end na porta 3000
```

---

## Status do desenvolvimento

- [x] Levantamento de requisitos com usuário real (gestora do espaço)
- [x] Modelagem de domínio e JDL completo
- [x] Definição da arquitetura de microsserviços
- [x] Escolha do stack e configuração do ambiente
- [ ] Geração do scaffold com JHipster
- [ ] Módulo de alunos e turmas (back-end)
- [ ] Módulo financeiro (back-end)
- [ ] Módulo pedagógico — PDI e laudos (back-end)
- [ ] Interfaces React — dashboards e formulários
- [ ] Integração WhatsApp
- [ ] Testes automatizados (meta: 70% de cobertura)
- [ ] Deploy em AWS com CI/CD via GitHub Actions

---

## Por que este projeto?

A maioria dos sistemas de gestão escolar disponíveis no mercado não foi pensada para espaços pequenos com perfil especializado em crianças atípicas. O PedagoGest resolve um problema real: a gestora de um espaço pedagógico real em Recife-PE gerenciava tudo em anotações manuais e WhatsApp, sem histórico estruturado de evolução dos alunos nem controle financeiro confiável.

---

## Autor

**Filipe Moreira Cabral** — Full Stack Java Developer
[linkedin.com/in/filipe-moreira](https://linkedin.com/in/filipe-moreira) · [github.com/filipecml](https://github.com/filipecml)
