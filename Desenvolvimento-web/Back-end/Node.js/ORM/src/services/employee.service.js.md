#### Eager Loading
```js
const getById = async (id) => {
  const employee = await Employee.findOne({
    where: { id },
    include: [{
      model: Address, as: 'addresses', attributes: { exclude: ['number'] },
    }],
  });
  return employee;
}
```
#### Lazy Loading
```js
const getById = async (id) => {
  const employee = await Employee.findOne({
    where: { id },
  });
  return employee;
}
```