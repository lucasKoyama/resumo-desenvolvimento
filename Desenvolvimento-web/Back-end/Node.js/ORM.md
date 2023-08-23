[[Node.js]]
ORM é utilizar javascript para fazer as queries sem tem que ficar escrevendo queries SQL!

| Migration | Cria as tabelas     |
|    ---    |         ---         |
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