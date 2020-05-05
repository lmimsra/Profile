<template>
  <div class="card">
    <header class="card-header">
      <p class="card-header-title">
        <span>{{ title }}</span>
        <span class="is-pulled-right">
          <span
            class="tag is-default tag-space"
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
      <p v-html="getMainContent()"></p>
    </div>
    <footer class="card-footer">
      <a :href="previewLink" class="card-footer-item" target="_blank">
        <span v-bind:class="{ 'null-target-link': isNullTargetLink }">
          Preview
        </span>
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
    previewLink: String || null,
    codeLink: String
  },
  methods: {
    getImage() {
      return require('@/assets/image/' + this.$props.valueOf().imageFile)
    },
    getMainContent() {
      const doc = this.$props.valueOf().description
      return doc.replace(/\n/g, '<br />')
    },
    getPreviewLink() {
      return this.$props.valueOf().previewLink === null
        ? '#'
        : this.$props.valueOf().previewLink
    }
  },
  computed: {
    isNullTargetLink() {
      return this.$props.previewLink === null
    }
  }
}
</script>
<style scoped lang="scss">
.tag-space {
  margin: 0 1px;
}
.null-target-link {
  color: black;
  text-decoration: line-through;
}
</style>
