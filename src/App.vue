<template>
  <div id="app">
    <router-view/>
  </div>
</template>
<script>

export default{
  
}
</script>

<style lang="scss">
#app {
  background: #6066D0 70%;
  min-height: 100vh;
}
@media only screen and (min-width: 1024px){
  #app{
    min-height: 120vh;
  }
}

</style>
