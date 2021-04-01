<template>
  <v-container>
    <div>
      <!-- <div v-bind:[style]="some"></div>   -->
      <v-row v-for="i of 30" :key="i">
        <v-col v-for="j of 30" :key="j" 
          @click="click(i-1, j-1, board)" 
          :class="{ 
              'purple lighten-5': activeItem1 === i-1 && activeItem2 === j-1 && number === 1,
              'purple lighten-4': activeItem1 === i-1 && activeItem2 === j-1 && number === 2,
              'purple lighten-3': activeItem1 === i-1 && activeItem2 === j-1 && number === 3,
              'purple lighten-2': activeItem1 === i-1 && activeItem2 === j-1 && number === 4,
              'purple lighten-1': activeItem1 === i-1 && activeItem2 === j-1 && number === 5,
              'purple': activeItem1 === i-1 && activeItem2 === j-1 && number === 6,
              'purple darken-1': activeItem1 === i-1 && activeItem2 === j-1 && number === 7,
              'purple darken-2': activeItem1 === i-1 && activeItem2 === j-1 && number === 8,
              'purple darken-3': activeItem1 === i-1 && activeItem2 === j-1 && number === 9,
              'purple darken-4': activeItem1 === i-1 && activeItem2 === j-1 && number === 10,
          }">
          </v-col>
      </v-row>
    </div>
  </v-container>
</template>
<script>
export default {
    data() {
      return {
        activeItem1: null,
        activeItem2: null,
        number: 0,
        board: [
          [1,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0],
          [0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0],
          [0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0],
          [0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0],
          [0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0],
          [0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0],
          [0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0],
          [0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0],
          [0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0],
          [0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0],
          [0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0],
          [0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0],
          [0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0],
          [0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0],
          [0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0],
          [0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0],
          [0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0],
          [0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0],
          [0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0],
          [0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0],
          [0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0],
          [0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0],
          [0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0],
          [0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0],
          [0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0],
          [0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0],
          [0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0],
          [0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0],
          [0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0],
          [0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0],
          [0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0],
        ],
      }
    },
    
    created() {
      this.number
      for (let i = 0; i < 30; i++) {
        for (let j = 0; j < 30; j++) {
          this.number = this.board[i][j]
        }
      }
    },

    methods: {
        click(row_index, col_index, board) {
            // console.log(this.activeItem1)
            // console.log(row_index)
            // console.log(col_index)
            // console.log(board)
            this.number = board[row_index][col_index]
            this.activeItem1 = row_index;
            this.activeItem2 = col_index;
            // console.log("----", this.activeItem1)
            if (this.activeItem1 === row_index && this.activeItem2 === col_index) {
                console.log(this.number)
                this.number++
            }
            if (this.number > 10) {
                this.number = 0
            }
            this.board = board
            console.log(this.board)
        },
    }
}
</script>
<style>
div .row{
  list-style: none;
  padding: 0;
}
div .col{
  border: 1px solid grey;
  /* display: block; */
  /* max-width: 480px; */
  width: 80%;
  background: #fff;
  /* box-shadow: 0 px 8px rgba(0,0,0,0.05); */
  cursor: pointer;
  /* transition: 0.1s ease-in-out; */
}

/* div .is-active{
    color: #fff;
    background: lightgreen;
    box-shadow: none;
  } */
</style>
