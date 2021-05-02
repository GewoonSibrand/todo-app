<template>
  <ThemeToggler/>
</template>

<script>
import { mapGetters } from 'vuex'
import ThemeToggler from './components/ThemeToggler'

export default {
  components: {
    ThemeToggler,
  },
  beforeMount() {
    this.$store.dispatch("initTheme")
  },
  computed: {
    ...mapGetters({ theme: 'getTheme' }),
  },
  watch: {
    theme(newTheme) {
      newTheme === 'light' 
      ? document.documentElement.classList.remove('dark')
      : document.documentElement.classList.add('dark')
    }
  }

}
</script>

