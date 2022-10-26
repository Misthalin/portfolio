<template>
  <div orientation="right" class="sideElement">
    <div>
      <a
        v-if="props.orientation === 'right'"
        href="mailto:adrian.n.riise@gmail.com"
        >adrian.n.riise@gmail.com</a
      >
    </div>
  </div>
</template>

<script setup lang="ts">
const props = defineProps<{
  orientation?: String;
}>();
</script>

<style scoped>
.sideElement {
  width: 40px;
  position: fixed;
  bottom: 0px;
  left: v-bind('props.orientation === "left" ? "40px" : "auto"');
  right: v-bind('props.orientation === "left" ? "auto" : "40px"');
  z-index: 10;
  color: var(--lightest-slate);
}

.sideElement div {
  display: flex;
  flex-direction: column;
  -webkit-box-align: center;
  align-items: center;
  position: relative;
}

.sideElement div a {
  margin: 20px auto;
  padding: 10px;
  font-family: var(--font-mono);
  font-size: var(--fz-xxs);
  line-height: var(--fz-lg);
  letter-spacing: 0.1em;
  -webkit-writing-mode: vertical-rl;
  writing-mode: vertical-rl;
}

a {
  display: inline-block;
  text-decoration: none;
  text-decoration-skip-ink: auto;
  color: inherit;
  position: relative;
  transition: var(--transition);
}

a:hover {
  color: var(--aqua);
}

.sideElement div::after {
  content: "";
  display: block;
  width: 1px;
  height: 90px;
  margin: 0px auto;
  background-color: var(--light-slate);
}

@media (max-width: 1080px) {
  .sideElement {
    left: v-bind('props.orientation === "left" ? "20px" : "auto"');
    right: v-bind('props.orientation === "left" ? "auto" : "20px"');
  }

  @media (max-width: 768px) {
    .sideElement {
      display: none;
    }
  }
}
</style>
