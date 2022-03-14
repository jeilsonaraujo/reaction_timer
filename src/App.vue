<template>
  <section class="hero hero1 is-primary has-text-centered">
    <div class="hero-body">
      <p class="title">Ninja Reaction Timer</p>
    </div>
  </section>
  <br />
  <section class="hero has-text-centered">
    <div class="hero-body">
      <button @click="playGame" :disabled="isPlayng" class="button is-info">
        Play
      </button>
    </div>
  </section>
  <Results />
  <PopUp v-if="isPlayng" @close="toggleModal" :delay="this.delay" />
</template>
<script>
import PopUp from "./components/PopUp.vue";
import Results from "./components/Results.vue";
export default {
  name: "App",
  components: { PopUp, Results },
  data() {
    return {
      isPlayng: false,
      delay: null,
    };
  },
  methods: {
    toggleModal() {
      this.isPlayng = !this.isPlayng;
    },
    playGame() {
      this.delay = 200 + Math.random() * 2000;
      this.isPlayng = true;
    },
  },
};
</script>
<style>
.hero1 {
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
}
</style>