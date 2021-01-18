<template>
  <NavBar />
  <Resume />
</template>

<script>
import Resume from './components/resume/index.vue';
import NavBar from './components/NavBar.vue';

export default {
  name: 'App',
  components: {
    Resume,
    NavBar,
  },
};
</script>

<style>
#app {
    font-family: JetBrains Mono, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    display: flex;
    height: 100%;
    background-color: #F6F6F8;
}
* {
    list-style-type: none;
    text-align: left;
    box-sizing: content-box;
}
@media screen and (max-width: 1000px) {
    #app {
        flex-direction: column;
    }
}
</style>
