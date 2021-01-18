<template>
  <div ref="exp" v-if="expData" class="exp">
    <div>
    <h2>Опыт работы</h2>
    <ul class="work-data-wrapper">
      <li
        v-for="workUnit in expData.work"
        :key="workUnit.organization"
      >
        <h4>{{workUnit.organization}}</h4>
        <p>{{workUnit.date}}</p>
        <p>{{workUnit.position}}</p>
        <p>{{workUnit.description}}</p>
      </li>
    </ul>
    </div>
    <div>
    <h2>Проекты</h2>
    <ul class="project-data-wrapper">
      <li
        v-for="projUnit in expData.projects"
        :key="projUnit.organization"
      >
        <h4>{{projUnit.name}}</h4>
        <div>
          <a :href="projUnit.git" target="_blank">
            <img src="https://img.icons8.com/windows/64/000000/github.png"/>
          </a>
          <a :href="projUnit.source" target="_blank">
            <img src="https://img.icons8.com/windows/64/000000/domain.png"/>
          </a>
        </div>
        <p>{{projUnit.description}}</p>
        <div class="tools">
          <div
            v-for="tool in projUnit.tools"
            :key="tool">
            {{tool}}
          </div>
        </div>
      </li>
    </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Experience',
  props: {
    expData: {
      type: Object,
    },
  },
};
</script>

<style scoped>
.exp {
    width: 100%;
    align-self: center;
    background-color: #F6F6F8;
    display: flex;
    flex-direction: column;
    max-width: 1500px;
    height: 100%;
    padding: 20px 0 40px 0;
}
.exp > div {
    padding-left: 37px;
}
h2 {
    color: #44b283;
    border-left: 8px solid #44b283;
    font-size: 30px;
    padding-left: 7px;
    margin-bottom: 30px;
    text-transform: uppercase;
    margin-left: -15px;
}
ul {
    display: flex;
    flex-wrap: wrap;
    justify-content: flex-left;
    margin-bottom: 57px;
}
li {
    max-width: 340px;
    width: 100%;
    margin-right: 20px;
    margin-bottom: 40px;
}
.work-data-wrapper li p:nth-child(2) {
    color: grey;
    margin-bottom: 5px;
    font-size: 12.5px;
    font-style: italic;
}
.work-data-wrapper li p:nth-child(3) {
    margin-bottom: 8px;
    font-weight: 600;
    font-size: 14.5px;
}
h4 {
    font-size: 18px;
    margin-bottom: 7px;
}
.project-data-wrapper li div:nth-child(2) {
    display: flex;
}
.project-data-wrapper img {
    height: 32px;
    width: 32px;
}
.project-data-wrapper p {
    min-height: 88px;
}
.tools {
    display: flex;
    flex-wrap: wrap;
    margin-top: 11px;
}
.tools div {
    font-size: 14.8px;
    padding: 0.8px 3.5px;
    margin-right: 6px;
    margin-bottom: 6px;
    border: 1.5px solid #d0cfd4;
    border-radius: 9px;
    background-color: #E8E7E7;
}
a {
    display: block;
    color: inherit;
    text-decoration: none;
}
@media screen and (max-width: 1000px) {
    .exp {
        align-items: center;
    }
    .exp > div {
        display: flex;
        flex-direction: column;
        justify-content: center;
    }
    ul {

        justify-content: center;
    }
    .project-data-wrapper p {
        min-height: inherit;
    }
}
</style>
