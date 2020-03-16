<template>
  <div class="toast" v-bind:class="{'animation' : open }">Login Completed</div>
</template>

<script>
let timer;

export default {
  props: ["open"],
  data() {
    return {};
  },
  watch: {
    open(newValue) {
      if (newValue) {
        console.log("open ToastPopup");
        clearTimeout(timer);
        timer = setTimeout(() => this.$emit("close"), 2000);
      }
    }
  }
};
</script>

<style scoped>
.toast {
  width: 200px;
  height: 40px;
  background-color: black;
  color: white;
  display: flex;
  justify-content: center;
  align-items: center;
  position: fixed;
  bottom: -5%;
  left: 5%;
  transition: bottom 0.5s linear;
}
.animation {
  bottom: 5%;
}
</style>