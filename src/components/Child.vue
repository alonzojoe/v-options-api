<template>
  <h3>Child Component</h3>
  <div>{{ greetings }}</div>
  <h5>Data message: {{ message }}</h5>
  <h3>Mounted Theme based on device: {{ currentTheme }}</h3>
  <button @click="sendDataToParent">Send Data to Parent</button>
</template>

<script>
export default {
  props: {
    greetings: {
      type: String,
      default: "test",
      required: false,
    },
  },
  data(props) {
    return {
      message: "",
      currentTheme: "light-mode",
    };
  },
  methods: {
    sendDataToParent() {
      this.$emit("send-data", "Hello from Child!");
    },
  },
  mounted() {
    this.message = "Component is mounted";
    if (
      window.matchMedia &&
      window.matchMedia("(prefers-color-scheme: dark)").matches
    ) {
      this.currentTheme = "dark-mode";
    }
  },
};
</script>

<style lang="scss" scoped></style>
