<template>
  <div>{{ greetings }}</div>
  <h5>Data message: {{ message }}</h5>
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
  mounted() {
    this.message = "Component is mounted";
  },
};
</script>

<style lang="scss" scoped></style>
