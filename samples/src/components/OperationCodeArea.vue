<template>
  <div class="operation-code-area">
    <div class="p-block-ttl">Script.py</div>
    <div><div id="operation-editor" /></div>
    <div class="p-button-group">
      <span class="c-button p-operation-button-reverse"><i class="fas fa-undo-alt"></i></span>
      <span class="c-button p-operation-button-reverse c-button120"><i class="fas fa-laptop-code"></i>Run</span>
      <span class="c-button p-operation-button"><i class="fas fa-paper-plane"></i>Submit</span>
    </div>
  </div>
</template>
<script>
import 'ace-builds';
import 'ace-builds/webpack-resolver';
export default {
  name: 'operation-code-area',
  mounted() {
    console.log('ace', ace)
    const editor = ace.edit("operation-editor", {
      mode: "ace/mode/python",
      theme: "ace/theme/tomorrow",
    })
  }
}
</script>
<style lang="scss" scoped>
$color-user: #1F3964;
$color-key: #F37726;
.operation-code-area {

}
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
  line-height: 40px;
  text-align: center;
  display: block;
  padding: 0 15px;
  font-weight: 500;
  box-sizing: border-box;
  margin-left: 30px;
}
.p-operation-button {
  width: 120px;
}
.p-operation-button-reverse {
  border: 1px solid $color-key;
  background-color: #fff;
  color: $color-key;
}
.c-button120{
  width: 120px;
}
</style>
