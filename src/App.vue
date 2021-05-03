<template>
  <div class="h-screen w-full bg-white dark:bg-black" :style="{ backgroundImage: 'url(' + backgroundImage + ')', backgroundRepeat: 'no-repeat' }">

    <ThemeToggler/>
  </div>
</template>

<script>
import { mapGetters } from 'vuex'
import ThemeToggler from './components/ThemeToggler'

export default {
  data() {
    return {
      backgroundImage: null,
    };
  },
  components: {
    ThemeToggler,
  },
  methods: {
  },
  beforeMount() {
    this.$store.dispatch("initTheme")
  },
  computed: {
    ...mapGetters({ theme: 'getTheme' }),
  },
  watch: {
    theme(newTheme) {
      // this.setBackground(newTheme)
      newTheme === 'dark' 
      ? this.backgroundImage = require('@/assets/img/bg-desktop-dark.jpg') 
      : this.backgroundImage = require('@/assets/img/bg-desktop-light.jpg')
      newTheme === 'dark' 
      ? document.documentElement.classList.add('dark')
      : document.documentElement.classList.remove('dark')
    }
  }

}
</script>

