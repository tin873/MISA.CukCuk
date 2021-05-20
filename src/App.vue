<template>
  <div id="app">
    <BodyLeft />
    <BodyRight />
  </div>
</template>

<script>
import BodyLeft from './components/BodyLeft.vue'
import BodyRight from './components/BodyRight.vue'

export default {
  name: 'App',
  components: {
    BodyLeft,
    BodyRight
  }
}
</script>
<style>
  @import './assets/css/common/main.css';
  @import './assets/css/common/layout.css';
</style>
