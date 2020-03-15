<template>
  <div>
    <form v-on:submit.prevent="submitForm">
      <div>
        <label for="username">ID:</label>
        <input if="username" type="text" v-model="username" />
      </div>
      <div>
        <label for="password">PW:</label>
        <input id="password" type="text" v-model="password" />
      </div>
      <button type="submt">Login</button>
    </form>
    <p v-if="isError">ID error: Check your ID.</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      username: "",
      password: "",
      isError: false
    };
  },
  methods: {
    submitForm() {
      this.isError = true;
      //this.initForm();
    },
    initForm() {
      this.username = "";
      this.password = "";
    }
  }
};
</script>

<style></style>
