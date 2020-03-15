<template>
  <div>
    <form v-on:submit="submitForm">
      <div>
        <label for="username">ID: </label>
        <input if="username" type="text" v-model="username" />
      </div>
      <div>
        <label for="password">PW: </label>
        <input id="password" type="text" v-model="password" />
      </div>
      <button type="submt">Login</button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      username: "",
      password: ""
    };
  },
  methods: {
    submitForm(event) {
      event.preventDefault();
      console.log("submitted");
    }
  }
};
</script>

<style></style>
