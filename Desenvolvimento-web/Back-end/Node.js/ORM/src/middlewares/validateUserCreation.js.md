```js
const validator = require('email-validator');

const invalidDisplayName = (displayName) => !displayName || displayName.length < 8;
const invalidEmail = (email) => !email || !validator.validate(email);
const invalidPassword = (password) => !password || password.length < 6;

module.exports = (req, res, next) => {
  const { displayName, email, password } = req.body;

  if (invalidDisplayName(displayName)) {
    return res.status(400).json({
      message: '"displayName" length must be at least 8 characters long',
    });
  }

  if (invalidPassword(password)) {
    return res.status(400).json({
      message: '"password" length must be at least 6 characters long',
    });
  }
  
  if (invalidEmail(email)) {
    return res.status(400).json({ message: '"email" must be a valid email' });
  }
  
  next();
};
```