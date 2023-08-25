```jsx
import React from 'react';
import PropTypes from 'prop-types';
import { connect } from 'react-redux';

class Header extends React.Component {
  render() {
	// email provido ao mapear o estado global para as props
    const { email } = this.props;
    return (
      <header className="header">
        <div className="user-info">
          <h3 data-testid="email-field">{`Email: ${ email }`}</h3>
        </div>
      </header>
    );
  }
}

// mapeando o estado global e passando para as props do componente o email
const mapStateToProps = (state) => ({
  email: state.user.email,
});

Header.propTypes = {
  email: PropTypes.string,
}.isRequired;

/** conectando o redux ao componente com a função que mapea o estado global para as props */
export default connect(mapStateToProps)(Header);
```
