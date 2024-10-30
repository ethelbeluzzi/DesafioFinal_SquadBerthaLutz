# 📚 Projeto de Blog - Desafio Final Squad Bertha Lutz

Bem-vindo ao projeto de Blog do Squad Bertha Lutz! Este projeto é um sistema de gerenciamento de postagens que permite criar, editar, visualizar, e excluir postagens. Com recursos de modo claro e escuro e um layout intuitivo, o blog é ideal para organizar publicações de forma segura e atraente.

## 🚀 Funcionalidades Principais

- **Visualização de Postagens**: Lista todas as postagens publicadas na página inicial.
- **Detalhes da Postagem**: Exibe o conteúdo completo e os comentários de uma postagem específica.
- **Criar e Editar Postagens**: Usuários autenticados podem criar e editar postagens.
- **Publicação de Rascunhos**: Sistema de rascunhos para postagens não publicadas.
- **Autenticação de Usuário**: Login e controle de acesso para proteger funcionalidades restritas.
- **Modo Claro e Escuro**: Alternância para uma experiência de leitura personalizada.
- **Sistema de Comentários**: Permite a interação entre usuários

---

## 📂 Estrutura do Projeto

### Diretórios e Arquivos

- **`/base`**: Contém as views, models, forms e URLs para o funcionamento do blog.
- **`/base/templates`**: Templates HTML com layouts e estilos para o blog:
- **`/static`**: Arquivos de estilo (CSS) para modos claro e escuro.

### Estrutura do Código

- **`base/admin.py`**: Classe de administração do Django formaliza como os objetos do modelo `Postagem` são exibidos no painel administrativo. As opções `list_display`, `list_filter` e `search_filds` configuram como as postagens são listada, filtradas e pesquisadas.
- **`base/models.py`**: Define dois modelos `Postagens`, que representa uma postagem do blog, com atributos como título, conteúdo, data de postagem, e o método `publish` para publicar a postage, interessante notar que o campo `data_publicação` pode ser nulo, mais sobre isso em `base/views.py` e `Comentario`, que representa um comentário associado a uma postagem, e seu relacionamento com a classe `Postagens` . O diagrama abaixo explica as classes e as relações entre elas:
```
classDiagram
  class Postagem {
    titulo: string
    conteudo: text
    data_publicacao: DateTime (Nullable)
    data_criacao: DateTime
    autor: User
    publish()
    __str__()
  }

  class Comentario {
    postagem: Postagem {relationName="comentarios"}
    autor: User
    texto: text
    data_criacao: DateTime
    __str__()
  }

  Postagem <->|autor| User
  Comentario <->|autor| User
  Postagem <-|postagem| Comentario
```

- **`base/views.py`**: Lida com as requisições e respostas para cada funcionalidade:
	- `post_list`: exibe uma lista de postagens já publicadas;
	- `post_detail`: exibe os detalhes de uma postagem específica e permite adicionar comentários;
	- `post_new`: cria uma nova postagem sua chave estrangeira `<pk>`. (requer que o usuário esteja logado usando o decorador do Django `@login_required`);
	- `post_edit`: edita uma postagem existente (requer login);
	- `post_draft_list`: exibe uma lista de posts ainda não publicados (requer login);
	- `post_publish`: salva a postagem sem publicar (requer login);
	- `post_remove`: remove uma postagem (requer login).
	 
- **`base/urls.py`**: Configura as rotas para as funcionalidades de `base/views.py`
	- ``: `post_list`;
	- `post/<int:pk>`: `post_detail`;
	- `post/new`:`post_new`;
	- `post/<int:pk>`: `post_edit`
	- `drafts/`: `post_draft_list`;
	- `post/<int:pk>/publish/`: `post_publish`;
	- `post/<int:pk>/remove/`: `post_remove`.
	
- **`forms.py`**: Cria formulários de criação e edição de postagens e os valida.

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
