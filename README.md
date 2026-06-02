# 🚀 LifeOS - Estudo Prático com Spec Kit (Spec-Driven Development)

Este projeto tem como objetivo explorar na prática a metodologia **Spec-Driven Development (SDD)** utilizando o **Spec Kit** com integração via **Claude (IA)**.

O sistema desenvolvido é o **LifeOS**, uma plataforma de gerenciamento de tarefas e metas, escolhida por permitir evolução contínua de requisitos — ideal para validar o potencial do SDD.

# 🧠 O que é Spec-Driven Development

Spec-Driven Development é uma abordagem onde:

- A **especificação (SPEC)** é a principal fonte de verdade
- O código é consequência da SPEC
- O sistema evolui a partir da evolução das especificações

### Fluxo padrão:

```

SPEC → PLAN → TASKS → IMPLEMENTAÇÃO

````

---

# 🎯 Objetivo do Projeto

- Testar o uso do Spec Kit com Claude
- Validar evolução de requisitos de forma incremental
- Avaliar impacto das mudanças na arquitetura
- Simular um ciclo real de desenvolvimento orientado por especificação

---

# 📦 Sistema: LifeOS

O LifeOS é um sistema de gestão pessoal que começa simples e evolui progressivamente.

### Funcionalidades iniciais:
- Gerenciamento de tarefas
- Definição de metas

### Evoluções:
- Organização avançada
- Inteligência com IA
- Automação de regras

---

# 📦 Spec Kit - Referência e Instalação

Este projeto utiliza o **Spec Kit**, um toolkit open-source do GitHub para desenvolvimento orientado por especificação (**Spec-Driven Development - SDD**).

👉 Repositório oficial:  
[Spec Kit no GitHub](https://github.com/github/spec-kit)

---

## ⚙️ Pré-requisitos

Antes da instalação, certifique-se de ter:

- Python 3.11 ou superior  
- Git instalado  
- Um agente de IA (ex: Claude)  
- Gerenciador de pacotes `uv`  

---

## 🚀 Instalação do Spec Kit

### 🔹 Instalação recomendada (global)

Instala a CLI do Spec Kit de forma permanente na sua máquina:

```bash
uv tool install specify-cli --from git+https://github.com/github/spec-kit.git
````

Após a instalação, valide:

```bash
specify check
```

✅ Isso garante que o ambiente está pronto para uso.

***

### 🔹 Execução sem instalação (modo teste)

Caso queira apenas testar sem instalar globalmente:

```bash
uvx --from git+https://github.com/github/spec-kit.git specify init --force life-os 
```

✅ Essa abordagem executa diretamente sem instalar no sistema.

***

## 🧪 Inicializando um projeto

Após instalação:

```bash
specify init life-os 
cd life-os
```
#### Obs.: Para usar uma IA direto coloque o parametro --ai claude | cursor | etc...

Isso cria a estrutura inicial do projeto com suporte ao fluxo SDD.

***

## 📌 Observação importante

