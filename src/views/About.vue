<template>
  <div class="about">
    <h1>This is an about page</h1>
    <h3>{{ title }}</h3>
    <!-- we can use v-if or v-show to control the element's visibilty -->
    <AboutComponent v-if="isComponentVisible" :msg="'Hey!'"></AboutComponent>
  </div>
</template>

<script>
import AboutComponent from "@/components/AboutComponent.vue";
export default {
  name: "About",
  components: { AboutComponent: AboutComponent },
  data() {
    return {
      title: "This is the title of About.vue!",
      isComponentVisible: true
    };
  }
};
</script>
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
</style>