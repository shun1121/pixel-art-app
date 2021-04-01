<template>
  <v-container>
    <div>
      <!-- <div v-bind:[style]="some"></div>   -->
      <v-row v-for="i of 30" :key="i">
        <v-col v-for="j of 30" :key="j" 
          @click="click(i,j)" 
          :class="{ 
              'purple lighten-5': activeItem1 === i && activeItem2 === j && num === 1,
              'purple lighten-4': activeItem1 === i && activeItem2 === j && num === 2,
              'purple lighten-3': activeItem1 === i && activeItem2 === j && num === 3,
              'purple lighten-2': activeItem1 === i && activeItem2 === j && num === 4,
              'purple lighten-1': activeItem1 === i && activeItem2 === j && num === 5,
              'purple': activeItem1 === i && activeItem2 === j && num === 6,
              'purple darken-1': activeItem1 === i && activeItem2 === j && num === 7,
              'purple darken-2': activeItem1 === i && activeItem2 === j && num === 8,
              'purple darken-3': activeItem1 === i && activeItem2 === j && num === 9,
              'purple darken-4': activeItem1 === i && activeItem2 === j && num === 10,
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
        num: 0,
      }
    },

    methods: {
        click(row_index,col_index) {
            // console.log(this.activeItem1)
            // console.log(row_index)
            // console.log(col_index)
            this.activeItem1 = row_index;
            this.activeItem2 = col_index;
            // console.log("----", this.activeItem1)
            if (this.activeItem1 === row_index && this.activeItem2 === col_index) {
                this.num++
                console.log(this.num)
            }
            if (this.num > 10) {
                this.num = 0
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
