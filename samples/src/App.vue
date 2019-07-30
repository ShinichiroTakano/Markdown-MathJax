<template>
  <div id="app">
    <operation-pane
      :instructions="['train.csvを読み込み、変数trainに代入しましょう', 'test.tsvを読み込み、変数testに代入しましょう', 'ファイル「sample.txt」を確認した上で、適切に引数を設定し、変数sampleに代入しましょう']"
      :dataSets="[{id: 1, name: 'Sample.txt', content: 'ああああああああああ'}, { id: 2, name: 'Sample1.txt', content: 'いいいいいいいいいい'}, { id: 3, name: 'Sample2.txt', content: 'うううううううううう'}]"
      :title="'データの読み込み⽅'"
      :description="sampleMarkDown"
      :questId="1"
      :step="1"
      :missionStep="1"
      :tascStep="1"
      :questionSourceCode="sampleCode"
      :answerTip="'aaaaaaaaaaaaaaa'"
      :exp="150"
      :choices="[{id: 1, sentence: 'aaaaa'},{id: 2, sentence: 'bbbbb'},{id: 3, sentence: 'ccccc'},]"
      :hints="['あああああ', 'いいいいい', 'ううううう']"
      :selection="{selection: false, multiple: false}" />
  </div>
</template>

<script>
import OperationPane from './components/OperationPane.vue'
import sampleMarkDown from './components/sampleMarkDown.js'
import sampleCode from './components/sampleCode.js'

export default {
  name: 'app',
  components: {
   OperationPane
  },
  data() {
    return {
      sampleMarkDown,
      sampleCode
    }
  }
}
</script>

<style>
</style>
