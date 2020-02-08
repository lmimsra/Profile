<template>
  <div>
    <article class="media">
      <div class="media-content">
        <div class="content">
          <p>
            <strong>{{ skillName }}</strong>
            <br />
            <progress
              class="progress is-primary"
              v-bind:value="skillLevel"
              max="100"
            ></progress>
          </p>
        </div>
      </div>
    </article>
  </div>
</template>

<script>
export default {
  name: 'SkillBar',
  props: {
    skillName: String,
    skillLevel: Number
  }
}
</script>

<style scoped lang="scss"></style>
