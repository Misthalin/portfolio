<template>
  <OnClickOutside @trigger="close" class="hamburger-menu">
    <SidebarHamburgerButton
      :isActive="menuOpen"
      @click="menuOpen = !menuOpen"
    />
    <SidebarMenu :isActive="menuOpen" />
  </OnClickOutside>
</template>

<script setup lang="ts">
import { ref } from "vue";
import { OnClickOutside } from "@vueuse/components";
import SidebarHamburgerButton from "./SidebarHamburgerButton.vue";
import SidebarMenu from "./SidebarMenu.vue";

const menuOpen = ref<boolean>(false);

function close() {
  menuOpen.value = false;
}
</script>

<style scoped lang="less">
.hamburger-menu {
  display: none;
  @media (max-width: 768px) {
    display: block;
  }
}
</style>
