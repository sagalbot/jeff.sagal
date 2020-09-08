<template>
  <div class="flex flex-col md:flex-row">
    <header class="flex flex-col md:w-1/3 lg:px-20">
      <nuxt-link to="/" class="flex items-baseline">
        <h1 class="text-5xl font-black tracking-tight">jeff sagal</h1>
        <span class="text-purple-700 text-xl font-black">.dev</span>
      </nuxt-link>

      <nav>
        <ul class="flex space-x-5">
          <li class="text-lg"><nuxt-link to="/">Blog</nuxt-link></li>
          <li class="text-lg">
            <nuxt-link to="/projects">Projects</nuxt-link>
          </li>
        </ul>
      </nav>
    </header>

    <main class="flex w-full h-full md:w-2/3">
      <Nuxt />
    </main>
  </div>
</template>

<script>
export default {}
</script>
