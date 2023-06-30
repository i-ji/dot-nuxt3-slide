<template>
  <div>
    <img :src="picture" alt="pic" width="256" height="192" />
  </div>
  <Button @prev="displayPrev" @next="displayNext" />
  <Thumbnail
    @slidePic0="displayPic0"
    :togglePic0="activePic0"
    @slidePic1="displayPic1"
    :togglePic1="activePic1"
    @slidePic2="displayPic2"
    :togglePic2="activePic2"
  />
</template>
<script setup>
import { ref } from "vue";
// 共通
const activePic0 = ref(true);
const activePic1 = ref(false);
const activePic2 = ref(false);
const picture = ref("../assets/pic0.png");

// サムネイル処理
const displayPic0 = () => {
  picture.value = "../assets/pic0.png";
  activePic0.value = true;
  activePic1.value = false;
  activePic2.value = false;
};
const displayPic1 = () => {
  picture.value = "../assets/pic1.png";
  activePic0.value = false;
  activePic1.value = true;
  activePic2.value = false;
};
const displayPic2 = () => {
  picture.value = "../assets/pic2.png";
  activePic0.value = false;
  activePic1.value = false;
  activePic2.value = true;
};

// ボタン処理
const displayPrev = () => {
  if (activePic0.value) {
    picture.value = "../assets/pic2.png";
    activePic0.value = false;
    activePic1.value = false;
    activePic2.value = true;
  } else if (activePic1.value) {
    picture.value = "../assets/pic0.png";
    activePic0.value = true;
    activePic1.value = false;
    activePic2.value = false;
  } else if (activePic2.value) {
    picture.value = "../assets/pic1.png";
    activePic0.value = false;
    activePic1.value = true;
    activePic2.value = false;
  }
};

const displayNext = () => {
  if (activePic0.value) {
    picture.value = "../assets/pic1.png";
    activePic0.value = false;
    activePic1.value = true;
    activePic2.value = false;
  } else if (activePic1.value) {
    picture.value = "../assets/pic2.png";
    activePic0.value = false;
    activePic1.value = false;
    activePic2.value = true;
  } else if (activePic2.value) {
    picture.value = "../assets/pic0.png";
    activePic0.value = true;
    activePic1.value = false;
    activePic2.value = false;
  }
};
</script>
