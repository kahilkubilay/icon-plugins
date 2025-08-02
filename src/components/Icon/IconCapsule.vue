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

const copyIcon = () => {
  copied_modal.showModal();
  console.log('copyIcon...')

  setTimeout(() => {
    // copied_modal.close();
  }, 500)
}
</script>

<template>
  <div class="flex flex-wrap">
    <IconModal />
    <div
      v-for="icon in icons"
      :key="icon.id"
      class="card bg-base-100 hover:bg-[#F8F8F8] shadow-sm flex-auto"
      @click="copyIcon()"
    >
      <div class="card-body items-center text-center">
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
