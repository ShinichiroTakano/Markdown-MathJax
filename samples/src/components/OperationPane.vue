<template>
  <div id="operation-pane">
    <operation-description-area
      id="descriptionArea"
      :title="title"
      :description="description"
      :dataSets="dataSets" />
    <operation-instructionsArea
      id="instructionsArea"
      :instructions="instructions"
      :exp="exp"
      :choices="choices"
      :hints="hints"
      :selection="selection" />
    <operation-codeArea
      id="codeArea"
      :questionSourceCode="questionSourceCode"
      :questId="questId"
      :step="step"
      :missionStep="missionStep"
      :tascStep="tascStep" />
    <operation-console-area
      id="consoleArea" />
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
      type: String,
      required: true
    },
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
  grid-template-rows: 60% 1% 3% 1% 35%;
  grid-template-columns: 34% 1% 65%;
  grid-template-areas: 
            "descriptionArea       verticalBorder codeArea"
            "leftHorizontalBorder  verticalBorder codeArea"
            "instructionsArea      verticalBorder codeArea"
            "instructionsArea      verticalBorder rightHorizontalBorder"
            "instructionsArea      verticalBorder consoleArea";
  height: calc(100vh - 196px);
  padding-right: 2%;
  padding-left: 2%;
}
#description-area {
  grid-area: descriptionArea;
}
#instructionsArea {
  grid-area: instructionsArea;
}
#codeArea {
  grid-area: codeArea;
  position: relative;
}
#consoleArea {
  grid-area: consoleArea;
  overflow-y: scroll;
}
</style>

