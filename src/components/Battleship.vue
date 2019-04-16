  <template>
  <div class="abc">
    <h3>A B C D E F G</h3>
    <table>
      <tr v-for="(row, rowIndex) in 7">
      <td v-for="(cell, cellIndex) in 7" :id="rowIndex + '-' + cellIndex" @click="checkHit"> <!-- :class="{ hit: hit, miss: miss }" -->
      </td>
      </tr>

    </table>
    <h3>0 1 2 3 4 5 6</h3>
  </div>
  </template>

  <script>
  export default {
  name: 'Battleship',
  data() {
    return {
      rows: 7,
      squares: 7,
      /*randomRow: String,
      randomCell: String,
      singleShip: String,
      Destoryer: String, //2
      Destoryer2: String, //2
      Cruiser: String, //3
      Cruiser2: String, //3
      Cruiser3: String, //3
      Submarine: String, //3
      Submarine2: String, //3 //Göra dessa till objekt istället?
      Submarine3: String, //3
      Battleship: String, //4
      Battleship2: String, //4
      Battleship3: String, //4
      Battleship4: String, //4
      Carrier: String, //5
      Carrier2: String, //5
      Carrier3: String, //5
      Carrier4: String, //5
      Carrier5: String, //5*/
      hit: Number,
      miss: Number,
      min: 0,
      max: 6,
    };
  },
  methods: {
    checkHit: function (event) {
      //https://codepen.io/CodifyAcademy/pen/ByBEOz
      console.log(event.target.id);
      /* Hur göra detta nu? */
      if (event.target.id !== this.randomPosition){
        this.hit = false;
        this.miss = true;
        console.log(this.hit);
      }
      if (event.target.id === this.randomPosition){
          this.hit = true;
          this.miss = false;
          console.log(this.hit);
          alert("nooo me ship!! >:(");
        }
      },
      /* How to not make these numbers overlap */
        singleShip: function() {
          this.randomRow = Math.floor(Math.random() * (this.max - this.min) + this.min);
          this.randomCell = Math.floor(Math.random() * (this.max - this.min) + this.min);
          this.singleShip = this.randomRow + "-" + this.randomCell;
          console.log("Single ship", this.singleShip);
        },
        Destroyer: function (){
          this.randomRow = Math.floor(Math.random() * (this.max - this.min) + this.min);
          this.randomCell = Math.floor(Math.random() * (this.max - this.min) + this.min);
          this.Destroyer = this.randomRow + "-" + this.randomCell;
          this.Destroyer2 = this.randomRow + "-" + (this.randomCell + 1);
          console.log("Destroyer ", this.Destroyer, this.Destroyer2);
          console.log("Randoms destroyer ", this.randomRow, this.randomCell);
        },
        Cruiser: function(){
          this.randomRow = Math.floor(Math.random() * (this.max - this.min) + this.min);
          this.randomCell = Math.floor(Math.random() * (this.max - this.min) + this.min);
          this.Cruiser = this.randomRow + "-" + this.randomCell;
          this.Cruiser2 = this.randomRow + "-" + (this.randomCell + 1);
          this.Cruiser3 = this.randomRow + "-" + (this.randomCell + 2);
          console.log("Cruiser", this.Cruiser, this.Cruiser2, this.Cruiser3);
        },
        Submarine: function() {
          this.randomRow = Math.floor(Math.random() * (this.max - this.min) + this.min);
          this.randomCell = Math.floor(Math.random() * (this.max - this.min) + this.min);
          this.Submarine = this.randomRow + "-" + this.randomCell;
          this.Submarine2 = this.randomRow + "-" + (this.randomCell + 2);
          this.Submarine3 = this.randomRow + "-" + (this.randomCell + 3);
          console.log("Submarine ", this.Submarine, this.Submarine2, this.Submarine3);
        },
        Battleship: function () {
          this.randomRow = Math.floor(Math.random() * (this.max - this.min) + this.min);
          this.randomCell = Math.floor(Math.random() * (this.max - this.min) + this.min);
          this.Battleship = this.randomRow + "-" + this.randomCell;
          this.Battleship2 = this.randomRow + "-" + (this.randomCell + 1);
          this.Battleship3 = this.randomRow + "-" + (this.randomCell + 2);
          this.Battleship4 = this.randomRow + "-" + (this.randomCell + 3);
          console.log("Battleship ", this.Battleship, this.Battleship2, this.Battleship3, this.Battleship4);
        },
        Carrier: function () {
          this.randomRow = Math.floor(Math.random() * (this.max - this.min) + this.min);
          this.randomCell = Math.floor(Math.random() * (this.max - this.min) + this.min);
          this.Carrier = this.randomRow + "-" + this.randomCell;
          this.Carrier2 = this.randomRow + "-" + (this.randomCell + 1);
          this.Carrier3 = this.randomRow + "-" + (this.randomCell + 2);
          this.Carrier4 = this.randomRow + "-" + (this.randomCell + 3);
          this.Carrier5 = this.randomRow + "-" + (this.randomCell + 4);
          console.log("Carrier ", this.Carrier, this.Carrier2, this.Carrier3, this.Carrier4, this.Carrier5);
        }
    },
    mounted(){
      this.singleShip();
      this.Destroyer();
      this.Cruiser();
      this.Submarine();
      this.Battleship();
      this.Carrier();
    }
  }
  </script>

  <style lang="less" scoped>
  table {
  display: inline-block;

  td {
    border: 1px solid green;
    height: 50px;
    width: 50px;
    }
  }

  h3 {
    &:first-of-type {
      letter-spacing: 0.2rem;
      display: inline-block;
      writing-mode: vertical-rl;
      text-orientation: upright;
    }

    &:last-of-type {
      letter-spacing: 1.2rem;
      margin-left: 5rem;
    }
  }
  </style>
