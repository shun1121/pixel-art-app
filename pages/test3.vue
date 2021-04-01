<template>
  <v-container>
    <div>
      <v-row v-for="i of 30" :key="i">
        <v-col v-for="j of 30" :key="j" :class="{ 'is-active': activeItem1 === i && activeItem2 === j }" @click="onActive(i,j)"></v-col>
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
        onActive(row_index,col_index) {
            console.log(this.activeItem1)
            console.log(row_index)
            console.log(col_index)
            //↓ this.activeItem1とthis.activeItem2の初期値はnull
            if (this.activeItem1 === row_index && this.activeItem2 === col_index) {
                // 既に押されている状態。is-activeを無効にする。
                this.activeItem1 = null;
                this.activeItem2 = null;
                console.log("++++", this.activeItem1)
            } else {
                // is-activeが発動する。
                this.activeItem1 = row_index;
                this.activeItem2 = col_index;
                console.log("----", this.activeItem1)
            }
        },


    //   changeColor() {
    //     // this.colour1 = "blue"
    //     if (this.num == 0) {
    //         this.colour1="white"
    //     }
    //     this.num++
    //     if (this.num == 1) {
    //         this.colour1="red"
    //         console.log(this.colour)
    //     } else if (this.num == 2) {
    //         this.colour1="orange"
    //     } else if (this.num == 3) {
    //         this.colour1="yellow"
    //     } else if (this.num == 4) {
    //         this.colour1="light-green"
    //     } else if (this.num == 5) {
    //         this.colour1="green"
    //     } else if (this.num == 6) {
    //         this.colour1="light-blue"
    //     } else if (this.num == 7) {
    //         this.colour="indigo"
    //     } else if (this.num == 8) {
    //         this.colour1="purple"
    //     } else if (this.num == 9) {
    //         this.colour1="pink"
    //     } else if (this.num > 9) {
    //         this.num = 0
    //         this.colour1="white"
    //     }
    //   }
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

div .is-active{
    color: #fff;
    background: lightgreen;
    box-shadow: none;
  }
</style>