<template>
  <v-app ref="app">
    <v-main>
      <ThemeSwitcher />
    </v-main>
  </v-app>
</template>

<script>
import ThemeSwitcher from './components/ThemeSwitcher';

export default {
  name: 'App',
  components: {
    ThemeSwitcher,
  },
  watch: {
    '$vuetify.theme.isDark'() {
      this.$nextTick(() => {
        const rootStyles = window.getComputedStyle(this.$refs.app.$el)
        console.log('backgroundColor', rootStyles.backgroundColor)
        document.body.style.backgroundColor = rootStyles.backgroundColor
      })
    }
  }
}
</script>
