<template lang="">
  <div>
    <h1>Counter -> <span>{{counter}}</span></h1>
    <button @click="increase()">Increase</button>
    <button @click="decrease()">Decrease</button>
  </div>

  <img scr="imgUrl">

  <div>
    <!-- Class styling binding -->
     <h4 :class="{hello:check}">Conditional Rendering</h4>
     <!-- Conditional rendering -->
    <h1 v-if="check">The value is true</h1>
    <h1 v-else>The value is false</h1>
    <button @click="change()">Change Status</button>

    <!-- conditional rendering -->
    <h1 v-show="check">This contains the v-show</h1>

    <ul>

      <!-- <li v-for="sport in sports" :key="sport">{{sport}}</li> -->
      <li v-for="({message},index) in objects" :key="index">{{message}}</li>
    </ul>

    <!-- one-way data binding -->
    <h3>{{oneWayText}}</h3>
    <!-- two-way data binding -->
    <h3>{{twoWayText}}</h3>
    <input type="text" v-model="twoWayText">
  </div>

  <!-- <info-comp first-name="hehe" last-name="hehehehe"/>
  <info-comp first-name="hehe1"/>
  <info-comp :object-data='singleObject'/> -->

 <info-comp>
  I'm using slots
 </info-comp>
 <slot-comp>
  <template #slotTitle>
    <!-- Card Slot -->
  </template>

  <template #Defualt>
    <!-- <img :scr="imgUrl"> -->
  </template>
 </slot-comp>

  </template>
  
<script>
/* eslint-disable */ 
import InfoComp from '../components/InfoComp.vue'
import SlotComp from '../components/SlotComp.vue'
export default {
  data(){
    return{
      counter: 0,
      imgUrl:"https://kingkrazee.github.io/eccomerce/images/FITZ.png",
      check: true,
      sports:['soccer', 'netball', 'volleyball'],
      objects:[
        {message: 'Hello There 1', id:1},
        {message: 'Hello There 2', id:2},
        {message: 'Hello There 3', id:3}
        ],
        singleObject:{
          name:'Candice',
          surname:'Keet'
        },
        oneWayText:'heyy',
        twoWayText:'heyyy'
    }
  },
  components:{
    InfoComp,
    SlotComp
  },
  methods:{
    increase(){
      this.counter++
    },
    decrease(){
      this.counter--
    }
  }
}
</script>

<style scoped>
  h1{
    color:blue
  }
</style>