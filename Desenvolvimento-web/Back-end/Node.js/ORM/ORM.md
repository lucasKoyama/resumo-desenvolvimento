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
## Estrutura das pastas e arquivos
1. criar model
2. criar migration
3. 