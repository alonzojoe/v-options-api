<template>
  <div>{{ greetings }}</div>
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
};
</script>

<style lang="scss" scoped></style>
