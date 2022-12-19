<script>
export default {
  props: {
    filename: String,
    resource: Number,
    egg: Boolean,
  },
  data() {
    return {
      counter: this.resource,
      totalEggs: 0,
      selected: false,
    };
  },
  methods: {
    plus(){
      if (this.counter === this.totalEggs && !this.selected) return null
      if(this.selected) return this.totalEggs++
      this.counter += 1;
    },
    minus() {
      if(this.selected){
        if(this.totalEggs !== 0 && this.totalEggs !== this.counter) return this.totalEggs--

      } else{
        if(this.counter !== 0) this.counter--
      }
    },
    getImageUrl() {
      return new URL(`./icons/${this.filename}`, import.meta.url);
    },
    toggleCounter() {
      this.selected = !this.selected;
      console.log("selected is now:", this.selected);
    },
  },
};
</script>

<template>
  <div class="row">
    <button @click="minus()" class="counter">-</button>
    <div class="resources">
      <img v-if="!egg" width="40" height="40" :src="getImageUrl()" />
      <img
        v-if="egg"
        v-bind:class="[selected ? 'blue' : 'none']"
        @click="toggleCounter()"
        width="40"
        height="40"
        :src="getImageUrl()"
      />
      <p v-if="!egg" class="hidden-border">{{ counter }}</p>
      <p v-if="egg" class="hidden-border">{{ counter }}/{{totalEggs}}</p>
    </div>
    <button v-if="!egg" @click="counter++" class="counter">+</button>
    <button v-if="egg" @click="plus()" class="counter">+</button>
  </div>
</template>

<style scoped>
.none{
  background-color: none;
}

.blue{
  background: rgb(86, 153, 196);
  background: radial-gradient(
    circle,
    rgba(86, 153, 196, 1) 0%,
    rgba(222, 222, 212, 1) 100%
  );
}

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

.hidden-border {
  border-style: none;
}

.counter {
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
