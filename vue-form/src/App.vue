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
        <input v-bind:type="passwordFieldType" v-model="password" />
        <button type="password" @click="switchVisibility">show/hide</button>
      </div>
      <button v-bind:disabled="!isUsernameValid" type="submit">Login</button>
    </form>
    <p v-if="!isUsernameValid">ID error: Check your ID.</p>
    <p v-if="isUsernameValid">ID format is correct.</p>
  </div>
</template>

<script>
//import New from "@/components/New.vue";
function validateEmail(email) {
  var re = /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
  return re.test(String(email).toLowerCase());
}

export default {
  data() {
    return {
      username: "",
      passwordFieldType: "password",
      password: "",
      isError: false,
      isSuccess: false
    };
  },
  computed: {
    isUsernameValid() {
      return validateEmail(this.username);
    }
  },
  methods: {
    submitForm() {
      this.isSuccess = true;
      //this.isError = true;
      //this.initForm();
    },
    initForm() {
      this.username = "";
      this.password = "";
    },
    switchVisibility() {
      this.passwordFieldType =
        this.passwordFieldType === "password" ? "text" : "password";
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
