<template>
  <div class="cards_container">
    
    <div v-for="card in playerWaist" :key="card.id">
        <div class="card_frame">
            <!-- <p>
                {{ card.id }}
                {{ card.figureName }}
                {{ card.colorName }}
            </p> -->
            <button class="card_button" @click="reveal(card)">
              <img class="card_image" :src="require('@/assets/cards/' + card.visibleImagePath)"/>
            </button> 
        </div> 
    </div>
    
  </div>
</template>

<script>
var apiURL = "http://localhost:9091/players/getPlayerCards/" + 1

export default {
  data() {
    return {
      playerWaist: [],
      cardImages: []
    }
  },
  methods: {
    reveal(card) {
      alert(card.figureName + ' ' 
          + card.colorName);
    }
  },
  created() {
    fetch(apiURL)
      .then(response => {
        return response.json();
      })
      .then(playerWaist => {
        this.playerWaist = playerWaist;
      })
  }
}
</script>

<style>
    .cards_container {
        margin-left: auto;
        margin-right: auto;
        width: 1200px;
        text-align: center;
        padding: 0;
        margin-bottom: 25px;
    }
    .card_image {
        width: 200px;
        /* transition: all .2s ease-in-out; */
    }
    /* .card_image:hover{
        -webkit-transform: scale(0.9);
        -ms-transform: scale(0.9);
        transform: scale(0.9);
    } */

    .card_frame {
        display: inline-block;
        float: left;
        text-align: center;
        border-radius: 5px;
        padding: 10px;
        transition: all .2s ease-in-out;
    }
    .card_frame:hover{
        background-color: #333333;
    }

    .card_button {
      padding: 0%;
      border: none;
      border-radius: 15px;
      background: transparent;
      transition: all .2s ease-in-out;
    }
    .card_button:hover {
      cursor: pointer;
      -webkit-transform: scale(0.9);
      -ms-transform: scale(0.9);
      transform: scale(0.9);
    }
</style>