# Family Grocery App

## 1. Objetivo

Criar um aplicativo de compras compartilhado para famílias.

Uma família pode criar sua própria conta/grupo e convidar seus membros para usar o mesmo aplicativo.

O app permitirá que os membros da família:

* Criem e gerenciem listas de compras
* Vejam alterações em tempo real
* Registrem compras realizadas
* Salvem recibos e informações das compras
* Consultem o histórico de compras
* Conversem pelo app

O objetivo é criar um produto que resolva um problema real e possa ser usado por qualquer família.

A primeira família a testar o aplicativo será a família do desenvolvedor.

---

## 2. Famílias e Usuários

O sistema deve suportar várias famílias.

Cada família terá seus próprios membros e dados.

Exemplo:

```text
Família A

├── Pessoa 1
├── Pessoa 2
└── Pessoa 3

Família B

├── Pessoa 1
├── Pessoa 2
├── Pessoa 3
└── Pessoa 4
```

Uma família nunca deve conseguir acessar os dados de outra família.

Cada usuário terá sua própria conta e poderá pertencer a uma família.

O número de membros não deve ser limitado a três pessoas pelo código do aplicativo.

### Primeiros usuários

A primeira família usada para testar o produto será:

* Vini
* Mãe
* Pai

Eles serão apenas os primeiros usuários, não uma limitação do sistema.

---

## 3. Lista de Compras

Cada família poderá ter uma ou mais listas de compras.

### Funcionalidades

* Adicionar item
* Editar item
* Deletar item
* Marcar item como comprado
* Desmarcar item
* Definir quantidade
* Todos os membros autorizados podem modificar a lista
* Alterações aparecem em tempo real

### Exemplo

```text
Shopping List

☐ Milk              2
☐ Rice              1
☑ Chicken           2
☐ Bananas           1
```

---

## 4. Compras

Depois que uma compra for realizada, será possível registrar a compra.

### Informações

* Mercado
* Data
* Produtos
* Quantidade
* Preço
* Total da compra

### Exemplo

```text
Costco

September 27, 2026

Milk               $4.99
Rice              $12.49
Chicken           $18.32
Bananas            $3.79

Total             $39.59
```

---

## 5. Recibos

Possibilidade de salvar informações do recibo da compra.

### Inicialmente

Registrar os dados manualmente.

### Futuramente

Permitir:

* Upload de foto do recibo
* Armazenar a imagem
* Ler automaticamente os dados do recibo
* Usuário revisar os dados antes de salvar

---

## 6. Histórico

Todas as compras realizadas ficam salvas.

Será possível visualizar:

* Data
* Mercado
* Total
* Produtos comprados

### Exemplo

```text
Purchase History

09/27/2026    Costco     $64.58
09/20/2026    Costco     $91.24
09/13/2026    Walmart    $47.82
```

Clicar em uma compra mostra seus detalhes.

---

## 7. Chat

Cada família terá um chat privado para seus membros.

### Funcionalidades

* Enviar mensagens
* Receber mensagens em tempo real
* Mostrar quem enviou
* Mostrar horário
* Salvar mensagens no banco

### Futuramente

* Enviar fotos
* Enviar recibos
* Compartilhar itens da lista

---

## 8. Usuários, Famílias e Permissões

Cada usuário terá:

* Conta
* Nome
* ID

Uma família terá vários membros.

Cada membro poderá acessar os dados da própria família.

### Segurança

Usuários só devem conseguir acessar e modificar os dados da família à qual pertencem.

As regras de segurança devem ser aplicadas no backend/banco de dados, e não apenas no frontend.

---

## 9. Realtime

O app deve atualizar automaticamente quando outro membro fizer uma alteração.

Exemplo:

```text
Pai marca "Milk" como comprado
        ↓
Banco é atualizado
        ↓
Vini e Mãe recebem a alteração
        ↓
A lista atualiza automaticamente
```

O mesmo conceito será utilizado no chat.

---

## 10. Tecnologia

### Frontend

* React
* TypeScript
* Tailwind CSS

### Backend / Serviços

* Supabase
* PostgreSQL
* Supabase Auth
* Supabase Realtime
* Supabase Storage

### Deploy

* Vercel

---

## 11. Banco de Dados

Possíveis tabelas:

```text
users
families
family_members
shopping_lists
shopping_items
purchases
purchase_items
stores
messages
```

O schema final será definido durante o desenvolvimento.

O banco deve ser projetado desde o início para suportar várias famílias.

---

# 12. Roadmap de Desenvolvimento

O projeto será desenvolvido em 12 etapas.

Cada etapa possui dois objetivos:

1. Construir uma parte real do aplicativo.
2. Aprender os conceitos e tecnologias utilizados naquela parte.

O projeto não deve ser desenvolvido inteiro de uma vez.

