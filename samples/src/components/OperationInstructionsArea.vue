<template>
<div class="operation-instructions-area">
  <div class="instruction-title">Instructions
    <div class="p-score">{{exp}}Exp</div>
  </div>
  <ol>
    <li v-for="instruction in instructions" 
        :key="instruction"
        class="instruction-sentence">
      {{ instruction }}
    </li>
  </ol>
  <input id="hint-check" class="p-hint-button" type="checkbox" v-model="hintCheck">
  <label class="p-hint-label" for="hint-check"><i class="fas fa-lightbulb hint-label"></i>Hint</label>
  <div class="p-hint-content" v-if="hintCheck.length > 0">
    <ul>
      <li v-for="hint in hints" :key="hint" class="hint-sentence">{{hint}}</li>
    </ul>
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
    },
    exp: {
      type: Number,
      required: true
    },
    choices: {
      type: Array,
      required: true
    },
    hints: {
      type: Array,
      required: true
    },
    selection: {
      type: Object,
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
.instruction-title {
  background-color: $color-user;
  color: #fff;
  height: 35px;
  padding-left: 20px;
  font-weight: normal;
  display: flex;
  align-items: center;
}
.p-score {
  background-color: #fff;
  color: $color-user;
  height: 25px;
  padding: 0 10px;
  border-radius: 15px;
  margin-left: auto;
  margin-right: 20px;
}
.instruction-sentence:not(:first-child) {
  margin-top: 10px;
}
.p-hint-button {
  display: none;
}
.p-hint-label {
  margin-top: 20px;
  color: $color-key;
  display: block;
  &:hover {
    cursor: pointer;
  }
}
.hint-label {
  margin-right: 10px;
}
.p-hint-content {
  transition: .5s;
  background-color: $color-key-light;
  border-radius: 6px;
  padding: 5px;
}
.hint-sentence:not(:first-child) {
  margin-top: 10px;
}
</style>
