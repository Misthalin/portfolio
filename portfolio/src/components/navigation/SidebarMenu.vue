<template>
  <div class="hamburger-menu">
    <div>
      <button
        aria-label="Menu"
        class="hamburger-menu-button"
        @click="menuOpen = !menuOpen"
      >
        <div class="hamburger-box">
          <div class="hamburger-box-inner"></div>
        </div>
      </button>
      <aside aria-hidden="true" tabindex="-1" class="navigation-sidebar">
        <nav
          class="sidebar"
          :style="
            menuOpen
              ? 'transform: translateX(0vw); visibility: visible'
              : 'transform: translateX(100vw); visibility: hidden'
          "
        >
          <ol>
            <li><a href="#/about">About</a></li>
            <li><a href="#/experience">Experience</a></li>
            <li><a href="#/work">Work</a></li>
            <li><a href="#/contact">Contact</a></li>
          </ol>
          <a href="/resume.pdf" class="resume-link">Resume</a>
        </nav>
      </aside>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from "vue";
import SidebarHamburgerButton from "./SidebarHamburgerButton.vue";

const menuOpen = ref<boolean>(false);
</script>

<style scoped>
button {
  cursor: pointer;
  border: 0px;
  border-radius: 0px;
  appearance: auto;
  writing-mode: horizontal-tb !important;
  text-rendering: auto;
  letter-spacing: normal;
  word-spacing: normal;
  line-height: normal;
  text-indent: 0px;
  text-shadow: none;
  display: inline-block;
  text-align: center;
  align-items: flex-start;
  box-sizing: border-box;
  margin: 0em;
  padding: 1px 6px;
  border-width: 2px;
  border-style: outset;
  border-image: initial;
}
.hamburger-menu-button .hamburger-box {
  display: inline-block;
  position: relative;
  width: var(--hamburger-width);
  height: 24px;
}

.hamburger-menu-button .hamburger-box-inner {
  position: absolute;
  top: 50%;
  right: 0px;
  width: var(--hamburger-width);
  height: 2px;
  border-radius: var(--border-radius);
  background-color: var(--green);
  transition: transform 0.22s cubic-bezier(0.55, 0.055, 0.675, 0.19) 0s;
  transform: rotate(0deg);
}
.hamburger-menu-button .hamburger-box-inner::before {
  content: "";
  display: block;
  position: absolute;
  left: auto;
  right: 0px;
  width: var(--hamburger-width);
  height: 2px;
  border-radius: 4px;
  background-color: var(--green);
  transition-timing-function: ease;
  transition-duration: 0.15s;
  transition-property: transform;
  width: 120%;
  top: -10px;
  opacity: 1;
  transition: var(--ham-before);
}

.hamburger-menu-button .hamburger-box-inner::after {
  width: 80%;
  bottom: -10px;
  transform: rotate(0deg);
  transition: var(--ham-after);
}

.hamburger-menu-button .hamburger-box-inner::before,
.hamburger-menu-button .hamburger-box-inner::after {
  content: "";
  display: block;
  position: absolute;
  left: auto;
  right: 0px;
  width: var(--hamburger-width);
  height: 2px;
  border-radius: 4px;
  background-color: var(--green);
  transition-timing-function: ease;
  transition-duration: 0.15s;
  transition-property: transform;
}

.hamburger-menu {
  display: none;
}
.sidebar {
  display: flex;
  -webkit-box-pack: center;
  justify-content: center;
  -webkit-box-align: center;
  align-items: center;
  position: fixed;
  top: 0px;
  bottom: 0px;
  right: 0px;
  padding: 50px 10px;
  width: min(75vw, 400px);
  height: 100vh;
  outline: 0px;
  background-color: var(--light-navy);
  box-shadow: -10px 0px 30px -15px var(--navy-shadow);
  z-index: 9;
  transition: var(--transition);
}
.sidebar .resume-link {
  color: var(--green);
  background-color: transparent;
  border: 1px solid var(--green);
  border-radius: var(--border-radius);
  font-size: var(--fz-sm);
  font-family: var(--font-mono);
  line-height: 1;
  text-decoration: none;
  cursor: pointer;
  transition: var(--transition);
  padding: 18px 50px;
  margin: 10% auto 0px;
  width: max-content;
}

@media (max-width: 768px) {
  .hamburger-menu-button {
    display: flex;
    -webkit-box-pack: center;
    justify-content: center;
    -webkit-box-align: center;
    align-items: center;
    position: relative;
    z-index: 10;
    margin-right: -15px;
    padding: 15px;
    border: 0px;
    background-color: transparent;
    color: inherit;
    text-transform: none;
    transition-timing-function: linear;
    transition-duration: 0.15s;
    transition-property: opacity, filter;
  }
  .hamburger-menu {
    display: block;
  }
}
</style>
