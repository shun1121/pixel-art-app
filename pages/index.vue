<template>
  <v-container>
    <div>
      <v-row v-for="i of 30" :key="i" class="px-16">
        <v-col v-for="j of 30" :key="j" 
          class="py-3"
          @click="click(i-1, j-1, board)" 
          :class="{ 
              'purple lighten-5': activeItem1 === i-1 && activeItem2 === j-1 && number === 1,
              'purple lighten-4': board[i-1][j-1] === 1,
              'purple lighten-3': board[i-1][j-1] === 2,
              'purple lighten-2': board[i-1][j-1] === 3,
              'purple lighten-1': board[i-1][j-1] === 4,
              'purple': board[i-1][j-1] === 5,
              'purple darken-1': board[i-1][j-1] === 6,
              'purple darken-2': board[i-1][j-1] === 7,
              'purple darken-3': board[i-1][j-1] === 8,
              'purple darken-4': board[i-1][j-1] === 9,
              'white': board[i-1][j-1] === 10,
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
          [0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0],
        ],
      }
    },

    methods: {
        click(row_index, col_index, board) {
            this.activeItem1 = row_index;
            this.activeItem2 = col_index;

　　　　　    if (board[row_index][col_index] == 0) {
                board[row_index][col_index] = 1
                this.number = board[row_index][col_index]
            } else if (board[row_index][col_index] == 1) {
                board[row_index][col_index] = 2
                this.number = board[row_index][col_index]
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
  width: 100%;
  background: #fff;
  cursor: pointer;
}
</style>