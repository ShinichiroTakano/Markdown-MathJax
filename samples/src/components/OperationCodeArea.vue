<template>
  <div class="operation-code-area">
    <div class="p-block-ttl">Script.py</div>
    <div id="operation-editor" />
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
.operation-code-area {
  height: 60vh;
}
#operation-editor {
  position: absolute;
  top: 35px;
  right: 0;
  bottom: 100px;
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
</style>
