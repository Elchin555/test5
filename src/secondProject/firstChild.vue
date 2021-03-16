<template>
  <div>
    <p>1-ci bala</p>
    <p>Yasi bura yaz :{{age}}</p>
    <ul>
      <li v-for="arr in array">{{arr}}</li>
    </ul>
  </div>
</template>


<script>
import {eventBus} from "../main"

export default{
  data(){
    return{
      age:"",
      array:[],
    }
  },
  created(){
    eventBus.$on("testAge",(e)=>{
      this.age=e;
    }),
    eventBus.$on("testArray",(er)=>{
      this.array=er
    })
  }


}
</script>