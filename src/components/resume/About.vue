<template>
  <div v-if="aboutData" class="about">
    <div class="main-data">
      <div class="grade">
        <h1>{{aboutData.name}}</h1>
        <h2>{{aboutData.grade}}</h2>
      </div>
      <ul>
        <li
          v-for="contact in aboutData.contacts"
          :key="contact.name"
        >
          <img :src="contact.icon">
          <a>{{contact.data}}</a>
        </li>
      </ul>
    </div>
    <div class="bio">{{aboutData.bio}}</div>
    <div class="other-data">
      <div class="skills">
        <h3>Навыки</h3>
        <div>
          <h4>Технические</h4>
          <ul>
            <li
              v-for="techUnit in aboutData.skills.technical"
              :key="techUnit"
            >
              <p class="tech">{{techUnit}}</p>
            </li>
          </ul>
        </div>
        <div class="other-skills">
          <div>
            <h4>Другие</h4>
            <ul>
              <li
                v-for="otherUnit in aboutData.skills.other"
                :key="otherUnit"
              >
                <p>{{otherUnit}}</p>
              </li>
            </ul>
          </div>
          <div>
            <h4>Языки</h4>
            <ul>
              <li
                v-for="langUnit in aboutData.skills.languages"
                :key="langUnit"
              >
                <p>{{langUnit}}</p>
              </li>
            </ul>
          </div>
        </div>
      </div>
      <div class="education-wrapper">
        <h3>Образование и курсы</h3>
        <ul class="education">
          <li
            v-for="place in aboutData.education"
            :key="place.name"
          >
            <h5>{{place.name}}</h5>
            <p>{{place.subName}}</p>
            <p>{{place.year}}</p>
          </li>
        </ul>
      </div>
    </div>
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
    align-self: center;
    height: 100vh;
    background-color: #F6F6F8;
    max-width: 1500px;
    padding-top: 60px;
}
.main-data {
    display: flex;
    justify-content: space-between;
    margin-bottom: 40px;
}
.bio {
    padding: 50px 0;
    border-top: 1px solid #d0cfd4;
    border-bottom: 1px solid #d0cfd4;
}
h1 {
    font-size: 53px;
    word-spacing: -9px;
    color: #44b283;
    text-transform: uppercase;
}
li {
    display: flex;
    align-items: flex-start;
    margin-bottom: 8px;
}
li img {
    width: 22px;
    height: 22px;
    margin-right: 5px;
}
ul {
    margin-right: 30px;
}
.education {
    margin: 30px 40px 60px 0;
}
.other-data {
    padding-top: 37px;
    padding-left: 30px;
    display: flex;
    justify-content: space-between;
}
.education li {
    display: flex;
    flex-direction: column;
    margin-bottom: 25px;
    max-width: 300px;
}
.education li p:last-child {
    color: grey;
    margin-top: 6px;
}
h5 {
    margin-bottom: 9px;
    font-size: 16px;
}
h3 {
    margin-left: -15px;
    padding-left: 7px;
    font-size: 25px;
    color: #44b283;
    border-left: 8px solid #44b283;
    text-transform: uppercase;
}
h4 {
    margin: 30px 0 15px 0;
}
.other-skills {
    display: flex;
}
.skills {
    width: 500px;
    display: flex;
    flex-direction: column;
}
.skills h3 {
    align-self: flex-start;
}
.education-wrapper {
     margin-right: 8vw;
}
.tech {
    letter-spacing: 1px;
    line-height: 20px;
}
</style>
