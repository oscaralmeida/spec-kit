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
- Listar tarefas ordenadas por prioridade
- Marcar tarefa como concluída
- Criar metas
- Vincular tarefas a metas

# Regras de negócio
- Toda tarefa deve ter título
- Tarefas concluídas não aparecem na lista padrão
- Uma tarefa pertence a apenas uma meta
- Uma meta pode ter várias tarefas

# Casos extremos
- Tarefa sem título
- Tarefas duplicadas
- Grande volume de tarefas (>10k)

# Requisitos não funcionais
- Tempo de resposta < 500ms
- Persistência obrigatória
- Preparado para futuras funcionalidades com IA

# Fora do escopo
- IA
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

- API backend
- Modelo de dados
- Estrutura modular
- Entidades de tarefas e metas
- Endpoints REST
- Preparação para evolução futura
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
- Tarefas pequenas e independentes
- Incluir backend e persistência
- Incluir testes automatizados
```

***

## 🔧 Implementação Fase 1 — MVP

## Comando

```bash
/speckit.implement 
```

## Prompt

```text
Implemente o sistema LifeOS considerando:

- Funcionalidades do MVP
- Evolução 1 aplicada (organização de tarefas)
- Backend com API REST
- Persistência de dados
- Estrutura modular
- Inclusão de testes
```

***

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
