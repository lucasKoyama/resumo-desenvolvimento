- `npm i eslint@6.8.0 eslint-config-trybe-backend@1.0.1 --save-dev --save-exact`
- `touch .eslintignore .eslintrc.json`
```bash
// .eslintignore

node_modules
```
```bash
// .eslintrc.json
{
  "env": {
    "es2020": true
  },
  "extends": "trybe-backend",
  "rules": {
    "sonarjs/no-duplicate-string": ["error", 5]
  }
}
```
  