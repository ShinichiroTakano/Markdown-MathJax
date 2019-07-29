<template>
  <div id="app">
    <operation-description-area
      :dataSets="[
        {
          id: 1,
          name: 'Sample.txt',
          content: 'ああああああああああ'
        },
        {
          id: 2,
          name: 'Sample1.txt',
          content: 'いいいいいいいいいい'
        },
        {
          id: 3,
          name: 'Sample2.txt',
          content: 'うううううううううう'
        }
      ]"
      description-title="データの読み込み⽅"
      operation-description="それでは実際に重回帰モデルを作成していきましょう。モデルを作成する為には、まず目的変数と説明変数を表す変数を作成し、それをセットでモデル学習を行う必要があります。重回帰モデルをpythonで作成する場合には、まず`scikit-learn.linear_model`から`LinearRegression`をインポートします。
- aaaaa
 - bbbb
 - cccc

* 順序無しリストのアイテム
 * サブアイテムはタブもしくは4つのスペースでインデントする
* 順序無しリストの別のアイテム


1. 番号付きリスト1
  1. 番号付きリスト1_1
  1. 番号付きリスト1_2
1. 番号付きリスト2
1. 番号付きリスト3

# 見出し1
## 見出し2
### 見出し3
#### 見出し4
##### 見出し5
###### 見出し6

    class User
        def 

normal *italic* normal
normal _italic_ normal

normal **bold** normal
normal __bold__ normal

normal ***bold*** normal
normal ___bold___ normal

***

___

---

*    *    *

[Google先生](https://www.google.co.jp/)
https://www.google.co.jp/

```python
def factorial(x):
    if x == 0:
        return 1
    else:
        return x * factorial(x - 1)
```

```
class Hoge
  def hoge
    print 'hoge'
  end
end
```

|header1|header2|header3|
|:--|--:|:--:|
|align left|align right|align center|
|a|b|c|


> お世話になります。xxxです。
> 
> ご連絡いただいた、バグの件ですが、仕様です。

$$
    y = a_1X_1+a_2X_2+a_3X_3+...+a_0
$$


`from sklearn.linear_model import LinearRegression`

`scikit-learn`でモデルを作成する際には、まずモデルを表す箱を準備し、その箱を表す変数へ代入する必要があります。具体的には、箱を表す変数名をmodelとした場合、下記のように記述します。

`model = LinearRegression()`

箱の準備が終わったら、いよいよモデルの学習です。モデルの学習には`fit`関数を使い、引数の中に、説明変数、目的変数の順番で記述をします。具体的には、説明変数を表す変数名をX、目的変数を表す変数名をyとすると、下記のように記述できます。

`model.fit(X,y)`

モデルの予測精度をさらに改善するために、説明変数の対数化による特徴量の生成を行なってみましょう。    
動画でも解説しましたが、目的変数と説明変数の散布図を描画したとき、指数関数のような分布となる場合に、説明変数を対数化することで直線的な分布に近づけることができ、線形回帰モデルへの当てはまりがよくなる可能性があります。  

では、実際に対数化を行なってみましょう。  
はじめに、目的変数mpgと説明変数displacementの散布図をもう一度確認します。  

![mpg_displacement.png](https://static-dev.quest.signate.jp/tasks/21727805-1868-471d-93c4-4ec1d59bc932/01/mpg_displacement.png)

指数関数のように、曲線を描くようなデータ分布となることがわかります。  
よって、説明変数displacementを対数化することでより直線的な分布に近づけることができそうです。  

対数化を行うには、`numpy`ライブラリの`log`関数を使用します。  
引数として、DataFrameの対数化したいカラムを与えます。

`np.log(DataFrameを代入した変数['対数化したいカラム名'])`

また、対数化したカラムは、DataFrameの新しいカラムとして追加しましょう。

`DataFrameを代入した変数['新たなカラム名'] = np.log(DataFrameを代入した変数['対数化したいカラム名'])`

もともとのDataFrameにはないカラム名を指定して値を代入した場合、新しいカラムとしてDataFrameに追加されます。" />
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
