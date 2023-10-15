<script>
import mainHero from "../components/MainHero.vue";
import mainAdvantages from "../components/MainAdvantages.vue";
import mainCourses from "../components/MainCourse.vue";
import mainForm from "../components/MainForm.vue";
import test from "../components/test.vue";
import mainComments from "../components/MainComments.vue";
import AOS from "aos";
import "aos/dist/aos.css";
export default {
  components: {
    mainHero,
    mainAdvantages,
    mainCourses,
    mainComments,
    mainForm,
    test,
  },
  mounted() {
    AOS.init({
      // Global settings:
      offset: 120, // offset (in px) from the original trigger point
      delay: 0, // values from 0 to 3000, with step 50ms
      duration: 400, // values from 0 to 3000, with step 50ms
      easing: "ease", // default easing for AOS animations
      once: false, // whether animation should happen only once - while scrolling down
      anchorPlacement: "top-bottom", // defines which position of the element regarding to window should trigger the animation
    });
  },
};
</script>

<template>
  <test class="hero" />
  <!-- <mainHero /> -->
  <mainAdvantages id="advantages" />
  <mainCourses id="courses" />
  <mainComments id="comments" />
  <mainForm />
</template>

<style>
.hero {
  overflow: hidden;
}
</style>
