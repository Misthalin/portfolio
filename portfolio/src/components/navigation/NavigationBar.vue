<template>
  <header>
    <nav>
      <div>Adrian</div>
      <div>
        <ol>
          <li><span>01.</span> About</li>
          <li><span>02.</span> Experience</li>
          <li><span>03.</span> Work</li>
          <li><span>04.</span> Contact</li>
        </ol>
      </div>
    </nav>
  </header>
</template>

<script setup lang="ts"></script>

<style scoped>
header {
  height: 100px;
}
header {
  display: flex;
  -webkit-box-pack: justify;
  justify-content: space-between;
  -webkit-box-align: center;
  align-items: center;
  position: fixed;
  top: 0px;
  z-index: 11;
  padding: 0px 50px;
  width: 100%;
  height: var(--nav-height);
  background-color: rgba(10, 25, 47, 0.85);
  backdrop-filter: blur(10px);
  transition: var(--transition);
  filter: none !important;
  pointer-events: auto !important;
  user-select: auto !important;
}
nav {
  display: flex;
  -webkit-box-pack: justify;
  justify-content: space-between;
  -webkit-box-align: center;
  align-items: center;
  position: relative;
  width: 100%;
  color: var(--lightest-slate);
  font-family: var(--font-mono);
  counter-reset: item 0;
  z-index: 12;
}
ol {
  display: flex;
  -webkit-box-pack: justify;
  justify-content: space-between;
  -webkit-box-align: center;
  align-items: center;
  padding: 0px;
  margin: 0px;
  list-style: none;
}
</style>
