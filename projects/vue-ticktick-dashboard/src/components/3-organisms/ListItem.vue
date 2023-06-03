<script setup></script>

<template>
  <div class="todo-list-section">
    <div
      class="w-full pl-5 group hover:bg-green-100 flex items-center relative todo-list-item"
      draggable="true"
    >
      <div
        class="absolute left-0 -ml-4 opacity-0 group-hover:opacity-100 cursor-move"
      >
        <svg
          fill="none"
          stroke="currentColor"
          stroke-width="1.5"
          viewBox="0 0 24 24"
          xmlns="http://www.w3.org/2000/svg"
          aria-hidden="true"
          class="w-4 inline-block"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            d="M3.75 6.75h16.5M3.75 12h16.5m-16.5 5.25h16.5"
          ></path>
        </svg>
      </div>
      <svg
        fill="none"
        stroke="currentColor"
        stroke-width="1.5"
        viewBox="0 0 24 24"
        xmlns="http://www.w3.org/2000/svg"
        aria-hidden="true"
        class="w-5 mr-2 inline-block hover:cursor-pointer hover:cursor-pointer"
      >
        <path
          stroke-linecap="round"
          stroke-linejoin="round"
          d="M19.5 14.25v-2.625a3.375 3.375 0 00-3.375-3.375h-1.5A1.125 1.125 0 0113.5 7.125v-1.5a3.375 3.375 0 00-3.375-3.375H8.25m2.25 0H5.625c-.621 0-1.125.504-1.125 1.125v17.25c0 .621.504 1.125 1.125 1.125h12.75c.621 0 1.125-.504 1.125-1.125V11.25a9 9 0 00-9-9z"
        ></path>
      </svg>
      <div
        class="w-full text-sm flex justify-between py-2 pr-1 border-b border-gray-300"
      >
        <span contenteditable="true">Note</span>
        <span class="cursor-pointer"
          ><span class="text-gray-400">List</span>
          <span class="text-red-500">Date</span></span
        >
      </div>
      <div
        class="absolute right-0 -mr-4 opacity-0 group-hover:opacity-100 cursor-pointer"
      >
        <svg
          fill="none"
          stroke="currentColor"
          stroke-width="1.5"
          viewBox="0 0 24 24"
          xmlns="http://www.w3.org/2000/svg"
          aria-hidden="true"
          class="w-4 inline-block"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            d="M6.75 12a.75.75 0 11-1.5 0 .75.75 0 011.5 0zM12.75 12a.75.75 0 11-1.5 0 .75.75 0 011.5 0zM18.75 12a.75.75 0 11-1.5 0 .75.75 0 011.5 0z"
          ></path>
        </svg>
      </div>
    </div>
  </div>
</template>

<style scoped></style>
