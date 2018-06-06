<template>
  <div id="app">
    <h1 class="site-name">
      <a href="https://github.com/egoist">
        <img src="https://github.com/egoist.png" class="avatar" alt="egoist">
        EGOIST Rocks
      </a>
    </h1>
    <Projects :projects="projects" />
    <a class="more" href="https://github.com/egoist?tab=repositories">
      <MoreHorizontalIcon />
    </a>
  </div>
</template>

<script>
import { MoreHorizontalIcon } from 'vue-feather-icons'
import Projects from './components/Projects.vue'
import projects from '../projects.json'

export default {
  data() {
    return {
      projects
    }
  },

  components: {
    Projects,
    MoreHorizontalIcon
  }
}
</script>

<style>
body {
  background: rgb(95, 91, 212);
  margin: 0;
  font-family: Source Sans Pro,Avenir,Helvetica Neue,Helvetica,Arial,sans-serif;
  font-size: 14px;
  line-height: 1.4;
  color: white;
}

* {
  box-sizing: border-box;
  font-weight: 300;
}

a {
  color: white;
}

#app {
  max-width: 70em;
  margin: 20px auto;
}

.site-name {
  font-size: 2rem;
}

.avatar {
  width: 32px;
  height: 32px;
  border-radius: 50%;
  margin-right: 10px;
  background: #eee;
}

.site-name a {
  text-decoration: none;
  display: flex;
  align-items: center;
}

.more {
  display: flex;
  margin: 20px 0;
  width: 100px;
  border: 1px solid rgba(255, 255, 255, 0.2);
  color: rgba(255, 255, 255, 0.2);
  border-radius: 3px;
  text-align: center;
  justify-content: center;
  align-items: center;
  transition: border-color .3s ease-in-out;
  height: 26px;
}

.more:hover {
  border-color: rgba(255, 255, 255, 0.5);
  color: rgba(255, 255, 255, 0.5);
}
</style>