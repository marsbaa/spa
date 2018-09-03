<template>
  <div id="app">
    <StickyHeader />
    <Carousel :sm=1 :lg=3 />
    <Blank />
    <Blank />
  </div>
</template>

<script>
import StickyHeader from './components/StickyHeader'
import Carousel from './components/Carousel'
import Blank from './components/Blank'

export default {
  name: 'app',
  components: {
    StickyHeader,
    Carousel,
    Blank
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
</style>
