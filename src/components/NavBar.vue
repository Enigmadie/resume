<template>
  <nav>
    <ul>
      <li
        v-for="page in pages"
        :key="page.id"
      >
        <a
        v-bind:class="{ active: page.id === activePageId }"
          >{{page.name}}</a>
      </li>
    </ul>
  </nav>
</template>

<script>
export default {
  name: 'NavBar',
  data() {
    return {
      pages: [
        { id: 1, name: 'Я' },
        { id: 2, name: 'Портфолио' },
        { id: 3, name: 'Контакты' },
      ],
      activePageId: 1,
    };
  },
};
</script>

<style scoped>
  nav {
    height: 100%;
    width: 25vw;
    background-color: #33333C;
  }
  ul {
    position: relative;
    top: 40%;
  }
  li {
    font-size: 23px;
    line-height: 30px;
    font-weight: 500;
    color: #A6A8AF;
    list-style-type: none;
    margin-bottom: 25px;
    cursor: pointer;
  }
  a {
    padding: 3px;
  }
  a:hover {
    border-bottom: 2px solid #A6A8AF;
  }
  .active {
    color: #F5F6F9;
  }
  .active:hover {
    border-bottom: 2px solid #F5F6F9;
  }
</style>
