<template>
  <div id="content" v-html="compiledMarkdown"></div>
</template>
<script>
import marked from 'marked';
import aaa from 'mathjax'
export default {
  name: 'operation-description',
  props: {
    operationDescription: {
      type: String,
      required: true
    }
  },
  created() {
    console.log('aaa', aaa)
    console.log('MathJax', MathJax)
  },
  computed: {
    compiledMarkdown() {
      return 'avdvdvdvdv'
    }
  }
}
</script>
<style lang="scss" scoped>

</style>
