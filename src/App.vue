<script>
export default {
  data() {
    return {
      count: 0, //reactive data
    };
  },
  methods: {
    //functions
    changeCount(type) {
      if (type === "increment") {
        this.count++;
      } else {
        this.count--;
      }
    },
  },
  computed: {
    doubleCount() {
      return this.count * 2;
    },
  },
};
</script>

<template>
  <div>
    <h3>Reactive Data and Methods</h3>
    <button @click="changeCount('increment')">+</button>
    <span style="margin: 0 15px">Count: {{ count }}</span>
    <button @click="changeCount('decrement')">-</button>
  </div>
  <div>
    <h3>Computer Properties</h3>
    <span>Double Count computed: {{ doubleCount }}</span>
  </div>
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
