<script>

import { links } from './data/linkVideo.js';

import AppHeader from './components/AppHeader.vue';
import Jumbotron from './components/Jumbotron.vue';
import Intro from './components/Intro.vue';
import BannerCards from './components/BannerCards.vue';

export default {
  data() {
    return {
    };
  },
  components: { AppHeader, Jumbotron, Intro, BannerCards },
  computed: {
    linksData() {
      return links;
    }
  }
}





</script>

<template>
  <AppHeader></AppHeader>
  <Jumbotron></Jumbotron>
  <BannerCards :links="linksData"></BannerCards>
  <Intro></Intro>
</template>

<style></style>
