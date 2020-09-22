<template>
  <div class="forIf">
    <h1>New For / If page</h1>
    <h1 v-if="awesome">Vue is visible!</h1>
    <h1 v-if="!awesome">Vue is visible!</h1>
    <h1 v-else-if="isElse">This is Else If</h1>
    <h1 v-else>Oh no 🥶</h1>
    <h1 v-show="ok">👨‍💻 👩‍💻</h1>
    <!-- v-else는 v-if가 안보이면 대신 보이는것 -->
    <!-- <img alt="Vue logo" src="../assets/logo.png" /> -->
    <HelloWorld msg="Welcome to Your Vue.js App" />
  </div>
</template>

<script>
// @ is an alias to /src
export default {
  name: "ForIF",
  components: {},
  data() {
    return {awesome: true};
  },
  computed: {},
  methods: {}
  };
</script>
<style lang="scss" scoped>

</style>