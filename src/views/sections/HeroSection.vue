<template>
  <section>
    <h1>Hi, my name is</h1>
    <h2 class="big-heading">Adrian N. Riise.</h2>
    <h3 class="big-heading">I build things for the web.</h3>
    <p>
      I'm a web developer specializing in building exceptional web experiences.
      Currently, I'm focused on developing
      <a href="https://www.junglemap.com/" target="_blank" rel="noreferrer"
        >Junglemap's</a
      >
      NanoLearning platform.
    </p>
  </section>
</template>

<script setup lang="ts"></script>

<style scoped lang="less">
h1 {
  margin: 0px 0px 10px 4px;
  color: var(--green);
  font-family: var(--font-mono);
  font-size: clamp(var(--fz-sm), 5vw, var(--fz-md));
  font-weight: 400;
}

h3 {
  margin-top: 0px;
  color: var(--slate);
  line-height: 0.9;
}

p > a {
  display: inline-block;
  text-decoration: none;
  text-decoration-skip-ink: auto;
  position: relative;
  transition: var(--transition);
  color: var(--green);
  &::after {
    content: "";
    display: block;
    width: 0px;
    height: 1px;
    position: relative;
    bottom: 0.37em;
    background-color: var(--green);
    transition: var(--transition);
    opacity: 0.5;
  }
}
</style>
