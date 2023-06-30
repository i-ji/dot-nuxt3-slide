<template>
  <div>
    <img :src="picture" alt="pic" width="256" height="192" />
  </div>
  <Button @prev="displayPrev" @next="displayNext" />
  <Thumbnail
    @slidePic="displayPic"
    :togglePic0="activePic0"
    :togglePic1="activePic1"
    :togglePic2="activePic2"
  />
</template>
<script setup>
import { ref } from "vue";
// 共通
const activePic0 = ref(true);
const activePic1 = ref(false);
const activePic2 = ref(false);
const pictures = ref([
  "../assets/pic0.png",
  "../assets/pic1.png",
  "../assets/pic2.png",
]);
let picture = ref(pictures.value[0]);
let currentPic = ref(0);

// アクティブクラスの真偽
const pic0 = () => {
  activePic0.value = true;
  activePic1.value = false;
  activePic2.value = false;
};

const pic1 = () => {
  activePic0.value = false;
  activePic1.value = true;
  activePic2.value = false;
};
const pic2 = () => {
  activePic0.value = false;
  activePic1.value = false;
  activePic2.value = true;
};

// サムネイル処理
const displayPic = (index) => {
  picture.value = pictures.value[index];
  currentPic.value = index;
  if (index === 0) {
    pic0();
  } else if (index === 1) {
    pic1();
  } else if (index === 2) {
    pic2();
  }
};

// ボタン処理
const displayPrev = () => {
  currentPic.value--;
  if (currentPic.value < 0) {
    currentPic.value = 2;
  }
  picture.value = pictures.value[currentPic.value];
  if (activePic0.value) {
    pic2();
  } else if (activePic1.value) {
    pic0();
  } else if (activePic2.value) {
    pic1();
  }
};

const displayNext = () => {
  currentPic.value++;
  if (currentPic.value > 2) {
    currentPic.value = 0;
  }
  picture.value = pictures.value[currentPic.value];
  if (activePic0.value) {
    pic1();
  } else if (activePic1.value) {
    pic2();
  } else if (activePic2.value) {
    pic0();
  }
};
</script>
