<script setup>
import Card from './Card.vue';
import headerComponent from './headerComponent.vue';
import Footer from './Footer.vue';
import videos from '../assets/data.json';
import { ref } from 'vue';
import { computed } from '@vue/reactivity';



const content=ref(videos)

var ind = ref(0)

function giveInex(inde){
  console.log(inde)
  ind.value = inde;
}

var length=ref(videos.videos.length);
const emit = defineEmits(['nextPath']);

const removeVid =(id)=>{
  console.log(id,content)
 content.value.videos = content.value.videos.filter((video)=>
 {
    return video.id!=id
 })
  --length.value;
}



const home = 'home'
const a='a'

  const setNext = () =>{
    emit('nextPath',3 )
  }

</script>

<template >
  
  <header >
    <headerComponent @goToProfile="setNext" fromWhat="true"  />
  </header>  
  <main style="margin-top: 110px;">
    <div v-for="video in content.videos" :key="video.id" >
      <div :id="a+video.id">
      <Card @getVideo="$emit('nextPath',2)" @remove="removeVid" :videoId=video.id :videoSource=video.videoSource :videoTitle=video.videoTitle  v-bind:videoDiscription=video.videoDiscription v-bind:videoViews=video.videoViews v-bind:videoCreatorName=video.videoCreatorName v-bind:videoProducer=video.videoProducer v-bind:videoThumbnail=video.videoThumbnail :videoCreator=video.videoCreator></Card>
    </div>
    </div>
   </main>

   <footer>
    <Footer :location="home" v-bind:videoCount="length"></Footer>
   </footer>
 
</template>


