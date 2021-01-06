<template>
  <div class="resume">
    <About v-bind:aboutData="aboutData" />
  </div>
</template>

<script>
import aboutData from '@/mocks/bio-mock';
import About from '@/components/resume/About.vue';

export default {
  name: 'Resume',
  components: {
    About,
  },
  data() {
    return {
      aboutData,
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
    justify-content: center;
  }
</style>
