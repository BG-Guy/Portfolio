<template>
  <div class="portfolio-container">
    <div class="max-width-container">
      <div v-for="project in projects" :key="project">
        <Project
          :project="project"
          :scrollHeight="scrollHeight"
          :windowHeight="windowHeight"
        />
      </div>
    </div>
  </div>
</template>

<script>
import Project from "../components/project.vue";
export default {
  components: {
    Project,
  },

  data() {
    return {
      scrollHeight: 5,
      windowHeight: window.innerHeight,
      projects: [
        {
          name: "Worker",
          description:
            "Inspired By fiverr - end to end store for freelance services",
          features: ["End To End", "Web Sockets", "Vue", "Pixel Perfect"],
          githubLink: "https://worker-fiverr-prjj.herokuapp.com/#/",

          imgs: ["worker-mobile", "worker-tablet", "worker-tablet2"],
          projNum: 1,
        },
        {
          name: "Mister Bitcoin",
          description:
            "A full CRUD SPA. Send and Recieve bitcoin! authentication included",
          features: ["CRUD", "Authentication", "API", "CHART"],
          githubLink: "https://bg-guy.github.io/Mister-Bitcoin-Angullar/",

          imgs: [
            "MisterBitcoin-mobile",
            "MisterBitcoin-tablet",
            "MisterBitcoin-tablet2",
          ],
          projNum: 2,
        },
        {
          name: "Pacman",
          description: "Inspired by google - keeps and gmail",
          features: ["Vanilla Js", "Board-Game", "Timer", "Dynamic Images"],
          githubLink: "https://bg-guy.github.io/Pacman/",

          imgs: ["pacman-mobile", "pacman-tablet"],
          projNum: 3,
        },
        {
          name: "Minesweeper",
          description: "A classic board-game remastered",
          features: [
            "Vanilla Js",
            "Board-Game",
            "Timer",
            "Reccursive Functions",
          ],
          githubLink: "https://bg-guy.github.io/Mine-Sweeper/",

          imgs: ["minesweeper-mobile", "minesweeper-tablet"],
          projNum: 4,
        },
        {
          name: "appSus",
          description: "Inspired By Google - Keeps and Gmail",
          features: ["Dynamic Components", "Vue", "CRUDL"],
          githubLink: "https://bg-guy.github.io/appSus/",

          imgs: ["appsus-mobile", "appsus-tablet"],
          projNum: 5,
        },
        {
          name: "Chess",
          description: "A classic board-game of chess",

          features: ["Vanilla JS", "2-Side Timer", "Matrix Loops"],
          githubLink: "https://bg-guy.github.io/Chess/",

          imgs: ["chess-mobile", "chess-tablet"],
          projNum: 6,
        },
        {
          name: "Meme Generator",
          description: "A classic Meme Generator",

          features: ["Canvas", "Download", "Share", "Animations"],
          githubLink: "https://bg-guy.github.io/Meme-Generator/",

          imgs: ["memegenerator-mobile", "memegenerator-tablet"],
          projNum: 7,
        },
      ],
    };
  },

  mounted() {
    window.addEventListener("scroll", () => {
      this.scrollHeight = window.scrollY;
    });
  },

  computed: {},
};
</script>

<style></style>
