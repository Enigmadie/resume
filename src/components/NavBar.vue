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
      ],
      activePageId: 1,
    };
  },
};
</script>

<style scoped>
  nav {
    position: relative;
    min-height: 100%;
    width: 25%;
    background-color: #33333C;
  }
  ul {
    position: fixed;
    top: 20%;
    left: 6%;
  }
  li {
    font-size: 23px;
    line-height: 30px;
    font-weight: 500;
    color: #A6A8AF;
    margin-bottom: 25px;
    cursor: pointer;
    text-align: center;
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
