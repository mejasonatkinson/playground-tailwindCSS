<script setup>
import NavigationTemplate from "../4-templates/NavigationTemplate.vue";
import ListTemplate from "../4-templates/ListTemplate.vue";
import DetailsTemplate from "../4-templates/DetailsTemplate.vue";
</script>

<template>
  <main>
    <div class="grid grid-cols-12 grid-rows-1 gap-0">
      <NavigationTemplate />
      <ListTemplate />
      <DetailsTemplate />
    </div>
  </main>
</template>

<style scoped></style>
