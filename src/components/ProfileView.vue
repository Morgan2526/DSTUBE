<script setup>
import headerComponent from './headerComponent.vue';
import Footer from './Footer.vue';
import { ref } from 'vue';
import { computed } from '@vue/reactivity';

var fName=ref('')
var lName = ref('')
var mobileNumber = ref('')
var email = ref('')

var show=function(){
  alert(fName.value+" "+lName.value+" "+mobileNumber.value+" "+email.value)
}

const emit = defineEmits(['nextPath']);
const setNext = id =>{
    emit('nextPath',1 )
  }


const fullName = computed(()=>{
  return fName.value+" "+lName.value
})

</script>

<template>
    <headerComponent fromWhat="false"  @goToHome="setNext"></headerComponent>
    <input class="inputtags" type="text" v-model="fName" id="fName" placeholder="First Name" style="margin-top: 10%;">
    <input class="inputtags" type="text" v-model="lName" id="lName" placeholder="Last Name" style="margin-top: 15%;">
    <input class="inputtags" type="text" v-model="mobileNumber" id="mobileNumber" placeholder="Mobile Number" style="margin-top: 20%;">
    <input class="inputtags" type="text" v-model="email" id="email" placeholder="Email" style="margin-top: 25%;">

    <button @click="show()">Update</button>

    <p class="heading">Details</p>
    <div class="heading2">
    <p >Name: {{ fullName }}</p>
    <p>Mobile Number : {{ mobileNumber }}</p>
    <p>Email : {{ email }}</p>
    </div>

    <Footer location="profile"/>
</template>


<style scoped>
.inputtags{
      width: 40%;
      height: 33px;
      margin-left: 30%;
      color: white;
      background-color: #181818;
      border: 0.2px solid gray;
      z-index: 2;
      border-radius: 0px;
      padding-left: 20px;
      position:absolute;
      align-items: center;
  }
  .inputtags::placeholder{
    padding: 3px;
     color: rgb(217, 223, 228);
  }


  button{
    position: relative;
    top: 420px;
    left: 600px;
    background-color: #181818;
    border: 1px solid gray;
    padding: 10px;
    color:rgb(1, 148, 197);
    border-radius: 5px;
    font-size: 15px;
    font-weight: 600;
  }

  .heading{
    position: absolute;
    width: 855px;
    top:550px;
    left: 259px;
    height: 22.4px;
    font-family: 'Roboto';
    font-style: normal;
    font-weight: 400;
    font-size: 20px;
    line-height: 23px;
    color: #FFFFFF;
    text-decoration: underline  #CC0000 2px;
}

.heading2{
  position: relative;
    width: 468px;
    left: 259px;
    height: 22.4px;
    font-family: 'Roboto';
    top: 553px;
    font-style: normal;
    font-size: 17px;
    line-height: 9px;
    color: #e9e3e3;
}
</style>