<template>
<div class="foot">
   <span v-if="location== 'home'" class="footing"> {{ videoCount }} videos are fetched</span>
   <span class="foots">@2023</span>
</div>
</template>

<style scoped>
.foot{
    position:fixed;
      bottom: 0px;
      width: 100%;
      margin: 0;
      background-color: #202020;
      height:25px;
      left: 0px;
      margin-left: 0; 
      display: inline-block;
      color:white;
}

.foots{
    position: absolute;
    margin-left: 640px;
    font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
}

.footing{
    position: absolute;
    margin-left: 20px;
    font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
}

p{
    color:white;
}
</style>

<script setup>
var prop = defineProps({
    videoCount:{
        type:Number
    },
    location:{
        type:String,
        required:true
    }
})
</script>