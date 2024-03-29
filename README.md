# Starter Code [work in progress]

[Official Material UI Documentation](https://material-ui.com/getting-started/installation/)

Step by step on how I set up and use Material UI. Will mainly be following the official docs.

This repo will have the finished code. This guide was written so you can follow along from scratch.

# Getting Started

Initialize a project with Create react app

```sh
npx create-react-app myApp
```

## Adding Material UI

Here will accompolish 2 things. Installing the core packages and installing Fonts and Icons.

```
npm install --save @material-ui/core

npm install --save @material-ui/icons

npm install --save clsx

npm install --save prop-types

```

<strong>/public/index.html</strong>

###### the preconnect link is for performance increase

```html
<link
  rel="preconnect"
  href="https://fonts.gstatic.com/"
  crossorigin="anonymous"
/>
<link
  rel="stylesheet"
  href="https://fonts.googleapis.com/icon?family=Material+Icons"
/>
```

## Font Icons

```
npm install @material-ui/icons
```

# Code Snippets

> Snippets are good so you don't have to type the same thing every time. Atom and vscode have javascript and react snippets. Or you can create your own.
> These are my custom ones for material ui

### import statments

```javascript
'.source.js':
  'Snippet Name':
    'prefix': 'imc'
    'body': "import $1 from '@material-ui/core/$1';$0"
```

### Stateless Component - rscm

```javascript
import React from 'react';
import PropTypes from 'prop-types';
import withStyles from '@material-ui/core/styles/withStyles';

const styles = theme => ({
  root: {
    flexGrow: 1
  }
});

const App = props => {
  const { classes } = props;

  return (
    <div className={classes.root}>
      <Button variant='contained'>my button</Button>
    </div>
  );
};

App.propTypes = {
  classes: PropTypes.object.isRequired
};

export default withStyles(styles)(App);
```

### Class Component

```javascript
import React, { Component } from 'react';
import PropTypes from 'prop-types';
import withStyles from '@material-ui/core/styles/withStyles';
import Grid from '@material-ui/core/Grid';
import Typography from '@material-ui/core/Typography';

const styles = theme => ({
  root: {
    flexGrow: 1
  }
});

class App extends Component {
  render() {
    const { classes } = this.props;
    return (
      <div className={classes.root}>
        <Grid container justify='center' alignItems='center'>
          <Grid item xs={12}>
            <Typography variant='h4'>Sign In</Typography>
          </Grid>
        </Grid>
      </div>
    );
  }
}

App.propTypes = {
  classes: PropTypes.object.isRequired
};

export default withStyles(styles)(App);
```

---

# How to add snippets to atom

From the top of the menu Atom menu.

```sh
Atom > Snippets
```

then copy and paste this save and exit. Create a new javascript file.

## imc , rscm, rccm

```javascript
'.source.js':
  'Snippet Name':
    'prefix': 'imc'
    'body': "import $1 from '@material-ui/core/$1';$0"
  'reactStatelessMaterial':
    'prefix': 'rscm'
    'body': "import React from 'react';\nimport PropTypes from 'prop-types';\nimport withStyles from '@material-ui/core/styles/withStyles';\n\nconst styles = theme =>({\n\troot: {\n\t\tflexGrow: 1\n\t}\n});\n\nconst ${1:${TM_FILENAME_BASE}} = (props) => {\n\tconst { classes } = props;\n\n\treturn (\n\t\t<div className={classes.root}>\n\t\t\t$0\n\t\t</div>\n\t);\n};\n\n${1:${TM_FILENAME_BASE}}.propTypes = {\n\tclasses: PropTypes.object.isRequired,\n};\n\nexport default withStyles(styles)(${1:${TM_FILENAME_BASE}});"
  'reactclass':
    "prefix": "rccm",
    "body": "import React, { Component } from 'react';\nimport PropTypes from 'prop-types';\nimport withStyles from '@material-ui/core/styles/withStyles';\n\nconst styles = theme =>({\n\troot: {\n\t\tflexGrow: 1\n\t}\n});\n\nclass ${1:${TM_FILENAME_BASE}} extends Component {\n\trender() { \n\t\tconst { classes } = this.props;\n\t\treturn (\n\t\t\t<div className={classes.root}>\n\t\t\t\t$0\n\t\t\t</div>\n\t);\n\t}\n};\n\n${1:${TM_FILENAME_BASE}}.propTypes = {\n\tclasses: PropTypes.object.isRequired,\n};\n\nexport default withStyles(styles)(${1:${TM_FILENAME_BASE}});"
```

then type `imc` then `Tab`. After you are done typing press `Tab` one more time to go to the end of the line
