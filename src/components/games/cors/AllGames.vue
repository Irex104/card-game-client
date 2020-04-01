<template>
  <div class="list_of_players">
    
    <div v-for="game in games" :key="game.id">
        <div class="frame_of_row">
            {{ game.id }}
        </div>
         <div class="frame_of_row">    
            {{ game.name }}
        </div>
    </div>
    
  </div>
</template>

<script>
const apiURL = "http://localhost:9091/games/getAll"

export default {
  data() {
    return {
      games: []
    }
  },
  created() {
    fetch(apiURL)
      .then(response => {
        return response.json();
      })
      .then(games => {
        this.games = games;
      })
  }
}
</script>

<style>
    .list_of_players {
        font-size: 30px;
    }

    .frame_of_row {
       border: 2px solid black; 
       display: inline-block;
       min-width: 150px;
    }
</style>