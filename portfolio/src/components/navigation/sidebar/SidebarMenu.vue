<template>
  <aside aria-hidden="true" tabindex="-1">
    <nav>
      <ol>
        <li><a href="#about">About</a></li>
        <li><a href="#experience">Experience</a></li>
        <li><a href="#work">Work</a></li>
        <li><a href="#contact">Contact</a></li>
      </ol>
      <a href="/resume.pdf" class="resume-link">Resume</a>
    </nav>
  </aside>
</template>

<script setup lang="ts">
const props = defineProps<{
  isActive?: Boolean;
}>();
</script>

<style scoped>
aside {
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
  transform: v-bind('props.isActive ? "translateX(0vw)" : "translateX(100vw)"');
  visibility: v-bind('props.isActive ? "visible" : "hidden"');
  transition: var(--transition);
}
nav {
  display: flex;
  -webkit-box-pack: justify;
  justify-content: space-between;
  -webkit-box-align: center;
  align-items: center;
  width: 100%;
  flex-direction: column;
  color: var(--lightest-slate);
  font-family: var(--font-mono);
  text-align: center;
}
ol {
  padding: 0px;
  margin: 0px;
  list-style: none;
  width: 100%;
}

ol li {
  position: relative;
  margin: 0px auto 20px;
  counter-increment: item 1;
  font-size: clamp(var(--fz-sm), 4vw, var(--fz-lg));
}
ol a {
  display: inline-block;
  text-decoration: none;
  text-decoration-skip-ink: auto;
  color: inherit;
  position: relative;
  transition: var(--transition);
  width: 100%;
  padding: 3px 20px 20px;
}
ol a:hover {
  color: var(--green);
}
ol li::before {
  content: "0" counter(item) ".";
  display: block;
  margin-bottom: 5px;
  color: var(--green);
  font-size: var(--fz-sm);
}

li {
  display: list-item;
  text-align: -webkit-match-parent;
}
nav .resume-link {
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
</style>
