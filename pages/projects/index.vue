<template>
  <div class="max-w-2xl md:pt-8">
    <StyledHeading tag="h2" class="mb-4">Projects</StyledHeading>

    <p class="text-gray-900 mb-4">
      It almost makes more sense to call this page The Graveyard! I start more
      things than I finish. If I can get another person involved, that's usually
      the fuel to take things to the finish line. That said, a lot of these
      projects were just to scratch my own itch and solve a small problem in my
      own day to day.
    </p>

    <nav>
      <label for="projectSort">Sort By</label>
      <select name="projectSort" id="projectSort">
        <option value="started_at">Start Date</option>
      </select>
    </nav>

    <ul class="prose">
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
