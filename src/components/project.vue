<template>
  <div v-if="getScrolledInWindow > 200" class="project">
    <div
      :class="
        getScrolledInWindow > windowHeight / 4 &&
        getScrolledInWindow < windowHeight + 500
          ? 'reveal-animation'
          : 'reveal-animation'
      "
      class="left-side"
    >
      <div class="wrapper">
        <span class="project-number dynamic-text">
          {{ "0" + project.projNum }}
        </span>
      </div>
      <div class="wrapper">
        <span class="project-name dynamic-text">
          {{ project.name }}
        </span>
      </div>
      <div class="wrapper">
        <span class="description dynamic-text">
          {{ project.desc }}
        </span>
      </div>
      <div class="wrapper">
        <span>{{ project.date }}</span>
      </div>
      <div v-if="getScrolledInWindow < windowHeight * 1.5" class="wrapper">
        <span
          v-for="feature in project.features"
          :key="feature"
          class="features"
        >
          <li class="dynamic-text">• {{ feature }}</li>
        </span>
      </div>
    </div>
    <div
      v-for="(img, idx) in project.imgs"
      class="project-mockup"
      :key="img"
      :style="{
        transform: `translate(0px,-${
          (getScrolledInWindow / 10).toFixed() * (idx * 2 + 2)
        }%`,
        bottom: `-${120 + 40 * idx}%`,
      }"
      :class="img.split('-')[1]"
    >
      <a :href="project.githubLink" target="_blank">
        <img :src="getImage(img)" alt="" />
        <!-- <img :src="`@/assets/${img}.png`" alt="" /> -->
      </a>
    </div>
  </div>
</template>

<script>
export default {
  props: ["project", "scrollHeight", "windowHeight"],
  data() {
    return {
      scrolledInWindow: this.getScrolledInWindow,
    };
  },
  mounted() {
    console.log(
      `scrolled in ${this.project.projNum}, ${this.scrolledInWindow} `
    );
    console.log(
      `project ${this.project.name} window height: ${this.windowHeight}`
    );
  },
  computed: {
    getScrolledInWindow() {
      return this.scrollHeight - this.windowHeight * this.project.projNum;
    },
    getImage() {
      return (path) => new URL(`../assets/${path}.png`, import.meta.url).href;
    },
  },
};
</script>

<style></style>
