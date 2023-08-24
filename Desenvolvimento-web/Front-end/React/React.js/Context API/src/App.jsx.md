```jsx
import ThemeProvider from './context/ThemeProvider';
import Header from './components/Header';

export default function App() {
  return (
    <ThemeProvider>
      <Header />
    </ThemeProvider>
  );
}
```