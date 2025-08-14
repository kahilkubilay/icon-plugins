<script setup>
import HeaderComponent from '@/components/Header/HeaderComponent.vue'
import FooterComponent from '@/components/Footer/FooterComponent.vue'
import CustomSidebar from '@/components/Custom/CustomSidebar.vue'
</script>

<template>
  <!-- header -->
  <HeaderComponent />
  <div
    class="flex"
  >
    <div class="relative col-start-1 row-span-full row-start-1 max-lg:hidden">
      <!--  customization icons -->
      <CustomSidebar />
    </div>

    <!-- router content -->
    <div class="relative row-start-1 grid grid-cols-subgrid lg:col-start-3">
      <RouterView />
    </div>
  </div>

  <!-- footer -->
  <!--  <FooterComponent />-->
</template>

<style scoped></style>
