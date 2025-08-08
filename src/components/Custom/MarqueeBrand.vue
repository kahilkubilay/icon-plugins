<script setup></script>

<template>
  <div class="wrapper fadeout-horizontal">
    <div class="marquee-text">
      <div class="marquee-text-track">
        <p>JavaScript</p>
        <p>TypeScript</p>
        <p>CSS</p>
        <p>TailwindCSS</p>
        <p>Accessibility</p>
        <p>React</p>
        <p>Angular</p>
        <p aria-hidden="true">JavaScript</p>
        <p aria-hidden="true">TypeScript</p>
        <p aria-hidden="true">CSS</p>
        <p aria-hidden="true">TailwindCSS</p>
        <p aria-hidden="true">Accessibility</p>
        <p aria-hidden="true">React</p>
        <p aria-hidden="true">Angular</p>
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
  animation: marquee-move-text var(--speed, 10s) linear infinite
  var(--direction, forwards);
}

.wrapper {
  margin: 1em;
}

.marquee-text p {
  border: 3px solid black;
  background-color: #fff;
  border-radius: 999px;
  padding: 1rem 2.5rem;
  color: black;
}

@keyframes marquee-move-text {
  to {
    transform: translateX(-50%);
  }
}

.wrapper {
  max-width: 800px;
  margin: 0 auto;
  color: #fff;
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

