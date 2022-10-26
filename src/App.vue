<script setup lang="ts">
import MainView from "./views/MainView.vue";
import NavigationBar from "./components/navigation/NavigationBar.vue";
import SideElement from "./components/SideElement.vue";
</script>

<template>
  <NavigationBar />
  <main>
    <SideElement orientation="right">Right</SideElement>
    <SideElement orientation="left">Left</SideElement>
    <MainView />
  </main>
</template>

<style scoped></style>
