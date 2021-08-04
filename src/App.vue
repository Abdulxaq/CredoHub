<template>
  <div  id="app">
    <Nav/>


    <router-view/>
  </div>
</template>

<script>
import Nav from './components/nav.vue'
import register from './components/register.vue'
export default {
  name: 'App',
  components:{
    register,
    Nav,
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@100;300;400;500;700;900&display=swap');
*,:after,:before{
  padding: 0;
  margin: 0;
  box-sizing: border-box;
  font-family: 'Roboto', sans-serif;
}
#app{
  height: 3000px;
}
</style>
