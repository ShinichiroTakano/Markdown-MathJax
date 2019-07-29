<template>
<div class="operation-instructions-area">
  <h2 class="p-block-ttl p-block-ttl-borderless">Instructions
    <div class="p-score">150Exp</div>
  </h2>
  <ol>
    <li v-for="instruction in instructions" :key="instruction">
      {{ instruction }}
    </li>
  </ol>
  <input id="hint-check" class="p-hint-button" type="checkbox" v-model="hintCheck">
  <label class="p-hint-label" for="hint-check"><i class="fas fa-lightbulb"></i>Hint</label>
  <div class="p-hint-content" v-if="hintCheck.length > 0">
    <p>ヒントヒントヒントヒントヒントヒントヒントヒントヒントヒントヒントヒントヒントヒントヒントヒントヒントヒントヒントヒントヒントヒントヒントヒントヒントヒントヒントヒントヒントヒントヒントヒントヒントヒントヒントヒントヒントヒントヒントヒントヒントヒントヒントヒントヒントヒントヒントヒントヒントヒントヒントヒントヒントヒントヒントヒントヒントヒントヒントヒントヒントヒントヒントヒントヒントヒントヒントヒントヒントヒントヒントヒント</p>
  </div>
</div>
</template>
<script>
export default {
  name: 'operation-instructions-area',
  props: {
    instructions: {
      type: Array,
      required: true
    }
  },
  data() {
    return {
      hintCheck: []
    }
  }
}
</script>
<style lang="scss" scoped>
$color-user: #1F3964;
$color-key: #F37726;
$color-key-light: #FFF8F3;
$transition: 400ms ease-in-out;
.operation-instructions-area {
  background-color: #fff;
}
.p-score {
  float: right;
  background-color: #fff;
  color: $color-user;
  height: 25px;
  margin: 5px;
  padding: 0 10px;
  border-radius: 15px;
}
.p-block-ttl {
  background-color: $color-user;
  color: #fff;
  height: 35px;
  line-height: 35px;
  padding-left: 20px;
  font-weight: normal;
  border-radius: 8px 8px 0 0;
}
.p-block-ttl-borderless {
  border-radius: 0;
}
.p-hint-button {
  display: none;
}
.p-hint-label {
  margin-top: 40px;
  color: $color-key;
  display: block;
  &:hover {
    cursor: pointer;
  }
}
.p-hint-content {
  padding: 0 10px;
  transition: .5s;
  background-color: $color-key-light;
  border-radius: 6px;
}
</style>
