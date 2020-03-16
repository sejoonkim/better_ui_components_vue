<template>
  <div>
    <form v-on:submit.prevent="submitForm">
      <div>
        <label for="username">ID:</label>
        <input
          if="username"
          type="text"
          v-model="username"
          class="username-input"
          v-bind:class="{ 'error': !isUsernameValid }"
        />
      </div>
      <div>
        <label for="password">PW:</label>
        <input id="password" type="text" v-model="password" />
      </div>
      <button v-bind:disabled="!isUsernameValid" type="submit">Login</button>
    </form>
    <p v-if="!isUsernameValid">ID error: Check your ID.</p>
    <p v-if="isUsernameValid">ID format is correct.</p>
  </div>
</template>

<script>
function validateEmail(email) {
  var re = /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
  return re.test(String(email).toLowerCase());
}

export default {
  data() {
    return {
      username: "",
      password: "",
      isError: false
    };
  },
  computed: {
    isUsernameValid() {
      return validateEmail(this.username);
    }
  },
  methods: {
    submitForm() {
      //this.isError = true;
      //this.initForm();
    },
    initForm() {
      this.username = "";
      this.password = "";
    }
  }
};
</script>

<style scoped>
.username-input {
  outline: none;
}
.username-input.error {
  border: 1px solid red;
}
</style>
