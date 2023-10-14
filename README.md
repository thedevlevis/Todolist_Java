# Todolist em Java
Esse é um projeto feito no evento da Rocketseat do dia 09/10/2023 a 13/10/2023 para apresentar a linguagem JAVA no backend. 

# Técnológias e dependencias utilizadas

![Java](https://img.shields.io/badge/-Java-333333?style=flat&logo=Java&logoColor=007396)
![Insomnia](https://img.shields.io/badge/-Insomnia-333333?style=flat&logo=insomnia)
![Git](https://img.shields.io/badge/-Git-333333?style=flat&logo=git)
![GitHub](https://img.shields.io/badge/-GitHub-333333?style=flat&logo=github)
![Visual Studio Code](https://img.shields.io/badge/-Visual%20Studio%20Code-333333?style=flat&logo=visual-studio-code&logoColor=007ACC)
![Docker](https://img.shields.io/badge/-Docker-333333?style=flat&logo=docker)

* Spring Boot Web
* Spring Boot DevTools
* Lombok
* H2 database
* Bcrypt 
* Maven

# Deploy no Render.com
Link: https://todolist-java-ffjt.onrender.com - Disponivel até 13/11/2023

# Objetos para os testes

Rotas Publicadas:

<span style="color:#A4EA4F">POST</span> <a style="color:#00C2DF">https://todolist-java-ffjt.onrender.com/users/</a> -> Cria um novo usuario<br>
```json
{
	"username": "John",
	"name": "John Doe",
	"password": "12345"
}
```
### Necessário Autenticação - BASIC AUTH
<span style="color:#bc4ed8">GET</span> <a style="color:#00C2DF">https://todolist-java-ffjt.onrender.com/tasks/</a> -> Lista as tarefas do usuario logado<br>
<span style="color:#A4EA4F">POST</span> <a style="color:#00C2DF">https://todolist-java-ffjt.onrender.com/tasks/</a> -> Cria uma nova tarefa<br>
<span style="color:#fdfd96">PUT</span> <a style="color:#00C2DF">https://todolist-java-ffjt.onrender.com/tasks/</a> -> Atualiza a tarefa<br>
```json
{
	"description": "Descrição da Tarefa",
	"title": "Titulo da Tarefa menor que 50 caracteres",
	"priority": "ALTA",
	"startAt": "2023-10-14T12:30:00",
	"endAt": "2023-10-20T12:30:00"
}
```
# Regras de negócio: 
### Usuario
* No cadastro de usuario o username deve ser único;
* A senha deve ser criptografada antes de armazenar na camada de persistência da aplicação

### Tarefas - Necesserio Autenticação (Basic Auth)
* Rota GET: Somente deve-se retornar as tarefas criadas pelo proprio usuario
* Rota POST: O usuario não pode criar uma tarefa com a data de começo e final da tarefas menor que a data atual
* Rota POST: A data de começo da tarefa não pode ser menor que a data final
* Rota PUT: O usuario somento pode alterar as tarefas que foram criadas por ele mesmo

