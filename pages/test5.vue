<template>
  <v-container>
    <div>
      <!-- <v-row>
        <v-col v-on:click="onActive(n)" v-for="n of 6" :key="n" v-bind:class="{ 'is-active': activeItem === n }">Item {{n}}</v-col>
      </v-row> -->
      <v-row v-for="i in 30" :key="i" no-gutters>
        <v-col v-for="j in 30" :key="j">
          <v-btn :class="{ 'is-active': activeItem1 === i && activeItem2 === j }" x-small width="100%" @click="changeColour(i, j)">□</v-btn>
          <!-- <v-btn :class="colour" x-small width="100%" @click="changeColor(i-1, j-1)"></v-btn> -->
          <!-- <v-btn :class="board[i-1][j-1]" x-small width="100%" @click="changeColor(i-1, j-1)">{{ colour }}</v-btn> -->
        </v-col>
      </v-row>
    </div>
  </v-container>
</template>

<script>
export default {
  components: {
  },

  data() {
    return {
      activeItem: null,
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
      activeItem1: null,
      activeItem2: null,
      num: 0,
      colour: '',
    }
  },

  methods: {
    onActive(n) {
        if(this.activeItem === n){
          this.activeItem = null;
        }else{
          this.activeItem = n;
        }
    },


    changeColour(row_index, col_index) {
      if (this.activeItem1 === row_index && this.activeItem2 === col_index) {
        this.activeItem1 = null
        this.activeItem2 = null
        console.log(this.activeItem1)
        console.log(this.activeItem2)
        console.log("null") 
      } else {
        this.activeItem1 = row_index
        this.activeItem2 = col_index
        console.log(this.activeItem1)
        console.log(this.activeItem2)
        console.log("i,j")
      }
    },



    changeColor(row_index, col_index) {
      console.log(row_index)
      console.log(col_index)

      this.board[row_index][col_index]++
      console.log(this.board[row_index][col_index])
      if (this.board[row_index][col_index] == 0) {
        this.colour="white"
      }
      if (this.board[row_index][col_index] == 1) {
        this.colour="red"
      } else if (this.board[row_index][col_index] == 2) {
        this.colour="orange"
      } else if (this.board[row_index][col_index] == 3) {
        this.colour="yellow"
      } else if (this.board[row_index][col_index] == 4) {
        this.colour="light-green"
      } else if (this.board[row_index][col_index] == 5) {
        this.colour="green"
      } else if (this.board[row_index][col_index] == 6) {
        this.colour="light-blue"
      } else if (this.board[row_index][col_index] == 7) {
        this.colour="indigo"
      } else if (this.board[row_index][col_index] == 8) {
        this.colour="purple"
      } else if (this.board[row_index][col_index] == 9) {
        this.colour="pink"
      } else if (this.board[row_index][col_index] > 9) {
        this.board[row_index][col_index] = 0
        this.colour="white"
      }
      console.log(this.board[row_index][col_index],"num")
      console.log(this.colour,"colour")

      // for (let i = 0; i < this.board.length; i++) {
      //   for (let j = 0; j < this.board[0].length; j++) {
      //     this.board[row_index][col_index]++
      //     // let i=this.board[row_index][col_index]
      //     console.log(this.board[row_index][col_index])
      //     break
      //     if (i == 0) {
      //       this.colour = "white"
      //     } else if (i ==1) {
      //       this.colour = "blue"
      //     }
      //     // console.log(i)
      //   }
      // }



    // changeColor(row_index, col_index) {  
      // if (this.num == 0) {
      //   this.colour="white"
      // }
      // this.num++
      // if (this.num == 1) {
      //   this.colour="red"
      //   console.log(this.colour)
      // } else if (this.num == 2) {
      //   this.colour="orange"
      // } else if (this.num == 3) {
      //   this.colour="yellow"
      // } else if (this.num == 4) {
      //   this.colour="light-green"
      // } else if (this.num == 5) {
      //   this.colour="green"
      // } else if (this.num == 6) {
      //   this.colour="light-blue"
      // } else if (this.num == 7) {
      //   this.colour="indigo"
      // } else if (this.num == 8) {
      //   this.colour="purple"
      // } else if (this.num == 9) {
      //   this.colour="pink"
      // } else if (this.num > 9) {
      //   this.num = 0
      //   this.colour="white"
      // }
      // }
    }
  }
}
</script>
<style>
.v-btn .is-active {
  background-color: "orange";
  color: "orange";
  border: 1px solid red;
}
div .row{
  list-style: none;
  padding: 0;
}
div .col{
  display: block;
  max-width: 480px;
  width: 100%;
  margin: 20px auto;
  padding: 20px;
  background: #fff;
  box-shadow: 0 3px 8px rgba(0,0,0,0.05);
  cursor: pointer;
  transition: 0.3s ease-in-out;
}
/* div .is-active{
    background: red;
    color: red;
    border: 1px solid red;
    box-shadow: none;
  } */
</style>

