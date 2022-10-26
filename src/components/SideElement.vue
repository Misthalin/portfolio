<template>
  <div orientation="right" class="sideElement">
    <div v-if="props.orientation === 'right'">
      <a href="mailto:adrian.n.riise@gmail.com">adrian.n.riise@gmail.com</a>
    </div>
    <div v-if="props.orientation === 'left'">
      <ul class="social__StyledSocialList-anu6nt-0 dVLQAC fade-enter-done">
        <li>
          <a
            href="https://github.com/misthalin"
            aria-label="GitHub"
            target="_blank"
            rel="noreferrer"
            ><svg
              xmlns="http://www.w3.org/2000/svg"
              role="img"
              viewBox="0 0 24 24"
              fill="none"
              stroke="currentColor"
              stroke-width="2"
              stroke-linecap="round"
              stroke-linejoin="round"
              class="feather feather-github"
            >
              <title>GitHub</title>
              <path
                d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22"
              ></path>
            </svg>
          </a>
        </li>
        <!-- <li>
          <a
            href="https://twitter.com/"
            aria-label="Twitter"
            target="_blank"
            rel="noreferrer"
            ><svg
              xmlns="http://www.w3.org/2000/svg"
              role="img"
              viewBox="0 0 24 24"
              fill="none"
              stroke="currentColor"
              stroke-width="2"
              stroke-linecap="round"
              stroke-linejoin="round"
              class="feather feather-twitter"
            >
              <title>Twitter</title>
              <path
                d="M23 3a10.9 10.9 0 0 1-3.14 1.53 4.48 4.48 0 0 0-7.86 3v1A10.66 10.66 0 0 1 3 4s-4 9 5 13a11.64 11.64 0 0 1-7 2c9 5 20 0 20-11.5a4.5 4.5 0 0 0-.08-.83A7.72 7.72 0 0 0 23 3z"
              ></path>
            </svg>
          </a>
        </li> -->
        <li>
          <a
            href="https://www.linkedin.com/in/adrianriise"
            aria-label="Linkedin"
            target="_blank"
            rel="noreferrer"
            ><svg
              xmlns="http://www.w3.org/2000/svg"
              role="img"
              viewBox="0 0 24 24"
              fill="none"
              stroke="currentColor"
              stroke-width="2"
              stroke-linecap="round"
              stroke-linejoin="round"
              class="feather feather-linkedin"
            >
              <title>LinkedIn</title>
              <path
                d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"
              ></path>
              <rect x="2" y="9" width="4" height="12"></rect>
              <circle cx="4" cy="4" r="2"></circle>
            </svg>
          </a>
        </li>
        <!-- <li>
          <a
            href="https://codepen.io/"
            aria-label="Codepen"
            target="_blank"
            rel="noreferrer"
            ><svg
              xmlns="http://www.w3.org/2000/svg"
              role="img"
              viewBox="0 0 24 24"
              fill="none"
              stroke="currentColor"
              stroke-width="2"
              stroke-linecap="round"
              stroke-linejoin="round"
              class="feather feather-codepen"
            >
              <title>CodePen</title>
              <polygon
                points="12 2 22 8.5 22 15.5 12 22 2 15.5 2 8.5 12 2"
              ></polygon>
              <line x1="12" y1="22" x2="12" y2="15.5"></line>
              <polyline points="22 8.5 12 15.5 2 8.5"></polyline>
              <polyline points="2 15.5 12 8.5 22 15.5"></polyline>
              <line x1="12" y1="2" x2="12" y2="8.5"></line>
            </svg>
          </a>
        </li> -->
      </ul>
    </div>
  </div>
</template>

<script setup lang="ts">
const props = defineProps<{
  orientation?: String;
}>();
</script>

<style scoped lang="less">
.sideElement {
  width: 40px;
  position: fixed;
  bottom: 0px;
  left: v-bind('props.orientation === "left" ? "40px" : "auto"');
  right: v-bind('props.orientation === "left" ? "auto" : "40px"');
  z-index: 10;
  color: var(--lightest-slate);
  & div {
    display: flex;
    flex-direction: column;
    -webkit-box-align: center;
    align-items: center;
    position: relative;
    & a {
      margin: 20px auto;
      padding: 10px;
      font-family: var(--font-mono);
      font-size: var(--fz-xxs);
      line-height: var(--fz-lg);
      letter-spacing: 0.1em;
      -webkit-writing-mode: vertical-rl;
      writing-mode: vertical-rl;
    }
    &::after {
      content: "";
      display: block;
      width: 1px;
      height: v-bind('props.orientation === "left" ? "167px" : "90px"');
      margin: 0px auto;
      background-color: var(--slate);
    }
  }
  @media (max-width: 1080px) {
    left: v-bind('props.orientation === "left" ? "20px" : "auto"');
    right: v-bind('props.orientation === "left" ? "auto" : "20px"');
  }
  @media (max-width: 768px) {
    display: none;
  }
}
ul {
  display: flex;
  flex-direction: column;
  -webkit-box-align: center;
  align-items: center;
  margin: 0px;
  padding: 0px;
  list-style: none;
}

li a svg {
  width: 20px;
  height: 20px;
}

svg .feather {
  fill: none;
}

a {
  display: inline-block;
  text-decoration: none;
  text-decoration-skip-ink: auto;
  color: inherit;
  position: relative;
  transition: var(--transition);
  &:hover {
    color: var(--aqua);
  }
}
</style>
