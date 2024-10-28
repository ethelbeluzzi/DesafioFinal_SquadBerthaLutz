# DesafioFinal_SquadBerthaLutz
O arquivo original com a base e os modelos foi construído em conjunto pela Equipe 02.

**estrutura de arquivos:**
- `/base`: corresponde ao aplicativo que gerencia as publicações do blog
- `/base/templates/base/`: contém os templates referentes ao blog.
    - `base.html`: é o template base, estendido para `post_list.html`, lista das postagens que fica na raiz do site, e `post_detail.html`.
- `base/templates/registration`: template para a página de cadastro de usuários

**views implementadas:**
- `post_list`: implementada na raiz do site, lista todos os posts publicados, ou seja que a data de publicação não está vazia.
- `post_detail`: mostra os detalhes da publicação numa url separada (`/post/{id}`)
- **comentários**:
    - `post_detail`: gerencia a exibição e adição de comentários em postagens.

**views implementadas que requerem login**
> funções de gerenciamento e edição das postagens, implementadas no front-end.
- `post_new`: cria novas publicações 
- `post_edit`: edita publicações 
- `draft_post_list`: lista as postagens que não foram publicadas
- `post_publish`: botão para publicação das postagens
- `delete_post`: botão para deletar publicação

**login de usuários**
rotas: 
- `/accounts/login/`: página de login para gerenciamento das postagens

**Administração do Django:**
- `/admin`: página de gerenciamento do Django, com acesso ao modelo Postagens.

O modelo Postagens foi registrado na interface de administração do Django, utilizando uma classe personalizada <b>PostagensAdmin</b>, que facilita o gerenciamento das publicações.

A classe PostagensAdmin permite:
Exibir os campos:
- titulo, 
- autor, 
- data_criacao   
- data_publicacao.

Filtrar postagens por:
- data_criacao 
- autor.

Pesquisar por:
- titulo 
- conteudo.

Um superusuário foi criado para permitir acesso à interface administrativa, possibilitando que os administradores gerenciem as postagens com facilidade.

**Adições no front-end:**
- Adicionada barra de pesquisa
- Implementação de "dark mode"
- Design responsivo implementado
- Adicionado diretório de templates em settings.py

### Comentários
- **Modelo `Comentario`**: Foi adicionado um novo modelo para permitir que os usuários comentem nas postagens.
- **View `post_detail`**: Implementada para exibir detalhes da postagem e gerenciar os comentários. Os usuários podem adicionar comentários às postagens.
- **Formulário `ComentarioForm`**: Criado para facilitar a criação de novos comentários, permitindo que os usuários adicionem seu texto de comentário.

### Testes - Banco de Dados
- A conexão com o banco de dados está funcional ao executar os comandos básicos.
- Os modelos gerados correspondem às tabelas no banco, com os relacionamentos (chaves estrangeiras) corretamente configurados.
- As operações de inserção, consulta e atualização de registros foram realizadas sem problemas.



