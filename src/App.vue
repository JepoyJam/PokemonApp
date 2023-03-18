<template>
<video autoplay loop muted class="video"> 
    <source src="./assets/background-live-wallpaper.mp4" type="video/webm"/>
    <source src="./assets/background-live-wallpaper.mp4" type="video/mp4"/>
  </video>  
  <div>
    <Header />
    <Layout>
      <!-- router view component will be rendered in the <slot /> inside Layout component -->
      <RouterView />
    </Layout>
  </div>
</template>

<script setup>
import { defineAsyncComponent } from "vue";
import { RouterView } from "vue-router";
// lazy load the Header component
const Header = defineAsyncComponent(() => import("./components/Header.vue"));
// lazy load the Layout component
const Layout = defineAsyncComponent(() => import("./components/Layout.vue"));
</script>

<style scoped>
video{
z-index: -1000;
margin-top: 410px;
margin-left: 720px;
width: 100vw;
height: 100vh;
position: fixed;
-webkit-transform: translate(-50%, -50%);
-moz-transform: translate(-50%, -50%);
-ms-transform: translate(-50%, -50%);
transform: translate(-50%, -50%);
object-fit: cover;
}
</style>
