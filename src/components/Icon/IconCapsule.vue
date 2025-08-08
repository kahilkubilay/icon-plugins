<script setup>
import { onMounted, ref } from 'vue'
import IconModal from '@/components/Icon/IconModal.vue'

const icons = ref([])

const fetchIcons = async () => {
  try {
    const response = await fetch('/data/homeIcons.json')
    icons.value = await response.json()
  } catch (error) {
    throw new Error(`Error while fetching icons. Details: ${error}`)
  }
}

onMounted(() => {
  fetchIcons()
})

const downloadIconAsImage = (svgContent, iconTitle) => {
  const svgBlob = new Blob([svgContent], { type: 'image/svg+xml;charset=utf-8' })
  const url = URL.createObjectURL(svgBlob)

  const img = new Image()
  img.onload = () => {
    const canvas = document.createElement('canvas')
    const ctx = canvas.getContext('2d')

    canvas.width = img.width
    canvas.height = img.height
    ctx.drawImage(img, 0, 0)

    canvas.toBlob((blob) => {
      if (blob) {
        const downloadUrl = URL.createObjectURL(blob)
        triggerDownload(downloadUrl, iconTitle)
        URL.revokeObjectURL(downloadUrl)
      }
    }, 'image/png')
  }

  img.src = url
}

const triggerDownload = (url, iconTitle) => {
  const a = document.createElement('a')
  a.href = url
  a.download = `${iconTitle}.png`
  document.body.appendChild(a)
  a.click()
  document.body.removeChild(a)

  download_modal.showModal()
  setTimeout(() => {
    download_modal.close()
  }, 750)
}
</script>

<template>
  <div class="flex flex-wrap">
    <IconModal />
    <div
      v-for="icon in icons"
      :key="icon.id"
      class="card bg-base-100 hover:bg-[#F8F8F8] shadow-sm flex-auto"
      @click="downloadIconAsImage(icon.svg, icon.title)"
    >
      <div class="card-body items-center text-center" :title="`click to download ${icon.title}`">
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
