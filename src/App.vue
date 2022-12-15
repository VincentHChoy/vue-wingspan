<script setup>
import HelloWorld from "./components/HelloWorld.vue";
import TheWelcome from "./components/TheWelcome.vue";
import Resources from "./components/Resources.vue";
</script>

<template>
  <main class="background wrapper">
      <img
        alt="Vue logo"
        class="logo"
        src="./assets/logo.jpg"
        width="125"
        height="125"
      />
      <HelloWorld msg="Wingspan Counter" />
      <Resources/>
  </main>
</template>

<style scoped>

header {
  line-height: 1.5;
}

.background {
  height: 100vh;
  width: 100vw;
  background: rgb(86, 153, 196);
  background: radial-gradient(
    circle,
    rgba(86, 153, 196, 1) 0%,
    rgba(222, 222, 212, 1) 100%
  );
}

.wrapper {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  
}
</style>
