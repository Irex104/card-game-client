<template>
  <div>
    <player-gui/>
  </div>
</template>

<script>
import PlayerGui from './players/PlayerGui.vue'

export default {
  components: {
    PlayerGui
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