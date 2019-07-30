<template>
  <div class="operation-code-area">
    <div class="p-block-ttl">Script.py</div>
    <div><div id="operation-editor" /></div>
    <div class="p-button-group">
      <span class="c-button reset-button" @click="resetCode"><i class="fas fa-undo-alt"></i></span>
      <span class="c-button run-button" @click="runCode"><i class="fas fa-laptop-code run-icon"></i>Run</span>
      <span class="c-button submit-button" @click="submitCode"><i class="fas fa-paper-plane submit-icon"></i>Submit</span>
    </div>
  </div>
</template>
<script>
import 'ace-builds';
import 'ace-builds/webpack-resolver';
export default {
  name: 'operation-code-area',
  props: {
    questionSourceCode: {
      type: String,
      required: true
    }
  },
  data() {
    return {
      editor: null,
      isPending: false
    }
  },
  mounted() {
    this.editor = ace.edit("operation-editor", {
      mode: "ace/mode/python",
      theme: "ace/theme/tomorrow",
    })
    this.editor.setValue(this.questionSourceCode)
  },
  methods: {
    resetCode() {

    },
    runCode() {
      const currentCode = this.editor.getValue()
    },
    submitCode() {
    }
  }
}
</script>
<style lang="scss" scoped>
$color-user: #1F3964;
$color-key: #F37726;
#operation-editor {
  position: absolute;
  top: 35px;
  right: 0;
  bottom: 35px;
  left: 0;
}
.p-block-ttl {
  background-color: $color-user;
  color: #fff;
  font-weight: normal;
  border-radius: 8px 8px 0 0;
  height: 35px;
  display: flex;
  align-items: center;
  padding-left: 20px;
}
.p-button-group {
  position: absolute;
  bottom: 0;
  right: 0;
  display: flex;
}
.c-button {
  background-color: $color-key;
  border-radius: 8px;
  color: #fff;
  line-height: 30px;
  text-align: center;
  display: block;
  padding: 0 15px;
  font-weight: 500;
  box-sizing: border-box;
  margin-left: 30px;
  cursor: pointer;
}
.reset-button {
  border: 1px solid $color-key;
  background-color: #fff;
  color: $color-key;
}
.run-button {
  border: 1px solid $color-key;
  background-color: #fff;
  color: $color-key;
  width: 120px;
}
.submit-button {
  width: 120px;
}
.run-icon {
  margin-right: 10px;
}
.submit-icon {
  margin-right: 10px;
}
</style>
