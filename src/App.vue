<script>
import yghHeader from './components/yghHeader.vue'
import yghMain from './components/yghMain.vue'

export default {
  components: {
    yghHeader,
    yghMain,
  }
}
</script>

<template>
  <yghHeader />
  <yghMain />
</template>

<style lang="scss">
@use './style/main.scss';
</style>
