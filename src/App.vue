<template>
  <h1 v-text="text"></h1>
  <!-- <h1 v-show="isShowing"></h1> -->
  <!-- <h1 v-if="isShowing" v-html="title"></h1>
  <h3 v-else-if="isShowing === null">This is v-else-if</h3>
  <h2 v-else>This is v-else part</h2> -->
  <p>Something else</p>
</template>

<script>
export default {
  data(){
    return {
      title: "<h1>Hey</h1>",
      text: "Text",
      isShowing: false,
      count: 0,
    }
  }
}
</script>