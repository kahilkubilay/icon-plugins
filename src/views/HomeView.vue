<script setup>
import SearchComponent from '@/components/Search/SearchComponent.vue'
import IconCapsule from '@/components/Icon/IconCapsule.vue'
</script>

<template>
  <main class="grid-rows-1 grid-cols-1 grid ">
    <!-- content -->
    <div>
      <IconCapsule />
    </div>

    <!-- search bar -->
<!--    <SearchComponent />-->
  </main>
</template>

<style scoped>
main {
  display: flex;
  justify-content: center;
  margin: 40px;
}
</style>
