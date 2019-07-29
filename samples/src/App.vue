<template>
  <div id="app">
    <operation-pane
      :instructions="['train.csvを読み込み、変数trainに代入しましょう', 'test.tsvを読み込み、変数testに代入しましょう', 'ファイル「sample.txt」を確認した上で、適切に引数を設定し、変数sampleに代入しましょう']"
      :dataSets="[{id: 1, name: 'Sample.txt', content: 'ああああああああああ'}, { id: 2, name: 'Sample1.txt', content: 'いいいいいいいいいい'}, { id: 3, name: 'Sample2.txt', content: 'うううううううううう'}]"
      title="データの読み込み⽅"
      description="それでは実際に重回帰モデルを作成していきましょう。モデルを作成する為には、まず目的変数と説明変数を表す変数を作成し、それをセットでモデル学習を行う必要があります。重回帰モデルをpythonで作成する場合には、まず`scikit-learn.linear_model`から`LinearRegression`をインポートします。
- aaaaa
 - bbbb
 - cccc
[Google先生](https://www.google.co.jp/)
```python
def factorial(x):
    if x == 0:
        return 1
    else:
        return x * factorial(x - 1)
```
|header1|header2|header3|
|:--|--:|:--:|
|align left|align right|align center|
|a|b|c|
> ご連絡いただいた、バグの件ですが、仕様です。
$$
    y = a_1X_1+a_2X_2+a_3X_3+...+a_0
$$
![mpg_displacement.png](https://static-dev.quest.signate.jp/tasks/21727805-1868-471d-93c4-4ec1d59bc932/01/mpg_displacement.png)
" />
  </div>
</template>

<script>
import OperationPane from './components/OperationPane.vue'

export default {
  name: 'app',
  components: {
   OperationPane
  }
}
</script>

<style>
</style>
