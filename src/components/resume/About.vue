<template>
  <div v-if="aboutData" class="about">
    <div class="main-data">
      <div class="grade">
        <h1>{{aboutData.name}}</h1>
        <h2>{{aboutData.grade}}</h2>
      </div>
      <div class="contacts">
        <ul>
          <li
            v-for="contact in aboutData.contacts"
            :key="contact.name"
          >
            <img src={{contact.icon}}>
            <a>{{contact.data}}</a>
          </li>
        </ul>
      </div>
    </div>
    <div class="bio">{{aboutData.bio}}</div>
  </div>
</template>

<script>
export default {
  name: 'About',
  props: {
    aboutData: {
      type: Object,
    },
  },
};
</script>

<style scoped>
  .about {
    padding: 60px 40px;
    background-color: #F6F6F8;
  }
  .main-data {
      display: flex;
      justify-content: space-between;
  }
  h1 {
    font-size: 50px;
    text-align: left;
    color: #44b283;
  }
</style>
