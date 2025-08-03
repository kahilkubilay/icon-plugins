<script setup>
import { onMounted, ref } from 'vue'
import IconModal from '@/components/Icon/IconModal.vue'

const icons = ref([])

const fetchIcons = async () => {
  try {
    const response = await fetch('/data/icons.json')

    icons.value = await response.json()
  } catch (error) {
    throw new Error(`Error while fetching icons. Details: ${error}`)
  }
}

onMounted(() => {
  fetchIcons()
})

const copyIcon = (icon) => {
  console.log('copyIcon...');

  navigator.clipboard.writeText(icon).then(() => {
    copied_modal.showModal();

    setTimeout(() => {
      copied_modal.close();
    }, 750)
  }).catch(err => {
    console.error('Failed to copy icon: ', err);

    setTimeout(() => {
      copied_modal.close();
    }, 750)
  })
}
</script>

<template>
  <div class="flex flex-wrap">
    <IconModal />
    <div
      v-for="icon in icons"
      :key="icon.id"
      class="card bg-base-100 hover:bg-[#F8F8F8] shadow-sm flex-auto"
      @click="copyIcon(icon.svg)"
    >
      <div class="card-body items-center text-center" :title="`click to copy ${icon.title}`">
        <div class="figure">
          <figure v-html="icon.svg"></figure>
        </div>
        <h2 class="card-title">{{ icon.title }}</h2>
      </div>
    </div>
  </div>
</template>

<style scoped>
.card {
  margin: 10px;
}

.card:hover {
  cursor: pointer;
}
</style>
