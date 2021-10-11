# API Aplicação de posts
Essa API é responsável por retornar dados sobre os posts, realizar operações CRUD e autenticação JWT.

## Endpoints

### GET /api/posts
Esse end point é responsável por retornar todos os posts cadastrados no banco de dados.

#### Parametros 
Nenhum.

#### Respostas
##### OK! 201
Caso essa resposta aconteça você receberá a listagem de posts cadastrados.
Exemplo de reposta:
````
[{"_id":"01","title":"Google and Microsoft are creating a monopoly","content":"Sometimes major shifts happen ","imagePath":"http://server/images/google.png","creator":"01","__v":0}}],"maxPosts":4},
[{"_id":"01","title":"Apple products ","content":"All sort of products have been released ","imagePath":"http://server/images/apple.png","creator":"01","__v":0}}],"maxPosts":4},
[{"_id":"01","title":"Amazon and their self selling stores","content":"This is the new trending on 1st world countries. ","imagePath":"http://server/images/amazon.png","creator":"01","__v":0}}],"maxPosts":4},

````
#### Busca por posts falhou! 500
Caso você receba essa mensagem é por que o servidor não está respondendo.
Motivo: Servidor caiu por algum motivo desconhecido.

Exemplo de resposta : 

````

{
     message: "Fetching posts failed!" 
}

````
### GET /api/posts

#### Parametros 
ID : id do post cadastrado no sistema.


#### Respostas
##### OK! 201
Caso essa resposta aconteça você acessou algum post do servidor.


#### Criação de post falhou! 500
Caso você receba essa mensagem é por que o post que você tentou acessar não foi encontrado ou não existe mais.

Exemplo de resposta : 
````
{
        message: "Fetch post failed!",
}
````

### POST /api/posts
Esse end point é responsável por cadastrar posts no banco de dados.

#### Parametros 
Nenhum.

#### Respostas
##### OK! 201
Caso essa resposta aconteça você cadastrou o post no banco de dados.

#### Criação de post falhou! 500
Caso você receba essa mensagem é por que você não está autenticado (logado) no servidor.
Exemplo de resposta : 
````
{
        message: "Creating a post failed !",
}
````


### PUT /api/posts

#### Parametros 
ID : ID do usuário cadastrado no sistema.

#### Respostas
##### OK! 201
Caso você receba essa mensagem, você atualizou seu post com sucesso.
Exemplo de resposta : 

````

{
     message: "Successfully authorized" 
}

````
#### Criação de post falhou! 500
Caso você receba essa mensagem é por que você não está autenticado (logado) no servidor.
Exemplo de resposta : 
````

{
     message: "not authorized" 
}

````

### DELETE /api/posts

#### Parametros 
ID : ID do post cadastrado no sistema.

#### Respostas
##### OK! 201
Caso você receba essa mensagem, você deletou o post com sucesso.
Exemplo de resposta : 
````

{
     message: "Deleted post" 
}

````
#### Deleção de post falhou! 500
Caso você receba essa mensagem é por que você não está autenticado (logado) no servidor.
Exemplo de resposta : 

````

{
     message: "Not authorized" 
}

````

### POST /api/user/signup
Esse end point é responsável por cadastrar usuários no banco de dados.
#### Parametros 
Nenhum

#### Respostas
##### OK! 201
Exemplo de resposta : 

````
{
    "email": "juliojc.jord@gmail.com",
    "senha": "122334",
}
````
##### Falha no cadastro 500
Caso você receba essa mensagem é por que o e-mail ja foi cadastrado, ou você inseriu uma senha inválida.
Exemplo de resposta : 

````
{
    message: "Invalid user credentials, or e-mail already exists!"
}
````
### POST /api/user/login
Esse end point é responsável por autenticar usuários cadastrados.
#### Parametros 
Nenhum.

#### Respostas
##### OK! 201
Exemplo de resposta : 

````
{
    "email": "juliojc.jord@gmail.com",
    "senha": "122334",
}
````
##### Autenticação falhou! 500
Caso você receba essa mensagem é por que você inseriu a senha incorreta da sua conta, ou seu usuário não existe.

Exemplo de resposta : 
````
{
    message: "Invalid authentication credentials"
}
````
