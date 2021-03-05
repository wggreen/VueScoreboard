<template>
  <div id="app">
    <matchup-title :teamOne="team1" :teamTwo="team2" />
    <game-status :teamOne="team1" :teamTwo="team2" />
    <scorecard
      :score="team1.score"
      @score-increased="updateScore(team1, 1)"
      @score-decreased="updateScore(team1, -1)"
    />
    <scorecard
      :score="team2.score"
      @score-increased="updateScore(team2, 1)"
      @score-decreased="updateScore(team2, -1)"
    />
  </div>
</template>

<script>
import MatchupTitle from "./components/MatchupTitle";
import Scorecard from "./components/Scorecard";
import GameStatus from "./components/GameStatus";

export default {
  components: {
    MatchupTitle,
    Scorecard,
    GameStatus,
  },
  data() {
    return {
      team1: {
        name: "Team 1",
        score: 0,
      },
      team2: {
        name: "Team 2",
        score: 0,
      },
    };
  },
  methods: {
    updateScore(team, points) {
      if (team.score + points >= 0) {
        team.score += points;
      }
    },
  },
};
</script>

<style></style>