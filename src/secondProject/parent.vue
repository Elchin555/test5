<template>
  <div>
    <div class="papa">
      <h3>This is Parent</h3>
      <button @click="changeTwo">2ci balada ad deyis</button>
      <p>burda 2c-parentden gelen ada uygun deyisik ada olacaq:{{test}}</p>
      <hr>
      <div class="firstChild">
      <first-child></first-child>

      </div>
      <div class="secondChild">
    <two-child @data="test=$event"  v-bind:name="title"></two-child>

      </div>
    </div>
   
  </div>
</template>


<script>
import firstChild from "./firstChild";
import twoChild from "./twoChild";


export default{
  components: { firstChild,twoChild },
  data (){
    return{
      title:"Elcin",
      test:''
      
    }
  },
  methods:{
    changeTwo(){
      this.title="eliaga"
    }
  }
 
}
</script>

<style scoped>
.papa{
  background-color: rgb(255, 0, 191);
}
.firstChild{
  background-color: cadetblue;
  height:150px;
}
.secondChild{
  background-color: rgb(239, 255, 9);
  height:250px;
}

</style>