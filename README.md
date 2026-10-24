# 🧠 Segundo Cérebro — Backend Básico com NotebookLM

## Objetivo

> **Entender como uma API funciona por dentro, a estrutura básica de um projeto backend e a manutenção de dependências, para conseguir lidar melhor com projetos backend.**

---

## 📚 Fontes

### Videoaulas (Curso de FastAPI — Hashtag Programação)

| # | Aula | Tema |
|---|------|------|
| 01 | Apresentação do Projeto | Visão geral do projeto backend |
| 02 | Requisições e Roteamento da API | Como as requisições chegam e são direcionadas |
| 03 | Banco de Dados, Modelos e Migrações | Estrutura de dados e versionamento do banco |
| 04 | Criar conta de usuário, Schemas e Criptografia | Modelagem de dados e segurança básica |
| 05 | Criar Pedidos e Fazer Login | Fluxo de autenticação e operações CRUD |
| 06 | Autenticação, OAuth2 e JWT Tokens | Protocolos de autenticação |
| 07 | Bloqueio de Endpoints para Usuários Autenticados | Proteção de rotas |
| 08 | Níveis de Acesso e Lazyloaded do Banco de Dados | Controle de permissões e otimização de consultas |
| 09 | Adicionar Item em Pedido e Relationship em Models | Relacionamentos entre entidades |
| 10 | Finalização e Schemas para respostas de endpoints | Padronização de respostas da API |

### Artigos e Documentações Web

| Fonte | Tipo |
|-------|------|
| Autenticação Segura com JWT em React e Node.js — Hashtag Treinamentos | Artigo |
| Desenvolvimento backend com Python: guia completo para iniciantes — DataCamp | Tutorial |
| GitHub REST API documentation — GitHub | Documentação oficial |
| PostgreSQL: About — PostgreSQL.org | Documentação oficial |

### Livros e Materiais em PDF

| Título | Autor / Editora |
|--------|-----------------|
| Introdução a Docker | Insight Data Science Lab / UFC |
| Containers com Docker: Do desenvolvimento à produção | Daniel Romero — Casa do Código |
| PostgreSQL: Banco de dados para aplicações web modernas | Vinícius Carvalho — Casa do Código |

### Por que confio nessas fontes?

As fontes foram selecionadas com base nos seguintes critérios: os autores têm experiência prática com as tecnologias abordadas, todo o conteúdo inclui exemplos de código e demonstrações, e as documentações oficiais (GitHub, PostgreSQL) são referências primárias mantidas pelas próprias equipes dos projetos. O curso de FastAPI da Hashtag Programação foi escolhido por cobrir um projeto completo do zero, permitindo entender a conexão entre os componentes.

---

## 🤖 Diretriz de comportamento do Notebook

O notebook possui uma **nota pessoal** com orientações de ensino e diretrizes pedagógicas em Python, que guia o tom e o formato das respostas. A instrução orienta o notebook a atuar como um professor de programação, respondendo com base nas fontes carregadas e citando de qual fonte veio cada informação.

---

## ❓ Perguntas e Respostas

### Pergunta 1: Como fazer para entender a documentação de um backend básico?

**Resposta:** Para compreender a documentação de um backend básico, é fundamental dominar alguns conceitos essenciais que descrevem como o servidor disponibiliza, processa e responde às informações.

**1. Identificar as Rotas (Endpoints) e os Verbos HTTP**
- **Endpoints (Rotas):** Caminhos de URL definidos após o domínio principal (como `/pedidos` ou `/auth/login`) que direcionam a requisição para um recurso específico.
- **Verbos HTTP (Métodos):** Indicam a ação que a requisição pretende realizar:
  - **GET** — Solicita a leitura ou busca de informações.
  - **POST** — Envia dados ao servidor para criar um novo registro ou realizar ações como login.
  - **PUT / PATCH** — Atualiza ou edita registros existentes.
  - **DELETE** — Remove registros do sistema.

**2. Compreender os Dados de Entrada (Requisição)**
- **Parâmetros de Rota (Path Parameters):** Valores inseridos diretamente no caminho da URL (ex.: `/pedidos/cancelar/{id}`).
- **Corpo da Requisição (Request Body):** Dados enviados em formato JSON, seguindo uma estrutura padronizada chamada Schema (Esquema), que indica campos obrigatórios e tipos de dados aceitos.
- **Cabeçalhos (Headers):** Informações adicionais de contexto. Em rotas protegidas, exige o cabeçalho `Authorization` no formato `Bearer <token>`.

**Fonte(s):** Videoaulas 01, 02, 05, 06 e documentação GitHub REST API.

---

### Pergunta 2: Como funciona o token JWT?

**Resposta:** O JWT (JSON Web Token) é um padrão aberto (RFC 7519) utilizado para transmitir informações de forma segura entre cliente e servidor. Ele armazena dados codificados em formato JSON com uma assinatura digital que garante que as informações não foram alteradas. Funciona de maneira *stateless* — o servidor não precisa armazenar sessões ativas em memória ou banco de dados.

