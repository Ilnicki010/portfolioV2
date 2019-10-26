<template>
  <div class="projectWrapper">
    <div>
      <nuxt-link to="/">Back</nuxt-link>
    </div>
    <div class="projectWrapper__image"></div>
    <div class="projectWrapper__content">
      <div class="content__field">
        <span>Project name</span>
        <h1>{{ name }}</h1>
      </div>
      <div class="content__field">
        <span>Description</span>
        <p>{{ description }}</p>
      </div>
      <div class="content__field">
        <span>Stack</span>
        <ul>
          <li v-for="item in stack" :key="stack.indexOf(item)">{{ item }}</li>
        </ul>
      </div>
    </div>
  </div>
</template>
<script>
import myProjects from '@/static/projects.json'
export default {
  asyncData({ params, env, error, query }) {
    const project = myProjects.find(
      (project) => String(project.nameID) === query.name
    )
    if (!project) {
      return error({ message: 'User not found', statusCode: 404 })
    }

    return project
  }
}
</script>
<style lang="scss" scoped></style>
