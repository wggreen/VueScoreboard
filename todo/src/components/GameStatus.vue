<template>
  <div>
    <p>{{ gameLeaderDisplay }}</p>
  </div>
</template>

<script>
export default {
  props: ["teamOne", "teamTwo"],
  computed: {
    gameLeaderDisplay() {
      const { teamOne, teamTwo } = this.$props;
      if (teamOne.score > teamTwo.score) {
        if (teamOne.score - teamTwo.score > 1) {
          return `${teamOne.name} is winning by ${
            teamOne.score - teamTwo.score
          } points`;
        } else {
          return `${teamOne.name} is winning by ${
            teamOne.score - teamTwo.score
          } point`;
        }
      } else if (teamTwo.score > teamOne.score) {
        if (teamTwo.score - teamOne.score > 1) {
          return `${teamTwo.name} is winning by ${
            teamTwo.score - teamOne.score
          } points`;
        } else {
          return `${teamTwo.name} is winning by ${
            teamTwo.score - teamOne.score
          } point`;
        }
      } else {
        return "The game is tied";
      }
    },
  },
};
</script>

<style>
</style>