A estrutura de um token JWT é dividida em três partes separadas por pontos:

- **Header (cabeçalho):** contém o tipo do token e o algoritmo de criptografia utilizado para a assinatura.
- **Payload (dados):** carrega informações do usuário e da sessão, como ID, e-mail e data de expiração.
- **Signature (assinatura):** valida a autenticidade e a integridade do token por meio de uma chave secreta mantida no servidor.

No fluxo de autenticação, o cliente envia suas credenciais no login e o servidor valida os dados para gerar e retornar o token. O cliente armazena esse token e o envia no cabeçalho `Authorization` com o prefixo `Bearer` em todas as requisições para rotas protegidas. O backend verifica a assinatura com sua chave secreta e libera o acesso caso o token seja autêntico e válido.

**Fonte(s):** "Autenticação Segura com JWT em React e Node.js" (Hashtag Treinamentos) e Videoaulas 01 e 06.

---

### Pergunta 3: Como proteger rotas no backend?

**Resposta:** A proteção de rotas no backend é realizada exigindo que o cliente envie um token válido a cada requisição feita para recursos privados. O token é transmitido no cabeçalho HTTP `Authorization` utilizando o formato `Bearer <token>`.

**Fonte(s):** Videoaulas 06 e 07 e "Autenticação Segura com JWT em React e Node.js" (Hashtag Treinamentos).

---

### Pergunta 4: Quais fontes eu direcionei ao notebook?

**Resposta:** As fontes disponibilizadas totalizam **17 fontes principais** (videoaulas, tutoriais web e livros em PDF), além de 1 nota pessoal:

**Videoaulas (Curso de FastAPI — Hashtag Programação):**
1. Aula 01: Apresentação do Projeto
2. Aula 02: Requisições e Roteamento da API
3. Aula 03: Banco de Dados, Modelos e Migrações
4. Aula 04: Criar conta de usuário, Schemas e Criptografia
5. Aula 05: Criar Pedidos e Fazer Login
6. Aula 06: Autenticação, OAuth2 e JWT Tokens
7. Aula 07: Bloqueio de Endpoints para Usuários Autenticados
8. Aula 08: Níveis de Acesso e Lazyloaded do Banco de Dados
9. Aula 09: Adicionar Item em Pedido e Relationship em Models
10. Aula 10: Finalização e Schemas para respostas de endpoints

**Artigos e Documentações Web:**
- "Autenticação Segura com JWT em React e Node.js" (Hashtag Treinamentos)
- "Desenvolvimento backend com Python: guia completo para iniciantes" (DataCamp)
- "GitHub REST API documentation" (GitHub)
- "PostgreSQL: About" (PostgreSQL.org)

**Livros e Materiais em PDF:**
- "Introdução a Docker" (Insight Lab / UFC)
- "Containers com Docker: Do desenvolvimento à produção" (Casa do Código)
- "PostgreSQL: Banco de dados para aplicações web modernas" (Casa do Código)

**Nota Pessoal:**
- Nota com orientações de ensino e diretrizes pedagógicas em Python.

**Fonte(s):** Fontes e notas selecionadas no Notebook.

---

### Pergunta 5: Como funciona o refresh token na prática?

**Resposta:** O *refresh token* é um mecanismo utilizado para renovar o acesso de um usuário sem obrigá-lo a informar suas credenciais constantemente. Na arquitetura com duplo token, o *access token* possui um tempo de vida curto (como 15 a 30 minutos) e é enviado em cada requisição privada. Por outro lado, o *refresh token* tem uma validade mais extensa (como 7 dias) e serve unicamente para emitir novos *access tokens* quando o anterior expira.

Durante o login, o servidor valida a senha e retorna ambos os tokens na mesma resposta. O cliente guarda o *access token* para uso imediato e armazena o *refresh token* de forma protegida. Quando o *access token* expira, a API retorna um erro de não autorizado e o cliente faz uma chamada automática para o endpoint de renovação (como `/refresh`) enviando o *refresh token*. O servidor valida o *refresh token*, extrai a identificação do usuário e emite um novo *access token* de vida curta. Se o *refresh token* também estiver expirado ou for inválido, a renovação é recusada e o usuário deve fazer login novamente com e-mail e senha.

**Fonte(s):** "Autenticação Segura com JWT em React e Node.js" (Hashtag Treinamentos) e Videoaulas 01, 05, 06 e 07.

---

## 🔗 Notebook

[Abrir no Google NotebookLM](https://notebook.google.com/notebook/1e67c495-0942-488c-89ae-b761d6e3be11)

---

## 📋 Critérios de seleção de fontes

Antes de adicionar qualquer nova fonte, passe por este checklist:

| ✅ | Pergunta |
|----|----------|
| ☐ | Fala sobre API, estrutura de projeto ou dependências? |
| ☐ | O autor trabalha com isso na prática? |
| ☐ | Tem exemplo prático (código, demonstração)? |
| ☐ | Foi publicado nos últimos 2–3 anos? |
| ☐ | Eu entendi pelo menos 70% do conteúdo? |
