<template>
  <div>
    <div class="column is-half">
      <div class="box">
        <div class="content">
          <h4 class="title is-5">{{ title }}</h4>
          {{ about }}<br />
          ■ 使用技術<br />
          {{ technology }}<br />
          ■ 担当<br />
          {{ role }}<br />
          ■ 実績<br />
          {{ performance }}
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Resume',
  props: {
    title: String,
    about: String,
    technology: String,
    role: String,
    performance: String
  }
}
</script>

<style scoped></style>
