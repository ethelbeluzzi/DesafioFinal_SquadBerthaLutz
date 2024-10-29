# 📚 Projeto de Blog - Desafio Final Squad Bertha Lutz

Bem-vindo ao projeto de Blog do Squad Bertha Lutz! Este projeto é um sistema de gerenciamento de postagens que permite criar, editar, visualizar, e excluir postagens. Com recursos de modo claro e escuro e um layout intuitivo, o blog é ideal para organizar publicações de forma segura e atraente.

## 🚀 Funcionalidades Principais

- **Visualização de Postagens**: Lista todas as postagens publicadas na página inicial.
- **Detalhes da Postagem**: Exibe o conteúdo completo e os comentários de uma postagem específica.
- **Criar e Editar Postagens**: Usuários autenticados podem criar e editar postagens.
- **Publicação de Rascunhos**: Sistema de rascunhos para postagens não publicadas.
- **Autenticação de Usuário**: Login e controle de acesso para proteger funcionalidades restritas.
- **Modo Claro e Escuro**: Alternância para uma experiência de leitura personalizada.

---

## 📂 Estrutura do Projeto

### Diretórios e Arquivos

- **`/base`**: Contém as views, models, forms e URLs para o funcionamento do blog.
- **`/base/templates`**: Templates HTML com layouts e estilos para o blog:
  - `base.html`: Template base do layout principal.
  - `post_list.html`: Lista de postagens publicadas.
  - `post_detail.html`: Detalhes completos de uma postagem.
  - `post_draft_list.html`: Lista de rascunhos de postagens.
  - `post_edit.html`: Formulário para editar postagens.
  - `login.html`: Formulário de login com verificação de erros.
- **`/static`**: Arquivos de estilo (CSS) para modos claro e escuro.

### Estrutura do Código

- **`models.py`**: Define a estrutura de dados das postagens.
- **`views.py`**: Lida com as requisições e respostas para cada funcionalidade.
- **`urls.py`**: Configura as rotas para cada view.
- **`forms.py`**: Cria formulários de criação e edição de postagens.
- **`settings.py`**: Configurações gerais do projeto Django.

---

## 📜 Descrição dos Arquivos de Template

- **`base.html`**: Layout principal com barra de navegação e alternância para modo claro/escuro.
- **`post_list.html`**: Exibe a lista de postagens publicadas com data e link para detalhes.
- **`post_detail.html`**: Mostra o conteúdo de uma postagem específica com opções de editar, apagar e comentar (para usuários logados).
- **`post_draft_list.html`**: Lista de rascunhos acessível apenas para usuários autenticados.
- **`post_edit.html`**: Formulário para editar uma postagem, com campos para título e conteúdo.
- **`login.html`**: Tela de login com verificação de erro e formulário simples.

### Estilos e Acessibilidade

- **`base.css`**: Arquivo de estilos que define as cores para modo claro e escuro e melhora a acessibilidade para links e botões.

---
