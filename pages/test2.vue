<template>
  <v-container>
    <div>
      <v-row>
        <v-col v-on:click="onActive(n)" v-for="n of 6" :key="n" v-bind:class="{ 'is-active': activeItem === n }">Item {{n}}</v-col>
      </v-row>
    </div>
  </v-container>
</template>
<script>
export default {
    data() {
      return {
        activeItem: null,
        colour1: "",
        colour2: "",
        colour3: "",
        colour4: "",
        colour5: "",
        colour6: "",
        colour7: "",
        num: 0,
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


      changeColor() {
        // this.colour1 = "blue"
        if (this.num == 0) {
            this.colour1="white"
        }
        this.num++
        if (this.num == 1) {
            this.colour1="red"
            console.log(this.colour)
        } else if (this.num == 2) {
            this.colour1="orange"
        } else if (this.num == 3) {
            this.colour1="yellow"
        } else if (this.num == 4) {
            this.colour1="light-green"
        } else if (this.num == 5) {
            this.colour1="green"
        } else if (this.num == 6) {
            this.colour1="light-blue"
        } else if (this.num == 7) {
            this.colour="indigo"
        } else if (this.num == 8) {
            this.colour1="purple"
        } else if (this.num == 9) {
            this.colour1="pink"
        } else if (this.num > 9) {
            this.num = 0
            this.colour1="white"
        }
      }
    }
}
</script>
<style>
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
  box-shadow: 0 px 8px rgba(0,0,0,0.05);
  cursor: pointer;
  transition: 0.1s ease-in-out;
}

div .is-active{
    color: #fff;
    background: #333;
    box-shadow: none;
  }
</style>
