<template>
  <div id="app">
   <MyHeader />
   <MyMainContent />
   <MyFooter />
  </div>
</template>

<script>
import MyHeader from './components/MyHeader.vue'
import MyMainContent from './components/MyMainContent.vue'
import MyFooter from './components/MyFooter.vue'



export default {
  name: 'App',
  components: {
    MyHeader,
    MyMainContent,
    MyFooter,
  }
}
</script>

<style lang="scss">
@import'~bootstrap/dist/css/bootstrap.css'


</style>
