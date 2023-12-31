[[Node.js]]
## O que é ORM?
ORM (Mapeamento Objeto-Relacional) signica mapear objetos os relacionando com tabelas nos [[Banco de Dados|bancos de dados relacionais]]. Em outras palavras é usar linguagem de programação para fazer operações de CRUD em um banco de dados, transformando objetos em tabelas, objetos em linhas de uma tabela, etc.
```js
/* Modelo de um "objeto" que simboliza um usuário, em que as chaves (email e password) são os cabeçalhos de uma tabela de usuários, enquanto que os valores (user@gmail.com e senha) são os dados da tabela */
const objetoUsuario = {
	email: "user@gmail.com",
	password: "senha"
}
```
| email |password|
|---|---|
|user@gmail.com|senha|
#### Sequelize umas das libs mais conhecidas de ORM
|    Nome   |    O que faz?       |
|    ---    |         ---         |
| Migration | Cria as tabelas     |
| Seeders   | Alimenta as tabelas |
| Models    | Faz os CRUDs        |
## Passos
1. Inicie o seu backend `npm init -y`
2. instale o sequelize `npm install -E sequelize@6.3.4`
3. Crie o seu .env para guardar as variáveis de ambiente do seu banco
	```bash
	MYSQL_USER=root
	MYSQL_PASSWORD=senha_mysql
	MYSQL_DATABASE=orm_example
	MYSQL_HOST=localhost
	```
4. Instale o cli do sequelize `npm install -D -E sequelize-cli@6.2.0`
5. Instale sua linguagem SQL `npm install -E mysql2@2.1.0`
6. Entre na pasta src `cd src`
7. Inicie a estrutura do sequelize `npx sequelize-cli init`
8. Volte para a pasta raiz `cd ..`
9. Crie o arquivo [[sequelizerc|.sequelizerc]] que vai falar ao sequelize onde está o arquivo de configuração dele
10. Vá até o arquivo `src/config/config.json` e renomeie o arquivo para [[config.js]] adicionalmente substitua o código dele
11. Modifique o index.js da model para apontar para o arquivo de config.js ao invés de config.json `const config = require(__dirname + '/../config/config.js')[env];`
12. Suba um container SQL 
	`docker container run --name container-mysql -e MYSQL_ROOT_PASSWORD=senha_mysql -d -p 3306:3306 mysql:8.0.29`
13. Crie o banco `env $(cat .env) npx sequelize db:create`
14. Crie os modelos das entidades do seu banco. Exemplo de model [[user.model]]
	*Contém também outros exemplos de models com **relacionamentos 1:1, 1:N e N:N!***
15. Crie as migrations. Exemplo de migration da tabela users [[Desenvolvimento-web/Back-end/Node.js/ORM/src/migrations/timeStamp.users|timeStamp.users]]
	e depois rode elas `npx sequelize db:migrate`
16. Crie as seeders. Exemplo de seeders para a tabela users [[Desenvolvimento-web/Back-end/Node.js/ORM/src/seeders/timeStamp.users|timeStamp.users]]
	e depois rode elas `env $(cat .env) npx sequelize db:seed:all`
17. Crie as funções da camada service utilizando as funções padrões do sequelize para se comunicar com as models. Exemplo de [[employee.service.js|service dos employees]] com eager e lazy loading
18. Crie as funções da camada controller. Exemplo de [[employee.controller.js|controller dos employees]] com opção de carregar lazy ou eager loading
19. 
## Estrutura das pastas e arquivos
- **src**
	- **auth**
		- [[validateToken.js]]
	- **config**
		- [[config.js]]
	- **controllers**
		- [[employee.controller.js]]
	- **migrations**
		- [[Desenvolvimento-web/Back-end/Node.js/ORM/src/migrations/timeStamp.users|timeStamp.users]]
	- **models**
		- [[user.model]]
	- **seeders**
		- [[Desenvolvimento-web/Back-end/Node.js/ORM/src/seeders/timeStamp.users|timeStamps.users]]
	- **services**
		- [[employee.service.js]]
	- [[sequelizerc|.sequelizerc]]