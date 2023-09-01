<script setup>
import headerComponent from './headerComponent.vue';
import Footer from './Footer.vue';
import { ref } from 'vue';

var noOfLikes = ref(0)

var like = function () {

    noOfLikes.value++
}

var dislike = function () {
    if (noOfLikes.value > 0) {
        noOfLikes.value--;
    }
}



</script>

<template>
    <headerComponent fromWhat="f" @goToHome="$emit('nextPath', 1)" @goToProfile="$emit('nextPath', 3)" />
    <img src="../assets/download.png">
    <p class="videotitle">Tom & Jerry | Tom & Jerry in Full Screen | Classic Cartoon Compilation | WB Kids by WB Kids</p>
    <p class="views">2354289365 views</p>
    <p class="popular" v-show="noOfLikes > 10">Popular</p>
    <p class="trending" v-show="noOfLikes > 25">Trending</p>
    <p class="views">WbKids</p><button class="subs">SUBSCRIBE</button>
    <button class="first" @click="like()">LIKE {{ noOfLikes }}</button>&nbsp;&nbsp;
    <button class="button" @click="dislike()">DISLIKE</button>&nbsp;&nbsp;
    <button class="button">SHARE</button>

    <input type="text" class="commentSection" placeholder="Add a comment...">
    <Footer location="videoTile" />
</template>

<style scoped>
img {
    position: absolute;
    width: 800px;
    height: 400px;
    left: 220px;
    top: 169.67px;
}

.videotitle {
    margin-top: 586px;
    margin-bottom: 1rem;
    margin-left: 219px;
    color: white;
    font-size: 19px;
}

.views {
    font-size: 15px;
    margin-left: 219px;
}

.trending {
    margin-top: -33px;
    margin-left: 405px;
    color: hsl(101, 85%, 38%);
}

.popular {
    margin-top: -33px;
    margin-left: 347px;
    color: #CC0000;
}

.button {
    margin-top: 15px;
    height: 40px;
    width: 8%;
    background-color: #121212;
    border: 0.2px solid gray;
    color: white;
    font-weight: 600;
    border-radius: 3px;
    cursor: pointer;
}

.button:hover {
    background-color: #CC0000;
    color: aliceblue
}

.first {
    margin-left: 17%;
    margin-top: 15px;
    height: 40px;
    width: 8%;
    background-color: #121212;
    border: 0.2px solid gray;
    color: white;
    font-weight: 600;
    border-radius: 3px;
    cursor: pointer;
}

.first:hover {
    background-color: rgb(14, 192, 44);
    color: black;
}

.subs {
    position: absolute;
    left: 900px;
    bottom: 210px;
    background-color: #CC0000;
    border: none;
    border-radius: 3px;
    padding: 5px;
    padding-right: 10px;
    color: white;
    font-size: 17px;
    padding-left: 10px;
    cursor: pointer;
}

.commentSection {
    width: 61%;
    height: 33px;
    margin-left: -26%;
    color: white;
    background-color: #181818;
    border: 0.2px solid gray;
    border-radius: 0px;
    padding-left: 20px;
    position: absolute;
    align-items: center;
    bottom: 50px;
}

.commentSection::placeholder {
    color: white;
    font-size: 15px;
}
</style>