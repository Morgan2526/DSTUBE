<script setup>

var props = defineProps({
  fromWhat:{
    type:String,
    required:true
  }
})

var emit = defineEmits(['goToProfile','goToHome'])
function goToProfile(){
  emit('goToProfile')
}

function goToHome(){
  emit('goToHome')
}

</script>
<template>
  <div class="head">
      <button class="logo">DSTUBE</button>
      <input class="search" type="text" placeholder="Search">
      <button v-if="fromWhat =='true'" class="profile"  @click="goToProfile"> Profile</button>
      <button v-if="fromWhat == 'false'" class="profile"  @click="goToHome" >Home</button>
      <div v-if="fromWhat == 'f'" class="margin">
        <button  class="profile1"  @click="goToHome" >Home</button>
        <button class="profile1"  @click="goToProfile"> Profile</button>
      </div>
      
      </div>
</template>


<style scoped>

  .margin{
    margin-left:1030px ;
  }
  .head {
      position: fixed;
      top: 0px;
      width: 100%;
      margin: 0;
      background-color: #202020;
      height:75px;
      left: 0px;
      margin-left: 0; 
      display: inline-block;
  }
  .logo{
      margin-top: 15px;
      height: 40px;   
      width: 8%;
  }
  .logo{
      margin-left: 30px;
      background-color: #CC0000;
      border:none;
      color: wheat;
      font-weight: 600;
  }
  .profile{
      margin-left:240px;
      background-color: #181818;
      color: #3EA6FF;
      padding-left: 20px;
      padding-top: 10px;
      padding-bottom: 10px;
      padding-right: 20px;
      font-weight: 600;
      border: 1px solid #3EA6FF;
      border-radius: 5px;
  }

  .profile1{
    position: relative;
    top: -39px;
    margin-left: 17px;
    background-color: #181818;
    color: #3EA6FF;
    padding-left: 20px;
    padding-top: 10px;
    padding-bottom: 10px;
    padding-right: 20px;
    font-weight: 600;
    border: 1px solid #3EA6FF;
    border-radius: 5px;
  }
  .search{
      width: 40%;
      height: 33px;
      margin-left: 20%;
      color: white;
      background-color: #121212;
      border: 0.2px solid gray;
      z-index: 2;
      border-radius: 20px;
      padding-left: 20px;
  }
  .search::placeholder{
    padding: 3px;
     color: rgb(217, 223, 228);
  }

</style>