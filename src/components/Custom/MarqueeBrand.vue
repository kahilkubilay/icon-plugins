<script setup>
const templateList = [
  'JavaScript',
  'TypeScript',
  'Vue',
  'React',
  'Angular',
  'Svelte',
  'JavaScript',
  'TypeScript',
  'Vue',
  'React',
  'Angular',
  'Svelte',
]

const toggleAnimation = (state) => {
  const track = document.querySelector('.marquee-text-track')

  if (track) {
    track.style.animationPlayState = state ? 'running' : 'paused'
  }
}
</script>

<template>
  <div class="wrapper fadeout-horizontal mb-4 container mx-auto">
    <div class="marquee-text">
      <div
        class="marquee-text-track"
        @mouseover="toggleAnimation(false)"
        @mouseleave="toggleAnimation(true)"
      >
        <ul class="flex">
          <li v-for="template in templateList" class="marquee-capsule mr-4 p-1">
            <h4 class="component-preview-title mt-2 mb-1 text-lg font-semibold">
              <a href="#template">
                {{ template }}
              </a>
            </h4>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<style scoped>
.marquee-text {
  overflow: clip;
}

.marquee-text-track {
  display: flex;
  padding-left: 4.8rem;
  gap: 4.8rem;
  width: max-content;
  animation: marquee-move-text 15s linear infinite forwards;
}

.marquee-text .marquee-capsule {
  border-radius: 65px;
  width: 125px;
  text-align: center;
  background-color: #689B8A;
  color: #fff;
}

.marquee-text .marquee-capsule:hover {
  cursor: pointer;
  background-color: #280A3E;
  text-decoration: underline;
}

@keyframes marquee-move-text {
  to {
    transform: translateX(-50%);
  }
}

.fadeout-horizontal {
  mask-image: linear-gradient(
    to right,
    transparent,
    black 5rem,
    black calc(100% - 5rem),
    transparent
  );
}
</style>
