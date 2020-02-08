<template>
  <div class="card">
    <header class="card-header">
      <p class="card-header-title">
        <span>{{ title }}</span>
        <span class="is-pulled-right">
          <span
            class="tag is-default"
            v-for="(tag, index) in tags"
            v-bind:key="index"
          >
            {{ tag }}
          </span>
        </span>
      </p>
    </header>
    <div class="card-content">
      <figure class="image" v-if="imageFile !== null">
        <img v-bind:src="getImage()" alt="portfolioイメージ" />
      </figure>
      <p v-else>
        {{ description }}
      </p>
    </div>
    <footer class="card-footer">
      <a :href="previewLink" class="card-footer-item" target="_blank">
        Preview
      </a>
      <a :href="codeLink" class="card-footer-item" target="_blank">
        Source Code
      </a>
    </footer>
  </div>
</template>

<script>
export default {
  name: 'PortfolioCard',
  props: {
    title: String,
    tags: Array,
    imageFile: String || null,
    description: String,
    previewLink: String,
    codeLink: String
  },
  methods: {
    getImage() {
      return require('@/assets/image/' + this.$props.valueOf().imageFile)
    }
  }
}
</script>
<style scoped></style>
