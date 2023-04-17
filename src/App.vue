<template>
  <Nav />
  <router-view/>
</template>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Ubuntu:ital,wght@0,300;0,400;0,500;0,700;1,300;1,400;1,500;1,700&display=swap');
  * {
    font-family: 'Ubuntu', sans-serif;
  }
  body {
    background-color: #F5F5F5;
  }
</style>

<script>
import Nav from "@/components/Nav";
export default {
  components: {Nav}
}
</script>