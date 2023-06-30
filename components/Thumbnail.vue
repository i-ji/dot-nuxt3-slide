<template>
  <div class="flex gap-2 mt-2">
    <img
      src="~/assets/pic0.png"
      alt="pic0"
      width="80"
      height="60"
      class="cursor-pointer opacity-40"
      :class="{ active: togglePic0 }"
      @click="slidePic(0)"
    />
    <img
      src="~/assets/pic1.png"
      alt="pic1"
      width="80"
      height="60"
      class="cursor-pointer opacity-40"
      :class="{ active: togglePic1 }"
      @click="slidePic(1)"
    />
    <img
      src="~/assets/pic2.png"
      alt="pic2"
      width="80"
      height="60"
      class="cursor-pointer opacity-40"
      :class="{ active: togglePic2 }"
      @click="slidePic(2)"
    />
  </div>
</template>
<script setup>
import { ref } from "vue";
const props = defineProps(["togglePic0", "togglePic1", "togglePic2"]);
const emit = defineEmits(["slidePic"]);
const slidePic = (index) => {
  emit("slidePic", index);
};
</script>
