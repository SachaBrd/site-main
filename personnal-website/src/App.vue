<template>
  <!-- <div style="background-image:url(https://external-preview.redd.it/yfVNONOE-JRyWcswbTrxIOKN38w_gzqe4tJhyXkPgKU.jpg?auto=webp&s=9a7d5abd43b32d3ee01cc61c0dccbecf985480af); background-size: 100%; opacity: 0"> -->
  <div>
    <div class="flex flex-col justify-center items-center">
      <titleCard @closed="displayTitle = true" v-if="displayTitle"></titleCard>
      <aboutIntro :displayProject=this.displayProject @closed="displayIntro = false" v-if="displayIntro"></aboutIntro>
      <projectsInfo @closed="displayProject = false" v-if="displayProject"></projectsInfo>

      <!-- <router-link tag="li" class="col" class-active="active" to="/CNN" exact>CNN</router-link> -->

    </div>
    <menuBar @toggleTitle="displayTitle = !displayTitle" @toggleIntro="displayIntro = !displayIntro" @toggleProject="displayProject = !displayProject" :projectButton="displayProject" :infoButton="displayIntro" :titleButton="displayTitle"></menuBar>
  </div>
</template>

<script>
import aboutIntro from "./components/aboutIntro";
import projectsInfo from "./components/projectsInfo";
import titleCard from "./components/titleCard";
import menuBar from "./components/menuBar";
import "./index.css";

export default {
  name: "App",
  data() {
    return {
      displayIntro: true,
      displayProject: true,
      displayTitle: true,
    };
  },
  components: {
    aboutIntro,
    titleCard,
    menuBar,
    projectsInfo
  },
};
</script>