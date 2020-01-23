# code2seq: Generating Sequences from Structured Representations of Code

## タスク
ソースコードを入力として関数名や要約を生成するタスク

## 貢献点
抽象構文木を独自の方法でエンコードし、RNNを用いて関数名や要約を生成した

## モデル
ソースコードを先ず抽象構文木に変換する。
![](https://i.imgur.com/PlBsy9s.png)

木の葉と、別の葉を結ぶ系列全てをそれぞれ考える。
葉に相当するソースコードに実際に登場するトークンは、サブワードに分割してからそのembeddingしたものの要素和をとり、内点の系列はRNNでembeddingしている。
![](https://i.imgur.com/mX55t0T.png)

デコーダはluong attentionを用いたLSTMを用いている。

## 結果
githubのスター数上位のリポジトリから抽出したJavaのソースコードのコーパスと、C#のソースコードで実験を行なった。


![](https://i.imgur.com/Wk0dYUA.png)
3つの大きさのJavaコーパスでの関数名生成タスクの結果



![](https://i.imgur.com/CwvCnfg.png)
[Iyerらが2016年に提案したC#コーパス](https://www.aclweb.org/anthology/P16-1195.pdf)での、要約タスクのBLUEスコア比較
