<template>
  <header>
    <nav class="navbar">
      <div class="navbar-logo"><img src="../../assets/logo.png" /></div>
      <div class="navbar-link-list">
        <ol>
          <li><a href="#/about">About</a></li>
          <li><a href="#/experience">Experience</a></li>
          <li><a href="#/work">Work</a></li>
          <li><a href="#/contact">Contact</a></li>
        </ol>
        <div>
          <a
            class="resume-button"
            href="/resume.pdf"
            target="_blank"
            rel="noopener noreferrer"
            >Resume</a
          >
        </div>
      </div>
      <SidebarMenu />
    </nav>
  </header>
</template>

<script setup lang="ts">
import SidebarMenu from "./sidebar/NavigationSidebar.vue";
</script>

<style scoped>
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
  background-color: var(--navy);
  backdrop-filter: blur(10px);
  transition: var(--transition);
  filter: none !important;
  pointer-events: auto !important;
  user-select: auto !important;
}
.navbar {
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
li {
  text-align: match-parent;
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
  color: var(--green);
}
.navbar-logo {
  font-family: "Brush Script MT", cursive;
  color: var(--green);
}
.navbar-link-list {
  display: flex;
  -webkit-box-align: center;
  align-items: center;
}
.navbar-link-list ol {
  display: flex;
  -webkit-box-pack: justify;
  justify-content: space-between;
  -webkit-box-align: center;
  align-items: center;
  padding: 0px;
  margin: 0px;
  list-style: none;
}
.navbar-link-list ol li {
  margin: 0px 5px;
  position: relative;
  counter-increment: item 1;
  font-size: var(--fz-xs);
}
.navbar-link-list ol li a {
  padding: 10px;
}
.navbar-link-list ol li a::before {
  content: "0" counter(item) ".";
  margin-right: 5px;
  color: var(--green);
  font-size: var(--fz-xxs);
  text-align: right;
}
.navbar-link-list .resume-button {
  color: var(--green);
  background-color: transparent;
  border: 1px solid var(--green);
  border-radius: var(--border-radius);
  padding: 0.75rem 1rem;
  font-family: var(--font-mono);
  line-height: 1;
  text-decoration: none;
  cursor: pointer;
  transition: var(--transition);
  margin-left: 15px;
  font-size: var(--fz-xs);
}
@media (max-width: 1080px) {
  header {
    padding: 0px 40px;
  }
}
@media (max-width: 768px) {
  .navbar-link-list {
    display: none;
  }
}
</style>
