<template>
  <navigationTop />
  <heroHeader />
  <designArticle />
  <companyStrategy />
  <sliderPresentation />
  <scheduleCall />
</template>

<script setup>
import navigationTop from "@/components/navigationTop.vue";
import heroHeader from "@/components/heroHeader.vue";
import designArticle from "@/components/designArticle.vue";
import companyStrategy from "@/components/companyStrategy.vue";
import sliderPresentation from "@/components/sliderPresentation.vue";
import scheduleCall from "@/components/scheduleCall.vue";

{
  navigationTop,
    heroHeader,
    designArticle,
    companyStrategy,
    sliderPresentation,
    scheduleCall;
}
</script>

<style lang="scss">
@import "@/assets/scss/settings.scss";

body {
  font-family: "Commissioner", sans-serif;
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  width: 100%;
}

img {
  max-width: 100%;
}

#app {
  margin: 0;
  width: 100%;
}
</style>
