<template>
  <div id="operation-pane">
    <operation-description-area
      id="description-area-position"
      :title="title"
      :description="description"
      :dataSets="dataSets" />
    <operation-instructions-area
      id="instructions-area-position"
      :instructions="instructions" />
    <operation-code-area
      id="code-area-position" />
    <operation-console-area />
  </div>
</template>
<script>
import OperationDescriptionArea from './OperationDescriptionArea.vue'
import OperationInstructionsArea from './OperationInstructionsArea.vue'
import OperationCodeArea from './OperationCodeArea.vue'
import OperationConsoleArea from './OperationConsoleArea.vue'
export default {
  name: 'operation-pane',
  components: {
   OperationDescriptionArea,
   OperationInstructionsArea,
   OperationCodeArea,
   OperationConsoleArea
  },
  props: {
    questId: {
      type: Number,
      required: true
    },
    step: {
      type: Number,
      required: true
    },
    missionStep: {
      type: Number,
      required: true
    },
    tascStep: {
      type: Number,
      required: true
    },
    title: {
      type: String,
      required: true
    },
    description: {
      type: String,
      required: true
    },
    questionSourceCode: {
      type: String,
      required: true
    },
    answerTip: {
      type: Number,
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
    instructions: {
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
    },
    dataSets: {
      type: Array,
      required: true
    }
  }
}
</script>
<style lang="scss" scoped>
#operation-pane {
  display: grid;
  grid-template-rows: 60% 40%;
  grid-template-columns: 50% 50%;
  height: calc(100vh - 196px);
  grid-gap: 1%;
  padding-right: 2%;
  padding-left: 2%;
}
#description-area-position {
  grid-row: 1 / 2;
  grid-column: 1 / 2;
}
#instructions-area-position {
  grid-row: 2 / 3;
  grid-column: 1 / 2;
}
#code-area-position {
  grid-row: 1 / 2;
  grid-column: 2 / 3;
  position: relative;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
}
</style>