Antes de implementar uma funcionalidade importante, o desenvolvedor deve entender o que será feito, por que será feito e como as partes se conectam.

---

## Etapa 1 — Fundação do Projeto

### Objetivo

Criar a base técnica do projeto.

### Tarefas

* Criar projeto Vite
* Configurar React
* Configurar TypeScript
* Configurar Git
* Configurar ESLint
* Configurar formatter
* Limpar o template padrão do Vite
* Criar estrutura inicial de pastas
* Criar uma primeira aplicação React simples

### Conceitos principais

* Vite
* React
* TypeScript
* npm/pnpm
* Git
* ESLint
* Formatter
* Estrutura de projetos React

---

## Etapa 2 — Arquitetura e Planejamento

### Objetivo

Definir como o aplicativo será organizado antes de começar a construir suas funcionalidades principais.

### Tarefas

* Definir telas
* Definir navegação
* Definir fluxos principais
* Definir entidades
* Definir relacionamentos
* Definir responsabilidades do frontend e backend
* Definir organização do código
* Planejar a arquitetura inicial

### Conceitos principais

* SPA
* Componentização
* Arquitetura frontend
* Modelagem de entidades
* Fluxos de aplicação
* Separação de responsabilidades

---

## Etapa 3 — Supabase e PostgreSQL

### Objetivo

Criar o backend e banco de dados da aplicação.

### Tarefas

* Criar projeto no Supabase
* Conectar o frontend ao Supabase
* Criar banco PostgreSQL
* Criar tabelas
* Criar relacionamentos
* Definir chaves primárias
* Definir chaves estrangeiras
* Definir constraints
* Criar estrutura inicial para múltiplas famílias

### Conceitos principais

* Backend as a Service
* PostgreSQL
* SQL
* Banco relacional
* Tabelas
* Relacionamentos
* Primary keys
* Foreign keys
* Constraints

---

## Etapa 4 — Autenticação

### Objetivo

Permitir que cada pessoa tenha sua própria conta.

### Tarefas

* Cadastro
* Login
* Logout
* Sessão
* Recuperação de sessão
* Perfil do usuário
* Proteção das páginas que exigem autenticação

### Conceitos principais

* Autenticação
* Sessões
* Usuários
* Tokens
* Auth
* Estado de autenticação
* Rotas protegidas

---

## Etapa 5 — Famílias e Segurança

### Objetivo

Criar o sistema de famílias e garantir isolamento entre os dados.

### Tarefas

* Criar família
* Entrar em uma família
* Convidar membros
* Listar membros
* Relacionar usuários às famílias
* Definir permissões
* Implementar Row Level Security
* Garantir que uma família nunca consiga acessar os dados de outra

### Conceitos principais

* Multi-tenancy
* Relações entre usuários e famílias
* Autorização
* Permissões
* Row Level Security
* Segurança no backend/banco

---

## Etapa 6 — Lista de Compras

### Objetivo

Construir a primeira funcionalidade principal do produto.

### Tarefas

* Criar lista
* Adicionar item
* Editar item
* Deletar item
* Marcar como comprado
* Desmarcar item
* Definir quantidade
* Exibir itens
* Persistir dados no banco

### Conceitos principais

* CRUD
* Estado no React
* Formulários
* Eventos
* Queries
* Mutations
* Integração frontend/backend

---

## Etapa 7 — Realtime

### Objetivo

Permitir que todos os membros vejam alterações automaticamente.

### Tarefas

* Configurar Supabase Realtime
* Detectar alterações no banco
* Atualizar a lista automaticamente
* Testar alterações entre múltiplos usuários
* Preparar a mesma arquitetura para o chat

### Exemplo

```text
Pai marca "Milk" como comprado
        ↓
Banco é atualizado
        ↓
Supabase Realtime detecta a alteração
        ↓
Vini e Mãe recebem o evento
        ↓
A interface é atualizada
```

### Conceitos principais

* Web realtime
* Eventos
* Subscriptions
* Estado sincronizado
* Comunicação em tempo real

---

## Etapa 8 — Compras

### Objetivo

Permitir registrar compras realizadas.

### Tarefas

* Criar compra
* Selecionar mercado
* Registrar data
* Adicionar produtos
* Registrar quantidades
* Registrar preços
* Calcular total
* Salvar compra no banco
* Relacionar produtos à compra

### Conceitos principais

* Modelagem de dados
* Relacionamentos
* Formulários complexos
* Cálculos
* Transações e consistência de dados
* Histórico

---

## Etapa 9 — Histórico e Recibos

### Objetivo

Armazenar e consultar informações das compras anteriores.

### Tarefas

* Criar histórico de compras
* Listar compras
* Visualizar detalhes
* Upload de recibos
* Utilizar Supabase Storage
* Associar recibo à compra
* Visualizar recibos

### Posteriormente

* OCR
* Extração automática dos dados
* Revisão dos dados antes de salvar

