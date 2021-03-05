<template>
  <div>
    <h2>{{ score }}</h2>
    <button @click="plusClick">+</button>
    <button @click="minusClick">-</button>
  </div>
</template>

<script>
export default {
  props: ["score"],
  methods: {
    plusClick() {
      this.$emit("score-increased");
    },
    minusClick() {
      this.$emit("score-decreased");
    },
  },
};
</script>

<style></style>