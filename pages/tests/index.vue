<template>
    <main
            v-if="testPosts"
            class="main"
    >
        <h1 class="title text-left">Tests</h1>
        <ul
                v-for="(projectPost, index) in testPosts"
                :key="index"
                class="articles"
        >
            <nuxt-link
                    class="article article--clickable"
                    :to="`projects/${projectPost.slug}`"
            >
                <h3 class="article-title">{{ projectPost.title }}</h3>
                <div class="mt-4 mb-2">
                    <h2 class="inline py-1 px-2 mr-1 bg-accent text-white font-medium rounded-sm dark:bg-accent">{{ projectPost.test_type }}</h2>
                    <p class="inline">{{ projectPost.description }}</p>
                </div>
            </nuxt-link>
        </ul>
    </main>
</template>
<script>
  export default {
    computed: {
      projectPosts() {
        return this.$store.state.testPosts
      }
    }
  }
</script>
