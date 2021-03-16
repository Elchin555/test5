<template>
  <div>
    <p>2-ci bala</p>
    <p>istifadeci adi:{{name}}</p>
    <button @click="changeParent">parentde deyisiklik et</button>
    <button @click="changeAgeOne">1-ci balada yashi yaz</button>
    <button @click="sendToArray">arrayi 1 e gonder</button>

    <ul>
      <li v-for="ar in array">
        <ul>
          <li v-for="(a,key) in ar">
           {{key}}-- {{a}}
          </li>
          </ul>
      </li>
    </ul>
  </div>
</template>


<script>
import {eventBus} from "../main"


export default{

 props:["name"],
 data(){
   return{
    array:[
      {id:1,status:"kritik"},
      {id:2,status:"Normal"},
      {id:3,status:"UStun"},
    ]
   }
 },
 methods:{
   changeParent(){
     this.$emit("data","funcikkkkkkkkkk")
   },
   changeAgeOne(){
     this.age=466;
     eventBus.$emit("testAge",this.age)
   },
   sendToArray(){
     eventBus.$emit("testArray",this.array)
   }

 } 

}
</script>