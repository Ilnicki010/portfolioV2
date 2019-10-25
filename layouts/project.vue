<template>
  <div class="projectWrapper">
    <div>
      <nuxt-link to="/">Back</nuxt-link>
    </div>
    <div class="projectWrapper__image"></div>
    <div class="projectWrapper__content">
      <div class="content__field">
        <span>Project name</span>
        <h1>{{ project.name }}</h1>
      </div>
      <div class="content__field">
        <span>Description</span>
        <p>{{ project.description }}</p>
      </div>
      <div class="content__field">
        <span>Stack</span>
        <ul>
          <li v-for="item in project.stack" :key="item.indexOf">{{ item }}</li>
        </ul>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    project: {
      type: Object,
      default: null
    }
  }
}
</script>
<style lang="scss" scoped></style>
