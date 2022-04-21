<template>
  <div class="resume-container">
    <div class="max-width-container">
      <h1>ABOUT ME</h1>
      <p>
        Hi, Im Guy Buganim, 27 , A FullStack / Front-end Developer.<br />
        Im Coding Academy FullStack graduate. <br />
        Specialized in JS, CSS/SASS, HTML, AJAX, VUE3, REACT.JS, <br />
        Link for my latest project - An end-to-end seller and buyer store, with
        real time statistics and notifications, inspired by ‘Fiverr’ - Design
        100% by me . https://worker-fiverr-prjj.herokuapp.com/#/
      </p>
      <div class="exp-section">
        <ul>
          <h1>Experience</h1>
          <li v-for="job in jobs" :key="job">
            <h1>{{ job.name }}</h1>
            <h3>{{ job.date }}</h3>
            <p>{{ job.desc }}</p>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      jobs: [
        {
          name: "Combat engineer soldier",
          date: "2013 - 2016",
          desc: "‘DEKEL’ Platoon, 601.",
        },
        {
          name: "Partner, Technical support",
          date: "2017",
          desc: "Technical internet support, working with various softwares, creatively solving internet problems, while working under pressure, providing customer service, and selling products.",
        },
        {
          name: "Security guard at BGU university",
          date: "2019 - 2021",
          desc: "Since money was a problem - Tried to Learn FullStack development alone from the internet, Udemy, Lynda, YouTube courses in night shifts.",
        },
      ],
    };
  },
};
</script>

<style></style>
