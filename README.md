# Vue Simple Alert

[![version](https://img.shields.io/npm/v/vue3-simple-alert)](https://www.npmjs.com/package/vue3-simple-alert)
[![Vue.js version](https://badgen.net/badge/vue.js/3.x)](https://vuejs.org)
[![total downloads](https://img.shields.io/npm/dt/vue3-simple-alert)](https://www.npmjs.com/package/vue3-simple-alert)
[![downloads](https://img.shields.io/npm/dw/vue3-simple-alert)](https://www.npmjs.com/package/vue3-simple-alert)
[![license](https://img.shields.io/npm/l/vue3-simple-alert)](LICENSE)

Simple _**alert()**_, _**confirm()**_, _**prompt()**_ for Vue.js version 3, using sweetalert2.

## Origin project

Simple update of https://www.npmjs.com/package/vue-simple-alert to vue3

## Features

- Provides simple _alert()_, _confirm()_, _prompt()_ like DOM Window methods.
- Based on sweetalert2.
- Installed as a Vue.js plugin.
- Promise based API.
- Support typescript.

## Install

```bash
npm i vue3-simple-alert
```

## Basic Usage

### install plugin

```javascript
// main.js
import { createApp } from "vue";
import VueSimpleAlert from "vue-simple-alert";

const app = createApp({})

app.use(VueSimpleAlert);
```

### Alert

```javascript
// in any component

this.$alert("Hello Vue Simple Alert.");
```

### Confirm

```javascript
// in any component

this.$confirm("Are you sure?").then(() => {
  //do something...
});
```

### Prompt

```javascript
// in any component

this.$prompt("Input your name").then(text => {
  // do somthing with text
});
```

## Advanced Usage

### Global options

Global options can be set when initialize plugin. Refer to [sweetalert2 documentation](https://sweetalert2.github.io/#configuration)

```javascript
// main.js
import { createApp } from "vue";
import VueSimpleAlert from "vue-simple-alert";

const app = createApp({})

app.use(VueSimpleAlert, { reverseButtons: true });
```

## API

### alert(message?, title?, type?, options?)

The _alert()_ method displays an alert box with a specified message and an OK button.

- message: string

> Optional. Specifies the text to display in the alert box

- title: string

> Optional. Specifies title of the alert box

- type: 'success' | 'error' | 'warning' | 'info' | 'question'

> Optional. Specifies icon type.

- options: SweetAlertOptions

> Optional. Advanced options. Refer to [sweetalert2 documentation](https://sweetalert2.github.io/#configuration).

- returns: Promise\<boolean\>

> Will be resolved with true when alert box closed.

### confirm(message?, title?, type?, options?)

The confirm() method displays a dialog box with a specified message, along with an OK and a Cancel button.

- message: string

> Optional. Specifies the text to display in the confirm box

- title: string

> Optional. Specifies title of the confirm box

- type: 'success' | 'error' | 'warning' | 'info' | 'question'

> Optional. Specifies icon type.

- options: SweetAlertOptions

> Optional. Advanced options. Refer to [sweetalert2 documentation](https://sweetalert2.github.io/#configuration).

- returns: Promise\<boolean\>

> Will be resolved when OK button clicked. If confirm box closed by any other reason, this promise will be rejected.

### prompt(message, defaultText?, title?, type?, options?)

The prompt() method displays a dialog box that prompts the user for input.

- message: string

> Required. Specifies the text to display in the dialog box

- defaultText: string

> Optional. The default input text

- title: string

> Optional. Specifies title of the confirm box

- type: 'success' | 'error' | 'warning' | 'info' | 'question'

> Optional. Specifies icon type.

- options: SweetAlertOptions

> Optional. Advanced options. Refer to [sweetalert2 documentation](https://sweetalert2.github.io/#configuration).

- returns: Promise\<string\>

> Will be resolved with input text when OK button clicked. If the user clicks OK without entering any text, promise will be resolved with an empty string. If dialog box closed by any other reason, this promise will be rejected.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details
