<template>
  <div>
    
  </div>
</template>

<script>
export default {
  data() {
    return {
      playersData: [
        {
          id: "1",
          name: "Victor",
          championshipTotalPoints: 232.0
        },
      ]
    }
  },
  methods: {
    playersPointsOnSingleGame(playersDataByGame) {
      // Pontos = 10 
      //    * RAIZ(N° de jogadores / Rank) 
      //    * (1 + LOG(Premio total / Jogadores + 0.25))^2 
      //    / (1 + LOG(Buy-in + Rebuys + Add-ons + 0.25))
      const playersPoints = [];
      const numberOfPlayers = playersDataByGame.lenght;
      const buyins = playersDataByGame.lenght * (17000.0);
      const rebuys = 0.0;
      const addons = 0.0;
      const totalPrize = 0.0;

      for(pd in playersDataByGame) {
        
      }
      
      for(pd in playersDataByGame) {
        const playerRank = pd.rank;


        const playerPoints = 10.0 
          * Math.sqrt((numberOfPlayers / playerRank))
          * ( 1 + Math.pow( Math.log10(totalPrize / (numberOfPlayers + 0.25)), 2) ) 
          / (1 + Math.log10(buyins + rebuys + addons + 0.25));

        const player = {
          id: pd.id,
          points: playerPoints
        };

        playersPoints.push(player);

      }

      return playersPoints;
    }
  }
}
</script>