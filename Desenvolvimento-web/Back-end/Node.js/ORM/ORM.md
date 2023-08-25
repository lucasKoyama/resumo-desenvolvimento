[[Node.js]]
## O que é ORM?
ORM (Mapeamento Objeto-Relacional) signica mapear objetos os relacionando com tabelas nos bancos de dados relacionais. Em outras palavras é usar linguagem de programação para transformar objetos em linhas em uma tabela de um banco de dados relacional 
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
## Passos
## Estrutura das pastas e arquivos

|    Nome   |    O que faz?       |
|    ---    |         ---         |
| Migration | Cria as tabelas     |
| Seeders   | Alimenta as tabelas |
| Models    | Faz os CRUDs        |

```jsx
npm init -y

npm i eslint@6.8.0 eslint-config-airbnb-base@14.2.0 eslint-plugin-import@2.22.1 eslint-config-trybe-backend@1.0.3 -D

.eslintrc.json

{
  "root": true,
  "extends": ["trybe-backend"],
  "rules": {
    "sonarjs/no-duplicate-string": ["error", 5]
  }
}

```
1. criar model
2. criar migration
3. 