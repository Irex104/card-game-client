<template>
  <div class="list_of_players">
    
    <div v-for="player in players" :key="player.id">
        <div class="frame_of_row">
            {{ player.id }}
        </div>
         <div class="frame_of_row">    
            {{ player.name }}
        </div>
    </div>
    
  </div>
</template>

<script>
const apiURL = "http://localhost:9091/players/getAll"

export default {
  data() {
    return {
      players: []
    }
  },
  created() {
    fetch(apiURL)
      .then(response => {
        return response.json();
      })
      .then(players => {
        this.players = players;
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