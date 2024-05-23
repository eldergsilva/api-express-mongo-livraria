#API para Livraria - documentação



Esta API RESTful permite que você gerencie autores e livros em sua livraria de forma eficiente e automatizada. Desenvolvida com Node.js, Express e MongoDB, a API oferece uma interface simples e intuitiva para realizar diversas operações CRUD (Criar, Ler, Atualizar e Deletar) em seus dados de autores e livros.

Com a API para Livraria, você pode:

* Gerenciar autores:
    Cadastrar novos autores com nome, data de nascimento e nacionalidade.
    Consultar informações de autores existentes, incluindo seus livros publicados.
    Atualizar dados de autores já cadastrados.
    Remover autores da sua livraria.

* Gerenciar livros:
    Cadastrar novos livros com título, autor, editora, número de páginas e gênero.
    Consultar detalhes de livros específicos, incluindo informações do autor.
    Atualizar informações de livros já cadastrados.
    Remover livros da sua livraria.
    Filtrar livros por editora, título, número de páginas e nome do autor.

* Funcionalidades adicionais:

A API retorna respostas em formato JSON, facilitando a integração com diversas aplicações e linguagens de programação.
Os endpoints são protegidos por autenticação, garantindo a segurança dos seus dados.
A documentação completa da API está disponível para consulta, com exemplos de requisições e respostas para cada endpoint.


## Autores

### Listar todos os autores
Endpoint: GET /autores

Descrição: Retorna uma lista com todos os autores cadastrados na livraria.

Exemplo de resposta:

JSON
[
  {
    "_id": "5f2b1a1331654334944a621a",
    "nome": "João Silva",
    "dataNascimento": "1980-01-01",
    "nacionalidade": "Brasil",
    "livros": [
      "5f2b1a1331654334944a621b"
    ]
  },
  {
    "_id": "5f2b1a1331654334944a621c",
    "nome": "Maria Oliveira",
    "dataNascimento": "1990-02-02",
    "nacionalidade": "Portugal",
    "livros": [
      "5f2b1a1331654334944a621d"
    ]
  }
]


### Listar autor por ID
Endpoint: GET /autores/:id

Descrição: Retorna um autor específico a partir do ID informado.

Parâmetros:

:id: ID do autor a ser consultado.
Exemplo de resposta:

JSON
{
  "_id": "5f2b1a1331654334944a621a",
  "nome": "João Silva",
  "dataNascimento": "1980-01-01",
  "nacionalidade": "Brasil",
  "livros": [
    "5f2b1a1331654334944a621b"
  ]
}


### Cadastrar novo autor
Endpoint: POST /autores

Descrição: Cadastra um novo autor na livraria.

Corpo da requisição:

JSON
{
  "nome": "Novo Autor",
  "dataNascimento": "2000-03-03",
  "nacionalidade": "Brasil"
}
Use o código com cuidado.
content_copy
Exemplo de resposta:

JSON
{
  "_id": "5f2b1a1331654334944a621e",
  "nome": "Novo Autor",
  "dataNascimento": "2000-03-03",
  "nacionalidade": "Brasil",
  "livros": []
}


### Atualizar autor existente
Endpoint: PUT /autores/:id

Descrição: Atualiza os dados de um autor existente.

Parâmetros:

:id: ID do autor a ser atualizado.
Corpo da requisição:

JSON
{
  "nome": "João Silva Atualizado",
  "dataNascimento": "1980-01-01",
  "nacionalidade": "Brasil"
}


Exemplo de resposta:

JSON
{
  "message": "Autor atualizado com sucesso"
}
Use o código com cuidado.
content_copy
### Remover autor
Endpoint: DELETE /autores/:id

Descrição: Remove um autor da livraria.

Parâmetros:

:id: ID do autor a ser removido.
Exemplo de resposta:

JSON
{
  "message": "Autor removido com sucesso"
}



## Livros

### Listar todos os livros
Endpoint: GET /livros

Descrição: Retorna uma lista com todos os livros cadastrados na livraria.

Exemplo de resposta:

JSON
[
  {
    "_id": "5f2b1a1331654334944a621b",
    "titulo": "O Senhor dos Anéis",
    "autor": "5f2b1a1331654334944a621a",
    "editora": "Editora LTDA",
    "numeroPaginas": 50
  }
]