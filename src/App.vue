<script setup>

import HomeView from './components/HomeView.vue';
import ProfileView from './components/ProfileView.vue';
import View from './components/View.vue'
import { ref } from 'vue';
import employees from "./assets/employee.json"

var profile = ref(false)
var home = ref(true)
var videoTile = ref(false)



var setPath=id=>{

  if(id==1){
    profile.value=false;
    home.value=true;
    videoTile.value=false;
  }else if(id==3){
    profile.value=true;
    home.value=false;
    videoTile.value=false;
  }else if(id==2){
    profile.value=false;
    home.value=false;
    videoTile.value=true;
  }
   console.log(id)
}
</script>

<template>
    <HomeView @nextPath="setPath" v-if="home"></HomeView>
    <ProfileView  @nextPath="setPath" v-if="profile"></ProfileView>
    <View  @nextPath="setPath" v-if="videoTile"></View>
</template>