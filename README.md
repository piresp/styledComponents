# Styled Components

1. Installing styled-components:  

JS:
```
  yarn add styled-components
```
TS:
```
  yarn add styled-components @types/styled-components
```

2. Importing styled-components:  
``` jsx
import styled from 'styled-components';
```

3. Creating a styled component:  
``` jsx
  const Button = styled.button`
  background-color: #f44336;
  color: #ffffff;
  font-size: 16px;
  padding: 10px 20px;
  border-radius: 4px;
  cursor: pointer;
`;
```


4. Nesting styled components:
``` jsx
const Wrapper = styled.div`
  display: flex;
  justify-content: center;
  align-items: center;
`;

const Button = styled.button`
  /* styles */
`;

const StyledButton = () => (
  <Wrapper>
    <Button>Click me</Button>
  </Wrapper>
);
```


5. Using props in styled components:  
``` tsx
const Button = styled.button`
  background-color: ${(props) => (props.primary ? '#f44336' : '#e0e0e0')};
  color: ${(props) => (props.primary ? '#ffffff' : '#000000')};
  /* other styles */
`;

// same but lean
const Button = styled.button`
  background-color: ${({ primary }) => (primary ? '#f44336' : '#e0e0e0')};
  color: ${({ primary }) => (primary ? '#ffffff' : '#000000')};
  /* other styles */
`;

// with typescript

interface ButtonProps {
  primary?: boolean;
}

const Button = styled.button<ButtonProps>`
  background-color: ${({ primary }) => (primary ? '#f44336' : '#e0e0e0')};
  color: ${({ primary }) => (primary ? '#ffffff' : '#000000')};
  /* other styles */
`;
```

6. Extending styled components:
``` jsx
const Button = styled.button`
  /* styles */
`;

const PrimaryButton = styled(Button)`
  background-color: #f44336;
  color: #ffffff;
`;
```


7. Global styles with createGlobalStyle:
``` jsx
import { createGlobalStyle } from 'styled-components';

const GlobalStyle = createGlobalStyle`
  body {
    font-family: 'Arial', sans-serif;
  }
`;

const App = () => (
  <>
    <GlobalStyle />
    {/* Rest of your components */}
  </>
);
```


8. Theming with styled-components:
``` jsx
import { ThemeProvider } from 'styled-components';

const theme = {
  colors: {
    primary: '#f44336',
    secondary: '#3f51b5',
  },
};

const App = () => (
  <ThemeProvider theme={theme}>
    {/* Rest of your components */}
  </ThemeProvider>
);
```

9. Adapting styles with media queries:  
``` jsx
const Button = styled.button`
  /* styles */

  @media (max-width: 768px) {
    /* styles for smaller screens */
  }
`;
```


10. Animations with keyframes:
``` jsx
import styled, { keyframes } from 'styled-components';

const fadeIn = keyframes`
  from {
    opacity: 0;
  }
  
  to {
    opacity: 1;
  }
`;

const FadeInDiv = styled.div`
  animation: ${fadeIn} 1s linear;
`;
```
