<template>
  <div class="resume">
    <About v-bind:aboutData="aboutData" />
    <Experience v-bind:expData="expData" />
  </div>
</template>

<script>
import aboutData from '@/mocks/bio-mock';
import expData from '@/mocks/exp-mock';
import About from '@/components/resume/About.vue';
import Experience from '@/components/resume/Experience.vue';

export default {
  name: 'Resume',
  components: {
    About,
    Experience,
  },
  data() {
    return {
      aboutData,
      expData,
    };
  },
};
</script>

<style scoped>
.resume {
  height: 100%;
  width: 100%;
  background-color: #F6F6F8;
  display: flex;
  flex-direction: column;
  justify-content: center;
}
</style>
