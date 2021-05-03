<template>
    <button @click="toggleTheme" class="focus:outline-none">
        <img v-if="this.$store.state.theme.theme == 'dark' " class="" src="@/assets/img/icon-moon.svg" alt="dark mode icon">
        <img v-else class="" src="@/assets/img/icon-sun.svg" alt="dark mode icon">
    </button>
</template>

<script>
export default {
  methods: {
    toggleTheme() {
      this.$store.dispatch("toggleTheme");
    },
  },
};
</script>