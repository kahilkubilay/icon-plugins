<script setup>
import { h, createApp, ref } from 'vue'
import * as HeroIcons from '@heroicons/vue/24/outline'

const IconList = Object.keys(HeroIcons).map((iconName) => {
  return {
    title: iconName,
    component: HeroIcons[iconName],
  }
})

const downloadModalVisible = ref(false)

const getSvgContent = (iconComponent) => {
  const app = createApp({
    render: () => h(iconComponent),
  })

  const svgElement = document.createElement('div')
  app.mount(svgElement)

  const svgContent = svgElement.innerHTML
  app.unmount()
  return svgContent
}

const downloadIcon = (iconComponent, iconTitle) => {
  const svgContent = getSvgContent(iconComponent)
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

  downloadModalVisible.value = true
  setTimeout(() => {
    downloadModalVisible.value = false
  }, 1250)
}
</script>

<template>
  <div class="flex flex-wrap mt-10">
    <div
      v-for="(icon, index) in IconList"
      :key="index"
      class="card w-3xs bg-base-100 hover:bg-[#F8F8F8] shadow-sm flex-auto m-2 p-2 hover:cursor-pointer"
      @click="downloadIcon(icon.component, icon.title)"
    >
      <div class="card-body items-center text-center" :title="`click to download ${icon.title}`">
        <component :is="icon.component" class="h-6 w-6" />
        <p class="pt-2 text-sm">{{ icon.title }}</p>
      </div>
    </div>
  </div>

  <dialog v-if="downloadModalVisible" class="modal modal-bottom sm:modal-middle" open>
    <div class="modal-box absolute right-[100px] bottom-[50px]">
      <h3 class="text-lg font-bold">Congratulations, you have successfully downloaded 🎉🎉</h3>
    </div>
  </dialog>
</template>

<style scoped></style>
