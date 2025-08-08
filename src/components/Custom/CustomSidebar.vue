<script setup>
import { ref } from 'vue'
import SidebarBadge from '@/components/Custom/SidebarBadge.vue'

const fontSize = ref(24)
const fontColor = ref('#000')
const format = ref('svg')
</script>

<template>
  <!--  <div class="drawer drawer-open">
      <input id="my-drawer-2" type="checkbox" class="drawer-toggle" />
      <div class="drawer-side">
        <label for="my-drawer-2" aria-label="close sidebar" class="drawer-overlay"></label>
        <ul class="menu bg-base-200 text-base-content min-h-full w-80 p-12">
          <li>
            <label class="input">
              <SidebarBadge title="Icon Size"/>
              <input type="text" class="grow" placeholder="" v-model="fontSize" />
            </label>
          </li>
          <li>
            <label class="input">
              <SidebarBadge title="Icon Color"/>
              <input type="text" class="grow" placeholder="" v-model="fontColor" />
            </label>
          </li>
          <li>
            <label class="input">
              <SidebarBadge title="Icon Format"/>
              <input type="text" class="grow" placeholder="" v-model="format" />
            </label>
          </li>
        </ul>
      </div>
    </div>-->

  <aside class="h-screen sticky top-0 overflow-y-auto w-60 py-6 px-4 bg-base-200">
    <a class="btn btn-ghost"> ⚡ Quick Customization </a>

    <ul class="menu px-0">
      <li class="menu-title">Style</li>
      <li>
        <label class="input">
          <SidebarBadge title="Icon Size" />
          <input type="text" class="grow" placeholder="" v-model="fontSize" />
        </label>
      </li>
      <li>
        <label class="input">
          <SidebarBadge title="Icon Color" />
          <input type="text" class="grow" placeholder="" v-model="fontColor" />
        </label>
      </li>
      <li>
        <label class="input">
          <SidebarBadge title="Icon Format" />
          <input type="text" class="grow" placeholder="" v-model="format" />
        </label>
      </li>

      <li class="menu-title">Ready Templates</li>
      <li>
        <a>
          <i class="fa-solid fa-map fa-fw"></i>
          Guides
        </a>
      </li>
      <li>
        <a>
          <i class="fa-solid fa-arrows-rotate fa-fw"></i>
          Hotspots
        </a>
      </li>
    </ul>
  </aside>
</template>

<style scoped>
li {
  margin-bottom: 10px;
}
</style>
