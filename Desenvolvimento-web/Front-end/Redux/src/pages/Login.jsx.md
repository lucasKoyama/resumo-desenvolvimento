```jsx
import React from 'react';
import { PropTypes } from 'prop-types';
import { connect } from 'react-redux';
import { userLoginData } from '../redux/actions';

class Login extends React.Component {
  state = {
    email: '',
    password: '',
  };

  handleChange = ({ target }) => this.setState({ [target.name]: target.value });

  handleLogin = () => {
	// dispatch e history passados por meio do connect sendo pego via props
    const { dispatch, history } = this.props;
    const { email } = this.state;
    // despachando os dados de login com a função criada nas actions
    dispatch(userLoginData(email));
    history.push('/carteira');
  };

  render() {
    const { email, password } = this.state;
    const emailValidation = /^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$/;
    const passValid = 6;
    return (
      <section className="login-section">
        <div className="user-login">
          <p className="title">Faça seu login</p>
          <label htmlFor="user-email">
            Email:
            <input
              label="Email"
              type="text"
              data-testid="email-input"
              name="email"
              id="user-email"
              value={ email }
              onChange={ this.handleChange }
            />
          </label>
          <label htmlFor="user-password">
            Senha:
            <input
              label="Senha"
              type="password"
              data-testid="password-input"
              name="password"
              id="user-password"
              value={ password }
              onChange={ this.handleChange }
            />
          </label>
          <button
            disabled={ !(emailValidation.test(email) && password.length >= passValid) }
            onClick={ () => this.handleLogin() }
          >
            Entrar
          </button>
        </div>
      </section>
    );
  }
}

Login.propTypes = {
  history: PropTypes.objectOf({}),
  dispatch: PropTypes.func,
}.isRequired;

/* conectando o redux ao componente para que ele tenha acesso as funções de dispatch e history do redux */
export default connect()(Login);
```
