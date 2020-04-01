<template>
  <div>
    <player-gui/>
    <game-gui/>
  </div>
</template>

<script>
import PlayerGui from './players/PlayerGui.vue'
import GameGui from './games/GameGui.vue'

export default {
  components: {
    PlayerGui,
    GameGui
  }
}
</script>

<style>
    body {
        background-color: #908d99;
        font-family: Verdana;
        color: rgb(238, 235, 235);
    }
</style>