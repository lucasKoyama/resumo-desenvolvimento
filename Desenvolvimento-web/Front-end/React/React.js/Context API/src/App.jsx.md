```jsx
import ThemeProvider from './context/ThemeProvider';
import Header from './components/Header';
import './style.css';

export default function App() {
  return (
    <ThemeProvider>
      <Header />
    </ThemeProvider>
  );
}
```