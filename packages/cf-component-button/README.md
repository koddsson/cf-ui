Button in a fela theme provider example:

```
const { createRenderer } = require('cf-style-provider');
const { ThemeProvider } = require('cf-style-container');
const { Provider } = require('react-fela');
const { variables } = require('cf-style-const');

const fontNode = document.querySelector('#fela-fonts');
const renderer = createRenderer({ fontNode });

<Provider renderer={renderer} mountNode={fontNode}>
  <ThemeProvider theme={variables}>
    <Button type="primary" onClick={() => console.log('clicked')}>
      Hello world
    </Button>
  </ThemeProvider>
</Provider>
```

Button in a fela style provider example:

```
const { StyleProvider } = require('cf-style-provider');
const { applyTheme } = require('cf-style-container');
const ButtonTheme = require('./src/ButtonTheme').default;
const StyledButton = applyTheme(Button, ButtonTheme);

const cssNode = document.querySelector('#fela-style');
const fontNode = document.querySelector('#fela-fonts');

<StyleProvider
  cssNode={cssNode}
  fontNode={fontNode}
  dev={true}
  selectorPrefix="cf-"
>
  <StyledButton type="primary" onClick={() => console.log('clicked')}>
    Hello world
  </StyledButton>
</StyleProvider>
```
