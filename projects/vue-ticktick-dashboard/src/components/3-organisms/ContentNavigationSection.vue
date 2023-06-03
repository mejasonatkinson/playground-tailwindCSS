<script setup>
import CollapseArrowIcon from "../1-atoms/icons/CollapseArrowIcon.vue";
import AddIcon from "../1-atoms/icons/AddIcon.vue";
</script>

<template>
  <div
    class="w-full hover:bg-green-200 rounded-lg mb-1 cursor-pointer group"
  >
    <div class="flex items-center justify-between px-1 py-2 text-sm">
        <CollapseArrowIcon />
          Selection
        <AddIcon />
    </div> 
  </div>
</template>

<style scoped></style>
