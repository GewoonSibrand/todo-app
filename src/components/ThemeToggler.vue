<template>
    <button 
     @click="toggleTheme"
     class="">
        <img class="" src="@/assets/img/icon-moon.svg" alt="dark mode icon">
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