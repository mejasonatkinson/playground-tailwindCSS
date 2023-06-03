<script setup>
import ProfileIcon from "../1-atoms/icons/ProfileIcon.vue";
import TasksIcon from "../1-atoms/icons/TasksIcon.vue";
import CalendarIcon from "../1-atoms/icons/CalendarIcon.vue";
import InboxIcon from "../1-atoms/icons/InboxIcon.vue";
import NotificationIcon from "../1-atoms/icons/NotificationIcon.vue";
import HelpIcon from "../1-atoms/icons/HelpIcon.vue";
</script>

<template>
  <div class="col-span-2 h-screen bg-green-100">
    <nav class="h-screen relative">
      <ul class="absolute top-2 w-full">
        <li class="w-full h-10 p-2 mb-4 cursor-pointer">
          <ProfileIcon />
        </li>
        <li class="w-full h-10 p-2 mb-4 cursor-pointer">
          <TasksIcon />
        </li>
        <li class="w-full h-10 p-2 mb-4 cursor-pointer">
          <CalendarIcon />
        </li>
        <li class="w-full h-10 p-2 cursor-pointer">
          <InboxIcon />
        </li>
      </ul>
      <ul class="absolute bottom-8 w-full">
        <li class="w-full h-10 p-2 mb-4 cursor-pointer">
          <NotificationIcon />
        </li>
        <li class="w-full h-10 p-2 cursor-pointer">
          <HelpIcon />
        </li>
      </ul>
    </nav>
  </div>
</template>

<style scoped></style>
