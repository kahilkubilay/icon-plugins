<script setup>
import HeaderComponent from '@/components/Header/HeaderComponent.vue'
import FooterComponent from '@/components/Footer/FooterComponent.vue'
import CustomSidebar from '@/components/Custom/CustomSidebar.vue'
</script>

<template>
  <!-- header -->
  <HeaderComponent />
  <div class="grid grid-cols-4">
    <div class="col-span-1">
      <!--  customization icons -->
      <CustomSidebar />
    </div>

    <!-- router content -->
    <div class="col-span-2">
      <RouterView />
    </div>
  </div>

  <!-- main content -->

  <!-- footer -->
  <!--  <FooterComponent />-->
</template>

<style scoped></style>
