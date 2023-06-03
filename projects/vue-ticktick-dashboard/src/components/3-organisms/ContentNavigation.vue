<script setup>
import ContentNavigationItem from "./ContentNavigationItem.vue";
import ContentNavigationSection from "./ContentNavigationSection.vue";
</script>

<template>
    <div
      class="col-span-10 h-screen p-2 border-r border-gray-300 overflow-y-scroll"
    >
      <ContentNavigationItem class="bg-green-100" />
      <ContentNavigationItem />
      <ContentNavigationItem />
      <div class="w-full border-b border-gray-300 my-2"></div>
      <ContentNavigationSection />
        <ContentNavigationItem />
        <ContentNavigationItem />
        <ContentNavigationItem />
      <ContentNavigationSection />
        <ContentNavigationItem />
        <ContentNavigationItem />
        <ContentNavigationItem />
      <ContentNavigationSection />
      <div class="p-2 bg-gray-300 text-grey-400 text-sm opacity-40">
        Display tasks filtered by list, date, priority, tag, and more
      </div>
      <div class="w-full border-b border-gray-300 my-2"></div>
      <ContentNavigationItem />
      <ContentNavigationItem />
    </div>
</template>

<style scoped></style>
