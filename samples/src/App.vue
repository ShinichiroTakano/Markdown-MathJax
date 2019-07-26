<template>
  <div id="app">
    <operation-description-area
      :operationDescription="'aaaaaaaaa'"
    />
  </div>
</template>

<script>
import OperationDescriptionArea from './components/OperationDescriptionArea.vue'
export default {
  name: 'app',
  components: {
   OperationDescriptionArea
  }
}
</script>

<style>
</style>
