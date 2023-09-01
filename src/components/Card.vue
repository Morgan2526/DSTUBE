<template>
  <div class="grid-container">
    <div>
    <button class="videoButton" @click="getVideo()">
    <img class="thumbnail"  :src="videoThumbnail" :alt="videoTitle"/>
    </button>
    </div>
  <div>
    <button class="videoButton1" @click="getVideo()">
  	<p class="title">{{ videoTitle }}</p>
  	<p class="views">{{ videoViews }} views</p><br>
    </button>
      <div class="creator">
        <img v-bind:src="videoCreator" :alt="videoCreatorName" height="20"/>
         |  {{ videoProducer }}
      </div>
    <p class="discription">{{videoDiscription}}</p>
    <button :id="videoId" @click="remVideo()" class="buttons">REMOVE</button>
    </div>
</div>
</template>

<style>
.videoButton{
  background-color: #181818;
  border:none;
  cursor: pointer;
}

.videoButton1{
  background-color: #181818;
  border:none;
  cursor: pointer;
  text-align: left;
}

p{
    color: white;
}

a:link {
  text-decoration: none;
}

a:visited {
  text-decoration: none;
}

a:hover {
  text-decoration: none;
}

a:active {
  text-decoration: none;
}


.grid-container {
  display: grid;
  grid-template-columns: auto auto auto auto;
  gap: 20px;
  background-color: #181818;
  padding: 10px;
  align-items: left;
}

.grid-container > div {
  background-color: #181818;
  text-align: left;
  font-size: 27px;
}

.title{
    font-size: 19px; 
    color:white;
    text-align: left;
    font-weight: 300;
}

.views{
    color:white;
    font-size: 15px;
    text-align: left;
}

.creator{
    color:white;
    text-align: left;
}

.discription{
    font-size: 14px;
    color: white;
    text-align: left;
}

.buttons{
    background-color: #181818;
    color: white;
    border-radius: 5px;
    border: 1px solid gray;

    margin-left: 0px;
    padding-left: 12px;
    padding-right: 12px;
    padding-top: 5px;
    padding-bottom: 5px;
    cursor: pointer;
}

.thumbnail{
    width:370px ;
    height:260px;
    border-radius: 7px;
}
</style>

<script setup>
import { ref } from 'vue';



var props = defineProps({
  videoId:{
    type:Number,
    required:true
  },
  videoTitle:{
    type:String,
    required:true
  },
  videoCreator:{
    type:String,
    required:true
  },
  videoDiscription:{
    type:String,
    required:true
  },
  videoViews:{
    type:String,
    required:true
  },
  videoCreatorName:{
    type:String,
    required:true
  },
  videoProducer:{
    type:String,
    required:true
  },
  videoThumbnail:{
    type:String,
    required:true
  },
  videoSource:{
    type:String,
    required:true
  }
})

const emit = defineEmits(['remove','getVideo'])


function getVideo(){
  emit('getVideo',3);
}

function remVideo(){
  emit('remove',props.videoId)
}

</script>
