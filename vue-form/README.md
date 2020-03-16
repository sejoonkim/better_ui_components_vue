# vue-form

## Start Vue Project by creating Form

- App.vue

  - > 1. ctrl + a / cmd + a -> delete
    > 2. type vue -> default.vue
    > 3. Just like React.js, there should be 1 root html element per component

<br/>

- bind data to component, **v-model**

  - > <input _if_="username" _type_="text" _v-model_="username"/>

- vue.config.js

  - stop running eslint

<br/>

### Event controlling

- > v-on:submit.prevent === (event), event.preventDefault();

<br/>

### Login Validation

- Old: check user ID input

  > v-if:"true/false"

<br/>

### Login Validation

- Old: check user ID input

  > v-if:"true/false"

<br/>

- New: dynamically check user ID input

  - Use regex

    ```javascript
    function validateEmail(email) {
      var re = /^(([^<>()\[\]\\.,;:\s@"]+(\.[^<>()\[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
      return re.test(String(email).toLowerCase());
    }
    ```

  - computed:

    - runs whenever data, component is modified

<br/>

- dynamically display user input is correct or not

  - stylesheet only applied to current component

    > <style scoped>

  - CSS syntax

    ```css
    .classA.classB {
      border: 1px solid red;
    }
    ```

  - Vue dynamically change class

    ```javascript
    v-bind:class="{ 'error': !isUsernameValid }"
    ```

<br/>
<br/>

## Project setup

```
npm install
```

### Compiles and hot-reloads for development

```
npm run serve
```

### Compiles and minifies for production

```
npm run build
```

### Run your tests

```
npm run test
```

### Lints and fixes files

```
npm run lint
```

### Customize configuration

See [Configuration Reference](https://cli.vuejs.org/config/).
