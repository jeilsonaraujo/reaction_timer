<template>
  <div id="modal-js-example" class="modal is-active" v-if="isShowing">
    <div class="modal-content" @click="closePopUp">
      <div class="boxclick click has-text-centered">
        <br />
        <h1>Click me</h1>
        <br />
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: ["delay"],
  data() {
    return {
      isShowing: false,
      timer: null,
    };
  },
  methods: {
    startTimer() {},
    stopTimer() {},
  },
  mounted() {
    setTimeout(() => {
      this.isShowing = true;
      startTimer();
    }, this.delay);
  },
  methods: {
    closePopUp() {
      this.$emit("close");
    },
  },
};
</script>
<style>
.boxclick {
  background-color: #4de2cc;
  border-radius: 10px;
  color: white;
  font-size: 35px;
}
.modal-content {
  border-radius: 10px;
  background: rgba(255, 255, 255, 0);
  box-shadow: 0 8px 12px 0 rgba(0, 0, 0, 0.2), 0 12px 20px 0 rgba(0, 0, 0, 0.19);
}
</style>