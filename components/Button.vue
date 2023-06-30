<template>
  <div class="flex gap-2 mt-2">
    <button
      class="w-32 border border-gray-300 rounded-md box-border text-center py-1"
      @click="prev"
    >
      ←
    </button>
    <button
      class="w-32 border border-gray-300 rounded-md box-border text-center py-1"
      @click="next"
    >
      →
    </button>
  </div>
</template>
<script setup>
const emit = defineEmits(["prev", "next"]);
const prev = () => {
  emit("prev");
};
const next = () => {
  emit("next");
};
</script>
