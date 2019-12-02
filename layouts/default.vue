<template>
  <div>
    <main-menu/>
    <slider-menu />
    <nuxt />
    <main-footer/>
  </div>
</template>
<script>
import MainMenu from '@/components/MainMenu.vue'
import MainFooter from '@/components/MainFooter.vue'
import SliderMenu from '@/components/SliderMenu.vue'

export default {
  components: {
    MainMenu,
    MainFooter,
    SliderMenu
  }
  
}
</script>
<style>
html {
  font-family: 'Source Sans Pro', -apple-system, BlinkMacSystemFont, 'Segoe UI',
    Roboto, 'Helvetica Neue', Arial, sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

*,
*:before,
*:after {
  box-sizing: border-box;
  margin: 0;
}

</style>
