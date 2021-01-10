<template>
  <div v-if="expData" class="exp">
    <div class="main-data">
      <ul class="work-data-wrapper">
        <li
          v-for="workUnit in expData.work"
          :key="workUnit.organization"
        >
          <h4>{{workUnit.organization}}</h4>
          <p>{{workUnit.position}}</p>
          <p>{{workUnit.date}}</p>
          <p>{{workUnit.description}}</p>
        </li>
      </ul>
      <ul class="project-data-wrapper">
        <li
          v-for="projUnit in expData.projects"
          :key="projUnit.organization"
        >
          <h4>{{projUnit.name}}</h4>
          <p>{{projUnit.git}}</p>
          <p>{{projUnit.source}}</p>
          <p>{{projUnit.description}}</p>
          <div class="tools">
            <span
              v-for="tool in projUnit.tools"
              :key="tool">
              {{tool}}
            </span>
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
    background-color: #F6F6F8;
  }
</style>
