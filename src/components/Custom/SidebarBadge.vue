<script setup>
  const props = defineProps(['title']);

</script>
<template>
  <span class="badge badge-soft badge-success badge-sm whitespace-nowrap"
    >🪶
    {{ props.title }}
  </span>
</template>

<style scoped></style>
