<script setup>
import CalendarIcon from "../1-atoms/icons/CalendarIcon.vue";
import EllipsisIcon from "../1-atoms/icons/EllipsisIcon.vue";
</script>

<template>

<div
        class=" grid grid-cols-12 w-full hover:bg-green-200 rounded-lg mb-1 cursor-pointer group"
      ><!-- if selected: bg-green-100 -->
        <span class="col-span-2 p-2 flex items-center justify-center">
          <CalendarIcon v-if="1 == 1" />
        </span>
        <span class="col-span-8 p-2 text-sm flex items-center">Text</span>
        <span class="col-span-2 pt-1 pr-3 text-right flex justify-end items-center">
          <span class="text-sm group-hover:hidden">4</span>
          <EllipsisIcon />
        </span>
      </div>

</template>

<style scoped></style>
