```js
const jwt = require('jsonwebtoken');
const { UserService } = require('../services');

const secret = process.env.JWT_SECRET;

module.exports = async (req, res, next) => {
  const bearerToken = req.header('Authorization');
  if (!bearerToken) {
    return res.status(401).json({ message: 'Token not found' });
  }
  const token = bearerToken.split(' ')[1];
  try {
    const decoded = jwt.verify(token, secret);
    const user = await UserService.getByEmail(decoded.data.email);
    if (user) {
	    req.user = user;
	    return next();
    }
  } catch (err) {
    return res.status(401).json({ message: 'Expired or invalid token' });
  }
};
```