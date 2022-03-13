<template>
  <section class="hero hero1 is-primary has-text-centered">
    <div class="hero-body">
      <p class="title">Ninja Reaction Timer</p>
    </div>
  </section>
  <br />
  <section class="hero has-text-centered">
    <div class="hero-body">
      <button @click="toggleModal" class="button is-info">Play</button>
    </div>
  </section>

  <PopUp v-if="showModal" @close="toggleModal" />
</template>
<script>
import PopUp from "./components/PopUp.vue";
export default {
  name: "App",
  components: { PopUp },
  data() {
    return {
      showModal: false,
    };
  },
  methods: {
    toggleModal() {
      console.log(this.showModal);
      this.showModal = !this.showModal;
    },
  },
};
</script>
<style>
.hero1 {
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
}
</style>