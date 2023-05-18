<template>
  <div class="main">
    <div class="menu"></div>
    <div class="content">
      <navbar></navbar>
      <products></products>
    </div>
  </div>
</template>

<script>
import Navbar from '@/components/Navbar';
import Products from '@/components/Products.vue';
  export default {
    components:{
    Navbar,
    Products
}
  }
</script>

<style>
@import '@/fonts/fonts.css';
    *{
        margin: 0;
        padding: 0;
        box-sizing: border-box;
    }
    .menu{
      min-width: 229px;
      background-image: radial-gradient(circle at 29% 0, #000, #1c2734 103%);
      background-color: green;
    } 
    .main{
      display: flex;
      background-color: #eeeff1;
      height: 100vh;
    }
    .content{
      margin: 25px;
      width: 100%;
    }
</style>