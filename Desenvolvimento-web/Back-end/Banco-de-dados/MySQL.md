MySQL é um sistema de gerenciamento de [[Banco de Dados]] relacional (RDBMS) de código aberto. Em termos mais simples, ele é um gerente dos CRUDs feitos em um banco de dados em que as tabelas podem se relacionar.

Antes de usar comandos UPDATE e DELETE desabilite o safe-update que exige que selecione algo por ID

```sql
SET SQL_SAFE_UPDATES = 0;
```