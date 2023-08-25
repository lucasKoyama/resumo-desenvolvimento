```js
const getById = async (req, res) => {
  try {
    const { id } = req.params;
    const employee = await EmployeeService.getById(id);

    if (!employee) {
      return res.status(404).json({ message: 'Pessoa colaboradora não encontrada' });
    }

    if (req.query.includeAddresses === 'true') {
      const addresses = await AddressService.getAllByEmployeeId(id);
      return res.status(200).json({ employee, addresses });
    }

    return res.status(200).json(employee);
  } catch (e) {
    console.log(e);
    res.status(500).json({ message: 'Ocorreu um erro' });
  }
};
```