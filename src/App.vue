<script>
import Child from "./components/Child.vue";
export default {
  components: {
    Child,
  },
  data() {
    return {
      count: 0, //reactive data
      formData: {},
      message: "",
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
    receiveData(params) {
      this.message = params;
    },
  },
  computed: {
    doubleCount() {
      return this.count * 2;
    },
  },
  watch: {
    count(newValue, oldValue) {
      console.log("New Value", newValue);
      console.log("Old Value", oldValue);
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
  <div>
    <h3>Working with events receiving data from Child</h3>
    <span>Message from child: {{ message }}</span>
  </div>
  <Child @send-data="receiveData" :greetings="'working with propr'" />
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
