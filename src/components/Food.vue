<script>
export default {
  props: {
  filename: String,
  resource: Number
  },
  data(){
    return{
      counter: this.resource
    }
  },
  methods:{
    minus(num){
      if(num === 0) return num
      this.counter -= 1
    },
    getImageUrl(){
      return new URL(`./icons/${this.filename}`, import.meta.url);
    }
  }
}

</script>

<template>
  <div class="row">
    <button min="0" @click="minus(counter)" class="counter">-</button>
    <div class="resources">
      <img width="40" height="40" :src="getImageUrl()" />
      <p class="hidden-border">{{counter}}</p>
    </div>
    <button @click="counter++" class="counter">+</button>
  </div>
</template>

<style scoped>
.plus {
  height: 40px;
}

.row {
  width: 500px;
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  align-items: center;
}

.hidden-border{
  border-style: none;
}

.counter{
  cursor: pointer;
}

.resources {
  height: 40px;
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  align-items: center;
  border-style: none;
}


.column {
  display: flex;
  flex-direction: column;
  justify-content: space-around;
}
</style>
