<template>
  <div class="projects">
    <div class="project" v-for="project in projects">
      <div class="name">{{ project.name }}</div>
      <div class="description">{{ project.description }}</div>
      <div class="meta">
        <span class="github" v-if="project.github">
          <a :href="`https://github.com/${project.github}`" target="_blank"><GithubIcon /></a>
        </span>
        <span class="website" v-if="project.website">
          <a :href="project.website" target="_blank"><LinkIcon /></a>
        </span>
      </div>
    </div>
  </div>
</template>

<script>
import { GithubIcon, LinkIcon } from 'vue-feather-icons'

export default {
  props: ['projects'],

  components: {
    GithubIcon,
    LinkIcon
  }
}
</script>

<style scoped>
.projects {
  display: flex;
  flex-wrap: wrap;
}

.project {
  border: 1px solid #ffffff0d;
  background: #ffffff0d;
  font-size: 1.4rem;
  padding: 10px;
  width: 25%;
  position: relative;
  transition: transform .3s ease-in-out;
}

.project:not(:nth-child(5n)) {
  margin-left: -1px;
}

.project:first-child {
  margin-left: 0;
}

.project:hover {
  transform: scale(1.2);
  z-index: 3;
  border-color: white;
  background: rgba(95, 91, 212, .7);
}

.name {
  font-size: 1.4rem;
}

.description {
  font-size: 15px;
  margin-top: 10px;
  font-style: italic;
}

.meta {
  margin-top: 20px;
}

.meta span {
  font-size: 14px;
}

.meta svg {
  width: 17px;
  height: 17px;
}

.meta a:hover {
  color: rgb(179, 177, 236);
}

@media screen and (max-width: 768px) {
  .project {
    width: 100%;
  }

  .project:hover {
    transform: scale(1);
  }

  .project:not(:nth-child(5n)) {
    margin-left: 0;
  }
}
</style>