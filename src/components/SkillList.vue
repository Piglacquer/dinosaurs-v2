<template>
  <div class="skills-list">
    <section class="skills-container hidden">
      <h4>Skills</h4>
      <ul class="skills-list">
          <li v-for='skill in dinosaur.skills'>{{skill}}</li>
      </ul>
    </section>
  </div>
</template>
<script>
export default {
  name: "SkillList",
  props: {
    dinosaur:{
      type: Object,
      required: true
    }
  }
}</script>
<style scoped>
.skills-list {
  list-style: none;
}
</style>
