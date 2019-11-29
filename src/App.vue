<template>
  <div id="app">
    <router-view/>
    <About></About>
  </div>
</template>

<script>
import  About from './views/About'
export default{
  components:{
    About
  }
}
</script>