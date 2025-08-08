<script setup></script>

<template>
  <div class="search">
    <div class="search-capsule">
      <label class="input">
        <svg class="h-[1em] opacity-50" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24">
          <g
            stroke-linejoin="round"
            stroke-linecap="round"
            stroke-width="2.5"
            fill="none"
            stroke="currentColor"
          >
            <circle cx="11" cy="11" r="8"></circle>
            <path d="m21 21-4.3-4.3"></path>
          </g>
        </svg>
        <input type="search" class="grow" placeholder="Search" />
        <kbd class="kbd kbd-sm">⌘</kbd>
        <kbd class="kbd kbd-sm">K</kbd>
      </label>
    </div>
  </div>
</template>

<style scoped>
.search {
  position: absolute;
  bottom: 0;
  justify-content: center;
  width: 100%;
  text-align: center;
}

.search-capsule {
  width: 50%;
  background: #309898;
  padding: 10px 0 40px 0;
  position: relative;
  margin: 0 auto;
  border-radius: 150px 150px 0 0 ;
  border: 3px solid #FF9F00;
}
</style>
