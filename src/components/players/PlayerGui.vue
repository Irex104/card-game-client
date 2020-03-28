<template>
  <div>
    <all-players/>
    <player-waist/>
  </div>
</template>

<script>
import AllPlayers from './cors/AllPlayers.vue'
import PlayerWaist from './cors/PlayerWaist.vue'

export default {
  components: {
    AllPlayers,
    PlayerWaist
  }
}
</script>

<style>

</style>