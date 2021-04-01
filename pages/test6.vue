<template>
  <v-container>
    <div>
      <!-- <div v-bind:[style]="some"></div>   -->
      <v-row v-for="i of 2" :key="i">
        <v-col v-for="j of 2" :key="j" 
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
          [4,0],
          [0,0],
        ],
      }
    },

    methods: {
        click(row_index, col_index, board) {
            console.log(board[row_index][col_index])
            this.activeItem1 = row_index;
            this.activeItem2 = col_index;

　　　　　    if (board[row_index][col_index] == 0) {
                board[row_index][col_index] = 1
                this.number = board[row_index][col_index]
                console.log(this.number)
            } else if (board[row_index][col_index] == 1) {
                board[row_index][col_index] = 2
                this.number = board[row_index][col_index]
                console.log(this.number)
            } else if (board[row_index][col_index] == 2) {
                board[row_index][col_index] = 3
                this.number = board[row_index][col_index]
            } else if (board[row_index][col_index] == 3) {
                board[row_index][col_index] = 4
                this.number = board[row_index][col_index]
            } else if (board[row_index][col_index] == 4) {
                board[row_index][col_index] = 5
                this.number = board[row_index][col_index]
            } else if (board[row_index][col_index] == 5) {
                board[row_index][col_index] = 6
                this.number = board[row_index][col_index]
            } else if (board[row_index][col_index] == 6) {
                board[row_index][col_index] = 7
                this.number = board[row_index][col_index]
            } else if (board[row_index][col_index] == 7) {
                board[row_index][col_index] = 8
                this.number = board[row_index][col_index]
            } else if (board[row_index][col_index] == 8) {
                board[row_index][col_index] = 9
                this.number = board[row_index][col_index]
            } else if (board[row_index][col_index] == 9) {
                board[row_index][col_index] = 10
                this.number = board[row_index][col_index]
            } else if (board[row_index][col_index] == 10) {
                board[row_index][col_index] = 0
                this.number = board[row_index][col_index]
            }  
            let backup = new Array(2)
            // ↑ [[], []]この状態
            // for (let i = 0; i < board.length; i++) {
            //     arr[i] = new Array(3,3)
            // }
            // ↑ [ 
            //     [3,3],
            //     [3,3]
            //   ]  この状態
            
            for (let i = 0; i < board.length; i++) {
                backup[i] = new Array(2)
            }
            for (let i = 0; i < board.length; i++) {
                for (let j = 0; j < board[0].length; j++) {
                    backup[i][j] = board[i][j]
                }
            }      
            // backup.push(board)
            console.log(backup)
            console.log(board)
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
  width: 100%;
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