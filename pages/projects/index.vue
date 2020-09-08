<template>
  <div class="max-w-5xl">
    <StyledHeading tag="h2">Projects</StyledHeading>

    <nav>
      <label for="projectSort">Sort By</label>
      <select name="projectSort" id="projectSort">
        <option value="started_at">Start Date</option>
      </select>
    </nav>

    <ul>
      <li v-for="project in projects" :key="project.path">
        <h2>
          <nuxt-link :to="project.path">{{ project.title }}</nuxt-link>
        </h2>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  async asyncData({ $content, params }) {
    const projects = await $content('projects').fetch()

    return {
      projects,
    }
  },
}
</script>
