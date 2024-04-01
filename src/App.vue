<template>
  <div class="container">
    <div class="wrapper">
      <Main />
    </div>
    <Back id="render"/>
  </div>
</template>

<script setup>
import Back from '@/components/Back.vue';
import Main from '@/pages/Main.vue';
</script>

<style>

body {
  overflow: hidden;
}

* {
  box-sizing: border-box;
  padding: 0;
  margin: 0;
  outline: none;
  border: none;
  text-decoration: none;
  color: black;
  list-style-type: none;
  font-family: "Montserrat", sans-serif;
  font-optical-sizing: auto;
  font-style: normal;
}

#render {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
}
.container {
  position: relative;
}
.wrapper {
  min-height: 100vh;
  max-height: 100vh;
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  height: 100%;
  width: 100%;
  z-index: 10;
  overflow-y: auto;
  overflow-x: hidden;
  padding-bottom: 150px;
  
}

.img-container {
  width: 200px;
}

.img-container img{
  width: 100%;
  height: auto;
}
</style>