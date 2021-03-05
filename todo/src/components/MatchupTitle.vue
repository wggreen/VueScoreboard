<template>
  <div>
    <h2
      :class="{
        winning: teamOne.score > teamTwo.score,
        losing: teamOne.score < teamTwo.score,
      }"
    >
      {{ teamOne.name }}
    </h2>
    <h2
      :class="{
        winning: teamTwo.score > teamOne.score,
        losing: teamTwo.score < teamOne.score,
      }"
    >
      {{ teamTwo.name }}
    </h2>
  </div>
</template>

<script>
export default {
  props: ["teamOne", "teamTwo"],
};
</script>

<style>
.winning {
  color: green;
}
.losing {
  color: red;
}
</style>