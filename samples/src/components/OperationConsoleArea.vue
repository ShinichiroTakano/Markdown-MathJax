<template>
  <div>
    <div class="p-block-ttl">output</div>
    <div class="p-block-console-inner">
    </div>
  </div>
</template>
<script>
export default {
  
}
</script>
<style lang="scss" scoped>
$color-user: #1F3964;
.p-block-ttl {
  background-color: $color-user;
  color: #fff;
  height: 35px;
  padding-left: 20px;
  font-weight: normal;
  border-radius: 8px 8px 0 0;
  display: flex;
  align-items: center;
}
.p-block-console-inner {
  overflow-y: scroll;
  padding: 20px;
  height: 100%;
}
</style>
