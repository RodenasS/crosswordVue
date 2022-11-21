<template>
  <div class="entiretable">
    <table>
      <tr><td><input class="button" type="submit" value="Restartuoti"  v-on:click="this.RestartavimoFunkcija()"></td>
        <td><input class="button" type="submit" value="Tikrinti atsakymus"  v-on:click="this.TikrinimoFunkcija()"></td>
        <td><input class="button" type="submit" value="Rodyti atsakymus" v-on:click="this.PagalbosFunkcija()"></td> </tr>
    </table>
  </div>
</template>
<script>
export default {
  name: 'EngineComponent',
  mounted() {
    this.KrovimoFunkcija()
  },
  data: function() {
  },

  methods: {

    Numeriai(){
      document.getElementById("pzl_3_1").placeholder = "1";
      document.getElementById("pzl_1_6").placeholder = "2";
      document.getElementById("pzl_6_1").placeholder = "3";
      document.getElementById("pzl_3_8").placeholder = "4";
      document.getElementById("pzl_8_1").placeholder = "5";
      document.getElementById("pzl_3_10").placeholder = "6";
      document.getElementById("pzl_10_1").placeholder = "7";
      document.getElementById("pzl_5_4").placeholder = "8";
      document.getElementById("pzl_9_9").placeholder = "9";
      document.getElementById("pzl_3_2").placeholder = "10";
    },
    KrovimoFunkcija(){
      let puzzleTable = document.getElementById("puzzletable");
      this.puzzleData= this.PuzlesFunkcija();
      for ( let i = 0; i < this.puzzleData.length ; i++ ) {
        let row = puzzleTable.insertRow(-1);
        let rowData = this.puzzleData[i];
        for(let j = 0 ; j < rowData.length ; j++){
          let cell = row.insertCell(-1);
          if(rowData[j] != 0){
            let pzlID = String('pzl' + '_' + i + '_' + j);
            cell.innerHTML = '<input type="text" class="inputBox" maxlength="1" style="text-transform: uppercase" ' + 'id="' + pzlID + '">';
          }else{
            cell.style.background  = "#transparent";
          }
        }
      }
      this.Numeriai();
    },
    PuzlesFunkcija(){
      return [[0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0],
        [0, 0, 0, 0, 0, 0, 'e', 0, 0, 0, 0, 0],
        [0, 0, 0, 0, 0, 0, 's', 0, 0, 0, 0, 0],
        [0, 'j', 'a', 'v', 'a', 's', 'c', 'r', 'i', 'p', 't', 0],
        [0, 0, 'u', 0, 0, 0, 'o', 0, 'm', 0, 'u', 0],
        [0, 0, 's', 0, 'o', 0, 'r', 0, 'o', 0, 'r', 0],
        [0, 'f', 'i', 'a', 't', 0, 't', 0, 'l', 0, 'b', 0],
        [0, 0, 'n', 0, 't', 0, 0, 0, 'a', 0, 'i', 0],
        [0, 'm', 'i', 'n', 'o', 'l', 't', 'a', 0, 0, 'n', 0],
        [0, 0, 'm', 0, 0, 0, 0, 0, 0, 'k', 'a', 0],
        [0, 'm', 'o', 'n', 'o', 0, 0, 0, 0, 0, 0, 0],
        [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0],
      ];
    },
    RestartavimoFunkcija(){
      let puzzleTable = document.getElementById("puzzletable");
      puzzleTable.innerHTML = '';
      this.KrovimoFunkcija();
    },
    TikrinimoFunkcija(){
      for ( let i = 0; i < this.puzzleData.length ; i++ ) {
        let rowData = this.puzzleData[i];
        for(let j = 0 ; j < rowData.length ; j++){
          if(rowData[j] != 0){
            let selectedInputTextElement = document.getElementById('pzl' + '_' + i + '_' + j);
            if(selectedInputTextElement.value != this.puzzleData[i][j]){
              selectedInputTextElement.style.backgroundColor = '#a83232';

            }else{
              selectedInputTextElement.style.backgroundColor = '#4ca832';
            }
          }
        }
      }
    },
    PagalbosFunkcija(){
      for ( let i = 0; i < this.puzzleData.length ; i++ ) {
        let rowData = this.puzzleData[i];
        for(let j = 0 ; j < rowData.length ; j++){
          if(rowData[j] != 0){
            let selectedInputTextElement = document.getElementById('pzl' + '_' + i + '_' + j);
            selectedInputTextElement.value = this.puzzleData[i][j];
            selectedInputTextElement.style.backgroundColor = '#4ca832';
          }
        }
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
