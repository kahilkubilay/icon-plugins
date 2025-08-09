<script setup></script>

<template>
  <div class="flex flex-wrap">
    <div class="flex flex-col max-w-sm mr-4 mt-4">
      <div
        class="bg-[url('public/img/templates/logos/heroicons_logo.jpg')] bg-cover bg-center bg-no-repeat h-48"
      ></div>
      <div
        class="flex items-center gap-4 bg-base-200 py-4 px-6 font-bold text-md border-b-2 border-[#689B8A]"
      >
        <a
          href="https://heroicons.com/"
          class="group not-prose inline-flex items-center gap-1 pl-2 pr-0.5 py-1 rounded-md font-bold bg-inherit text-current text-lg hover:cursor-pointer"
        >
          heroicons
          <svg
            viewBox="0 0 24 24"
            class="size-5 stroke-[3px] fill-none stroke-current opacity-50 group-hover:opacity-100 transition-opacity duration-300 ease-in-out"
          >
            <line
              x1="5"
              y1="12"
              x2="19"
              y2="12"
              class="scale-x-0 translate-x-[10px] group-hover:translate-x-0 group-hover:scale-x-100 transition-transform duration-300 ease-in-out"
            />
            <polyline
              points="12 5 19 12 12 19"
              class="-translate-x-2 group-hover:translate-x-0 transition-transform duration-300 ease-in-out"
            />
          </svg>
        </a>
      </div>

      <!-- Content -->
      <div class="flex flex-col gap-6 bg-base-200 p-6 rounded-b-box">
        <span> Beautiful hand-crafted SVG icons, by the makers of Tailwind CSS. </span>

        <!-- Icons -->
        <div class="flex flex-col gap-2">
          <div class="flex gap-3 items-center text-sm">✨ React and Vue Libraries</div>
          <div class="flex gap-3 items-center text-sm">✨ 316 Icons</div>

          <button class="btn btn-primary">
            <svg
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 24 24"
              stroke-width="1.5"
              stroke="currentColor"
              class="size-6"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                d="m9 13.5 3 3m0 0 3-3m-3 3v-6m1.06-4.19-2.12-2.12a1.5 1.5 0 0 0-1.061-.44H4.5A2.25 2.25 0 0 0 2.25 6v12a2.25 2.25 0 0 0 2.25 2.25h15A2.25 2.25 0 0 0 21.75 18V9a2.25 2.25 0 0 0-2.25-2.25h-5.379a1.5 1.5 0 0 1-1.06-.44Z"
              />
            </svg>
            Download
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped></style>
