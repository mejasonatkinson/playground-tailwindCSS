<script setup>
import ListSection from "../3-organisms/ListSection.vue";
import ListItem from "../3-organisms/ListItem.vue";
</script>

<template>
  <div class="col-span-6 h-screen py-2 px-4 border-r border-gray-300">
    <div class="mb-2 flex justify-between items-center items-center">
      <div class="flex justify-between items-center items-center">
        <svg
          fill="none"
          stroke="currentColor"
          stroke-width="1.5"
          viewBox="0 0 24 24"
          xmlns="http://www.w3.org/2000/svg"
          aria-hidden="true"
          class="w-8 mr-2 inline-block hover:cursor-pointer"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            d="M15.75 9V5.25A2.25 2.25 0 0013.5 3h-6a2.25 2.25 0 00-2.25 2.25v13.5A2.25 2.25 0 007.5 21h6a2.25 2.25 0 002.25-2.25V15M12 9l-3 3m0 0l3 3m-3-3h12.75"
          ></path>
        </svg>
        <svg
          fill="none"
          stroke="currentColor"
          stroke-width="1.5"
          viewBox="0 0 24 24"
          xmlns="http://www.w3.org/2000/svg"
          aria-hidden="true"
          class="w-10 hidden hover:cursor-pointer"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            d="M15.75 9V5.25A2.25 2.25 0 0013.5 3h-6a2.25 2.25 0 00-2.25 2.25v13.5A2.25 2.25 0 007.5 21h6a2.25 2.25 0 002.25-2.25V15m3 0l3-3m0 0l-3-3m3 3H9"
          ></path>
        </svg>
        <h2 class="text-2xl font-semibold inline-block">Today</h2>
      </div>
      <div class="flex justify-between items-center items-center">
        <svg
          fill="none"
          stroke="currentColor"
          stroke-width="1.5"
          viewBox="0 0 24 24"
          xmlns="http://www.w3.org/2000/svg"
          aria-hidden="true"
          class="w-6 inline-block mr-2 hover:cursor-pointer"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            d="M12 3c2.755 0 5.455.232 8.083.678.533.09.917.556.917 1.096v1.044a2.25 2.25 0 01-.659 1.591l-5.432 5.432a2.25 2.25 0 00-.659 1.591v2.927a2.25 2.25 0 01-1.244 2.013L9.75 21v-6.568a2.25 2.25 0 00-.659-1.591L3.659 7.409A2.25 2.25 0 013 5.818V4.774c0-.54.384-1.006.917-1.096A48.32 48.32 0 0112 3z"
          ></path>
        </svg>
        <svg
          fill="none"
          stroke="currentColor"
          stroke-width="1.5"
          viewBox="0 0 24 24"
          xmlns="http://www.w3.org/2000/svg"
          aria-hidden="true"
          class="w-6 inline-block hover:cursor-pointer"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            d="M6.75 12a.75.75 0 11-1.5 0 .75.75 0 011.5 0zM12.75 12a.75.75 0 11-1.5 0 .75.75 0 011.5 0zM18.75 12a.75.75 0 11-1.5 0 .75.75 0 011.5 0z"
          ></path>
        </svg>
      </div>
    </div>
    <div class="col-span-12">
      <div
        class="w-full px-5 py-4 bg-gray-100 text-gray-400 rounded-lg"
        contenteditable="true"
      >
        <div class="flex opacity-40">
          <svg
            fill="none"
            stroke="currentColor"
            stroke-width="1.5"
            viewBox="0 0 24 24"
            xmlns="http://www.w3.org/2000/svg"
            aria-hidden="true"
            class="w-5 mr-2"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="M12 4.5v15m7.5-7.5h-15"
            ></path>
          </svg>
          <p class="text-sm">Add task to "inbox" on "Today"</p>
        </div>
      </div>
    </div>
    <div class="col-span-12">
      <ListSection />
      <ListItem />
      <ListItem />
    </div>
    <div class="col-span-12">
      <ListSection />
      <ListItem />
      <ListItem />
    </div>
    <div class="col-span-12">
      <ListSection />
      <ListItem class="opacity-50" />
      <ListItem class="opacity-50" />
    </div>
  </div>
</template>

<style scoped></style>