* A instalação oficial deve sempre ser feita a partir do repositório GitHub
* Pacotes com o mesmo nome fora desse repositório não são mantidos oficialmente [Ver documentação oficial de instalação]([https://github.com/github/spec-kit](https://github.github.com/spec-kit/installation.html))


***


# ⚙️ Setup Inicial

```bash
specify init life-os
cd life-os
````

***

# 🧩 Constituição do Projeto

## Comando

```bash
/speckit.constitution
```

## Prompt

```text
Defina os princípios do sistema LifeOS.

- O sistema deve ser simples e fácil de usar
- Todas as funcionalidades devem ser testáveis
- As APIs devem seguir padrão REST
- Deve suportar crescimento e novas funcionalidades
- O código deve seguir Clean Architecture
- Deve permitir futura integração com IA
- Deve garantir segurança dos dados dos usuários
- Performance deve suportar múltiplos usuários simultâneos
```

***

# 🧪 SPEC Inicial (MVP)

## Comando

```bash
/speckit-specify
```

## Prompt

```text
Construir um sistema chamado LifeOS para gerenciamento de tarefas e metas.

# Problema
Usuários têm dificuldade em organizar tarefas diárias e metas de longo prazo em um único lugar.

# Usuários
- Profissionais
- Estudantes

# Funcionalidades principais
- Criar tarefa com título, descrição e prioridade (baixa, média, alta)
- Listar tarefas ordenadas por prioridade e prazo
- Marcar tarefa como concluída
- Criar metas
- Vincular tarefas a metas
- Adicionar etiquetas (tags)
- Adicionar data de vencimento
- Criar subtarefas

# Escopo do sistema
O sistema deve ser desenvolvido completo, incluindo:
- Backend (API REST)
- Frontend (interface web)
- Integração entre as camadas

# Arquitetura
- Backend: API REST responsável pela lógica de negócio
- Frontend: aplicação web para interação do usuário
- Integração: frontend consome backend via HTTP

# Interface (Frontend)
- Exibir lista de tarefas ordenadas por prioridade e prazo
- Permitir criação, edição e conclusão de tarefas
- Permitir associação de tarefas com metas
- Permitir filtragem por prioridade, prazo e tags
- Interface simples e responsiva

# Backend
- API REST para gerenciamento de tarefas e metas
- Endpoints para criação, edição, listagem e conclusão de tarefas
- Endpoints para gerenciamento de metas
- Persistência de dados

# Regras de negócio
- Toda tarefa deve ter título
- Tarefas concluídas não aparecem na lista padrão
- Uma tarefa pertence a apenas uma meta
- Uma meta pode ter várias tarefas
- Subtarefas devem pertencer a uma tarefa principal
- Tarefas com data devem ser ordenadas por prazo

# Casos extremos
- Tarefa sem título
- Tarefas duplicadas
- Grande volume de tarefas (>10k)

# Requisitos não funcionais
- Tempo de resposta < 500ms
- Persistência obrigatória
- Preparado para futuras funcionalidades com IA
- Interface deve ser simples e responsiva
- Comunicação entre frontend e backend via API REST

# Fora do escopo
- Inteligência artificial (IA)
- Integrações externas
```

***

# 🔍 Refinamento da SPEC

## Comando

```bash
/speckit-clarify
```

## Prompt

```text
Esclareça como deve funcionar a ordenação das tarefas quando possuem a mesma prioridade.

Definir:

- Qual critério secundário deve ser usado (ex: data de vencimento ou data de criação)
- Como ordenar tarefas que tenham a mesma prioridade e mesma data
- Qual comportamento quando a tarefa não tiver data de vencimento

Requisitos:

- A ordenação deve ser consistente (mesma entrada gera o mesmo resultado)
- Deve funcionar da mesma forma no backend e no frontend

Incluir exemplos simples de ordenação.
```

***

# 🏗️ Plano Técnico

## Comando

```bash
/speckit-plan 
```

## Prompt

```text
Gerar o plano técnico do LifeOS considerando:

- Backend: API REST para gerenciamento de tarefas e metas
- Frontend: aplicação web para interação do usuário
- Integração entre frontend e backend via HTTP

- Modelo de dados para tarefas, metas e subtarefas
- Estrutura modular do sistema (separação backend e frontend)
- Definição de entidades principais (tarefas e metas)
- Definição dos principais endpoints REST
- Preparação para evolução futura do sistema

Requisitos:
- Manter consistência com a SPEC definida
- Garantir separação clara entre frontend e backend
- Priorizar simplicidade e organização do código
```

📌 **IMPORTANTE:**
Após gerar o planejamento, revise o resultado. Caso ele não esteja alinhado com o objetivo do projeto, ajuste o prompt e execute novamente o comando de planejamento.
Por exemplo, neste caso, como a linguagem não foi especificada inicialmente, o plano gerado utilizou Python. No entanto, como o objetivo é utilizar Java com PostgreSQL, é necessário refinar o planejamento.
Para isso, utilize novamente o comando /speckit.plan, informando explicitamente a tecnologia desejada no prompt.
   
```text
Atualizar o plano técnico do LifeOS para utilizar Java no backend ao invés de Python.

Requisitos:

- Backend deve ser implementado em Java (preferencialmente Spring Boot)
- Banco de dados deve ser PostgreSQL em todos os ambientes (inclusive no MVP)
- Manter API REST e contratos já definidos
- Manter arquitetura definida na SPEC (separação entre frontend e backend)
- Preservar modelo de dados e endpoints planejados

Manter:

- Frontend conforme definido (React)
- Integração entre frontend e backend via HTTP
- Regras de negócio já definidas

Garantir:

- Compatibilidade com o restante do sistema
- Estrutura modular e escalável
- Coerência entre backend, frontend e banco de dados
```
 


***

# 📋 Geração de Tarefas

## Comando

```bash
/speckit-tasks 
```

## Prompt

```text
Gerar tarefas de desenvolvimento do LifeOS.

Requisitos:

- Tarefas pequenas, claras e independentes
- Separar tarefas de backend (Java + Spring Boot) e frontend (React)
- Incluir persistência utilizando PostgreSQL em todos os ambientes
- Incluir testes automatizados para backend e frontend
- Garantir integração entre frontend e backend via API REST

Considerar:

- Funcionalidades definidas na SPEC (tarefas, metas, tags, subtarefas)
- Arquitetura definida (separação frontend e backend)
- Endpoints REST planejados
- Modelo de dados definido no plano técnico

Organização:

- Agrupar tarefas por camada (backend, frontend, integração, testes)
- Indicar dependências entre tarefas quando necessário
```

***

## 🔧 Implementação Fase 1 — MVP

## Comando

```bash
/speckit.implement 
```

## Prompt para implementar todo o codigo de uma vez

```text
Implementar o sistema LifeOS seguindo as tarefas definidas e organizadas por fases.

Requisitos:

- Implementar o backend em Java (Spring Boot) conforme definido no plano
- Implementar o frontend em React
- Utilizar PostgreSQL como banco de dados em todos os ambientes
- Garantir integração entre frontend e backend via API REST

Execução:

- Seguir a ordem das fases (Phase 1, Phase 2, Phase 3, etc.)
- Concluir cada fase totalmente antes de avançar para a próxima
- Implementar inicialmente as funcionalidades do MVP e Evolução 1

Considerar:

- Funcionalidades definidas na SPEC (tarefas, metas, tags e subtarefas)
- Arquitetura definida (separação front-end e back-end)
- Modelo de dados e endpoints definidos no plano
- Tarefas geradas na fase de /speckit.tasks

Garantir:

- Código organizado e modular
- Consistência entre backend, frontend e banco de dados
- Inclusão de testes automatizados
- Não alterar regras fora do escopo definido

```

## Prompt para implementar em fases
### 🟢 Fase 1 
```text
Implementar a Phase 1 (Setup) do sistema LifeOS conforme definido nas tarefas.

Requisitos:

- Backend em Java (Spring Boot)
- Frontend em React (Vite + TypeScript)
- Banco de dados PostgreSQL via docker-compose

Execução:

- Criar estrutura inicial do backend e frontend
- Configurar dependências e organização de pastas
- Configurar docker-compose com PostgreSQL
- Preparar ambiente de desenvolvimento

Garantir:

- Estrutura base do projeto funcional
- Backend e frontend inicializados corretamente
- Banco PostgreSQL disponível
- Não avançar para fases seguintes
```
### 🟢 Fase 2 
```text
Implementar a Phase 2 (Foundational) do sistema LifeOS.

Requisitos:

- Backend em Java (Spring Boot)
- Banco PostgreSQL obrigatório
- Persistência com JPA e Flyway
- Integração preparada para frontend

Execução:

- Implementar modelo de dados (Task, enums, entidades)
- Configurar Flyway e schema inicial
- Implementar repositórios e persistência
- Implementar algoritmo de ordenação (TaskSortOrder)
- Configurar infraestrutura base (CORS, OpenAPI, exception handler)

Frontend:

- Criar tipos e estrutura base
- Implementar função de ordenação (taskSort)
- Criar cliente HTTP base

Garantir:

- Persistência funcionando com PostgreSQL
- Ordenação consistente entre backend e frontend
- Testes unitários e integração da base
- Não iniciar user stories antes da conclusão
```
### 🟢 Fase 3 
```text
Implementar a Phase 3 (User Story 1 — MVP) do sistema LifeOS.

Objetivo:

- Criar, listar e concluir tarefas

Execução:

Backend:
- Implementar casos de uso (CreateTask, ListPendingTasks, CompleteTask)
- Criar endpoints REST
- Implementar DTOs

Frontend:
- Criar API client (tasks.ts)
- Criar hooks (useTasks)
- Criar componentes (TaskForm, TaskList, TaskItem)
- Criar página principal (TasksPage)

Integração:
- Conectar frontend ao backend
- Validar fluxo completo (criar → listar → concluir)

Garantir:

- Sistema funcional end-to-end
- Persistência em PostgreSQL
- Testes passando
- Não implementar funcionalidades das próximas fases
```

### 🟢 Fase 4 
```text
Implementar a Phase 4 (User Story 2) do sistema LifeOS.

Objetivo:

- Edição de tarefas e gestão de prazos

Execução:

Backend:
- Implementar UpdateTask, ListCompletedTasks, UncompleteTask
- Criar novos endpoints

Frontend:
- Implementar edição de tarefas
- Criar página de tarefas concluídas
- Atualizar componentes existentes

Integração:
- Garantir reordenação após mudanças de prazo
- Validar consistência com dados existentes

Garantir:

- Não quebrar funcionalidades do MVP
- Integração total com Phase 3
- Testes cobrindo novas regras
```

### 🟢 Fase 5 
```text
Implementar a Phase 5 (User Story 3) do sistema LifeOS.

Objetivo:

- Implementar metas e vínculo com tarefas

Execução:

Backend:
- CRUD de Goal
- Implementar vínculo Task ↔ Goal

Frontend:
- Criar telas de metas
- Permitir vinculação de tarefas

Integração:
- Validar vínculo e desvínculo
- Garantir consistência dos dados

Garantir:

- Não impactar funcionalidades anteriores
- Funcionalidade totalmente integrada

```

### 🟢 Fase 6 
```text
Implementar a Phase 6 (User Story 4) do sistema LifeOS.

Objetivo:

- Tags, filtros e subtarefas

Execução:

Backend:
- Implementar entidades Tag e Subtask
- Implementar filtros na listagem

Frontend:
- Criar filtros
- Implementar tags e subtarefas na UI

Integração:
- Validar filtros e visibilidade correta
- Garantir que subtarefas não aparecem na lista principal

Garantir:

- Consistência com funcionalidades anteriores
- Testes cobrindo cenários novos
```

### 🟢 Fase 7 
```text
Implementar a Phase 7 (Polish) do sistema LifeOS.

Objetivo:

- Finalizar sistema para uso completo

Execução:

Backend:
- Implementar paginação
- Ajustes de performance

Frontend:
- Melhorar responsividade
- Feedback de loading e erro

Integração:
- Completar docker-compose (backend + frontend)
- Validar fluxo completo

Testes:
- Implementar E2E com Playwright
- Validar todos os fluxos

Garantir:

- Sistema completo e estável
- Performance adequada
- Cobertura de testes
```

***

📌 **IMPORTANTE - ERROS COMUNS:**
 - ❌ Usar o mesmo prompt para todas as fases
   - **Resultado**:
     - IA reescreve tudo
     - perde contexto
- ❌ Não limitar a fase
  - **Resultado**:
    - IA tenta implementar tudo de novo
- ❌ Não falar de consistência
  - **Resultado**:
    - quebra o código existente


# 🔁 Evolução do Sistema

O principal objetivo do projeto é testar evolução incremental da SPEC.

***

## 🟡 Evolução 1 — Organização

```bash
/speckit-specify
```

```text
Adicionar organização de tarefas.

# Funcionalidades
- Etiquetas (tags)
- Datas de vencimento
- Subtarefas

# Regras
- Subtarefas pertencem a uma tarefa
- Ordenação por prazo quando houver data
```

***

## 🔵 Evolução 2 — Inteligência

```bash
/speckit-specify
```

```text
Adicionar inteligência ao sistema.

# Funcionalidades
- Sugestão automática de tarefas do dia
- Identificação de tarefas atrasadas
- Recomendações de foco

# Regras
- Tarefas atrasadas devem ter maior prioridade
```

***

## 🔴 Evolução 3 — Automação

```bash
/speckit-specify
```

```text
Adicionar automações ao LifeOS.

# Funcionalidades
- Definição de regras automáticas

Exemplos:
- Se tarefa atrasar → aumentar prioridade
- Se meta estiver próxima → priorizar tarefas associadas

# Requisitos
- Regras devem ser configuráveis
- Execução automática das regras
```

***
# ✅ Estratégia de Implementação - Evoluções 1, 2 e 3
## 🔧 Implementação Fase 1, 2 e 3 

## Comando

```bash
/speckit.implement 
```

## Prompt

```text
Implemente as evoluções do LifeOS considerando:

- Funcionalidades de Organização (Evolução 1)
- Funcionalidades de inteligência (Evolução 2)
- Funcionalidades de automação (Evolução 3)
- Integração com a base existente

Requisitos:
- Manter consistência com arquitetura inicial
- Garantir reaproveitamento de código
- Aplicar boas práticas
- Garantir testabilidade
```

***


# 🧠 Testes Avançados

## Mudança de Regra

```text
Alterar o sistema de prioridade de fixo (baixa, média, alta) para dinâmico (0 a 100)
```

***

## Conflito de Requisitos

```text
Sistema deve ser altamente performático e garantir consistência total dos dados
```

***

## Escala

```text
Sistema deve suportar até 1 milhão de tarefas por usuário
```

***

# 📂 Estrutura Esperada

```
.specify/
specs/
  lifeos-mvp/
  lifeos-organizacao/
  lifeos-inteligencia/
  lifeos-automacao/
```

***

# ✅ Conclusão

Este projeto permite validar na prática:

* Evolução incremental orientada por SPEC
* Redução de ambiguidades antes da implementação
* Impacto de mudanças de requisitos
* Qualidade do planejamento gerado por IA com contexto estruturado

O foco principal é entender como:

> **A especificação guia todo o ciclo de desenvolvimento**

***

# 🚀 Próximos Passos

Possíveis evoluções:

* Arquitetura com microsserviços
* Integrações com APIs externas
* Engine de regras avançada
* Assistente inteligente com IA

***

# 📌 Observação

Este projeto é experimental e focado em aprendizado da metodologia Spec-Driven Development com suporte de IA (Claude).

***
