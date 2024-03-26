<template>
  <h3>Child Component</h3>
  <div>{{ greetings }}</div>
  <h5>Data message: {{ message }}</h5>
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
    };
  },
  methods: {
    sendDataToParent() {
      this.$emit("send-data", "Hello from Child!");
    },
  },
  mounted() {
    this.message = "Component is mounted";
  },
};
</script>

<style lang="scss" scoped></style>
