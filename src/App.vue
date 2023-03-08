<template>
  <div>
    <Header />
  </div>
  <div>
    <router-view></router-view>
  </div>
  <div>
    <Footer/>
  </div>
  
</template>

<script>
import Header from './components/Header.vue'
import Footer from './components/Footer.vue'
export default {
  components:{
    Header,
    Footer
  }
}
</script>


<style>
  *{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    background-color: #141519;
    font-family: arial;
  }
</style>