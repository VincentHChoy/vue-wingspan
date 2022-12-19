<script setup>
import Food from "./Food.vue";
import Resources from "./Food.vue";
</script>


<script>
export default {
data() {
  return {
    egg:0,
    bug:0,
    cherry:0,
    wheat:0,
    fish:0,
    rat:0,
  }
}
}
</script>

<template>
  <section class="resources">
    <Food filename="egg.png" :method="minus" :resource=egg />
    <Food filename="bug.png" :resource="bug"/>
    <Food filename="cherry.png" :resource="cherry"/>
    <Food filename="wheat.png" :resource="wheat"/>
    <Food filename="fish.png" :resource="fish"/>
    <Food filename="rat.png" :resource="rat"/>
  </section>
  
</template>



<style scoped>
h1 {
  font-weight: 500;
  font-size: 2rem;
  top: -10px;
}

h3 {
  font-size: 1.2rem;
}

.plus {
  height: 40px;
}

.row {
  width: 500px;
  display: flex;
  flex-direction: row;
  justify-content: space-around;
}

.resources {
  padding: 2rem;
  color: blue;
  background-color: cornsilk;
  border: 5px double bisque;
  text-align: center;
}
</style>
