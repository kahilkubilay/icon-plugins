<script setup>
import HeaderComponent from '@/components/Header/HeaderComponent.vue'
import FooterComponent from '@/components/Footer/FooterComponent.vue'
import CustomSidebar from '@/components/Custom/CustomSidebar.vue'
</script>

<template>
  <!-- header -->
  <HeaderComponent />
  <div
    class="grid min-h-dvh grid-cols-1 grid-rows-[1fr_1px_auto_1px_auto] lg:grid-cols-[var(--container-2xs)_2.5rem_minmax(0,1fr)_2.5rem] xl:grid-cols-[var(--container-2xs)_2.5rem_minmax(0,1fr)_2.5rem]"
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