### Conceitos principais

* File upload
* Storage
* URLs
* Arquivos
* Processamento de imagens
* OCR

---

## Etapa 10 — Chat da Família

### Objetivo

Criar comunicação privada entre os membros da família.

### Tarefas

* Criar mensagens
* Enviar mensagens
* Exibir mensagens
* Mostrar remetente
* Mostrar horário
* Salvar mensagens no banco
* Realtime
* Histórico de mensagens

### Posteriormente

* Fotos
* Recibos
* Compartilhamento de itens da lista

### Conceitos principais

* Chat
* Mensagens
* Realtime
* Ordenação
* Paginação
* Estado de conversas

---

## Etapa 11 — Melhorias e Uso Real

### Objetivo

Melhorar o produto com base no uso real.

As funcionalidades devem ser escolhidas com base no que realmente for necessário após a família utilizar o aplicativo.

### Possíveis melhorias

* Categorias de produtos
* Produtos favoritos
* Múltiplas listas
* Vários mercados
* Estatísticas de gastos
* Gastos por mercado
* Gastos por período
* Notificações
* Produtos recorrentes
* Histórico de alterações
* Modo offline
* Melhorias de UX
* Performance
* Acessibilidade

O objetivo desta etapa não é adicionar funcionalidades apenas por adicionar.

As decisões devem ser baseadas em problemas reais encontrados durante o uso.

---

## Etapa 12 — Deploy e Produção

### Objetivo

Colocar o aplicativo em produção e utilizá-lo no mundo real.

### Tarefas

* Preparar aplicação para produção
* Configurar variáveis de ambiente
* Configurar Supabase para produção
* Deploy na Vercel
* Testar aplicação em produção
* Testar com a família
* Coletar feedback
* Corrigir bugs
* Melhorar funcionalidades
* Monitorar problemas

### Conceitos principais

* Deploy
* Produção
* Environment variables
* Build
* CI/CD
* Segurança em produção
* Debugging em produção
* Feedback de usuários

---

## 13. Banco de Dados e Arquitetura

O schema final do banco será definido conforme o projeto evoluir.

A arquitetura deve priorizar:

* Separação clara de responsabilidades
* Segurança
* Escalabilidade razoável
* Manutenibilidade
* Facilidade de entendimento
* Suporte a múltiplas famílias

Possíveis tabelas iniciais:

```text
users
families
family_members
shopping_lists
shopping_items
stores
purchases
purchase_items
messages
```

Novas tabelas poderão ser adicionadas quando novas funcionalidades forem implementadas.

Não criar tabelas, abstrações ou sistemas complexos sem uma necessidade real.

---

## 14. Desenvolvimento com IA

Este projeto também será usado para aprender desenvolvimento full-stack.

Claude pode ser utilizado como:

* Professor
* Pair programmer
* Code reviewer
* Debugger

A IA não deve simplesmente gerar o projeto inteiro sem que o desenvolvedor entenda o código.

Antes de implementar uma funcionalidade importante, o desenvolvedor deve entender:

1. O que está sendo construído
2. Por que isso é necessário
3. Como funciona
4. Quais tecnologias estão envolvidas
5. Como as partes se conectam

Quando apropriado, o desenvolvedor deve tentar implementar a solução antes de receber o código completo da IA.

### Regras de aprendizado

Antes de uma alteração importante, a IA deve explicar:

1. O que pretende fazer
2. Por que isso é necessário
3. Como pretende fazer
4. Por que essa abordagem é adequada
5. Quais outras abordagens relevantes existem

Depois de uma alteração, a IA deve explicar:

1. O que foi alterado
2. Quais arquivos foram criados ou modificados
3. O que cada mudança faz
4. Quais decisões importantes foram tomadas
5. Como verificar ou testar a alteração

Quando existir uma parte importante que o desenvolvedor possa implementar sozinho, a IA deve permitir que ele tente primeiro e oferecer dicas antes de fornecer uma solução completa.

O objetivo não é apenas terminar o aplicativo.

O objetivo é entender o sistema e desenvolver independência suficiente para reconstruir suas partes principais sem depender da IA.

---

## 15. Princípios do Projeto

### Produto real

> Build something families can actually use, while learning how every important part works.

A família do desenvolvedor será o primeiro ambiente de teste.

O produto, porém, deve ser desenvolvido desde o início como um sistema multi-família.

### Aprendizado

O código deve ser entendido, não apenas produzido.

### IA

A IA deve acelerar o desenvolvimento e ensinar o desenvolvedor, não substituir seu entendimento.

### Simplicidade

Não adicionar complexidade sem necessidade.

### Segurança

Dados de uma família nunca devem ser acessíveis por outra família.

### Evolução

As funcionalidades futuras devem ser guiadas pelo uso real do aplicativo e pelos problemas encontrados pelos usuários.
