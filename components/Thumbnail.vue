<template>
  <div class="flex gap-2 mt-2">
    <img
      src="~/assets/pic0.png"
      alt="pic0"
      width="80"
      height="60"
      class="cursor-pointer opacity-40"
      :class="{ active: togglePic0 }"
      @click="slidePic0"
    />
    <img
      src="~/assets/pic1.png"
      alt="pic1"
      width="80"
      height="60"
      class="cursor-pointer opacity-40"
      :class="{ active: togglePic1 }"
      @click="slidePic1"
    />
    <img
      src="~/assets/pic2.png"
      alt="pic2"
      width="80"
      height="60"
      class="cursor-pointer opacity-40"
      :class="{ active: togglePic2 }"
      @click="slidePic2"
    />
  </div>
</template>
<script setup>
import { ref } from "vue";
const props = defineProps(["togglePic0", "togglePic1", "togglePic2"]);
const emit = defineEmits(["slidePic0", "slidePic1", "slidePic2"]);
const slidePic0 = () => {
  emit("slidePic0");
};
const slidePic1 = () => {
  emit("slidePic1");
};
const slidePic2 = () => {
  emit("slidePic2");
};
</script>
