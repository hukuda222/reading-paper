# A Discourse-Aware Attention Model for Abstractive Summarization of Long Documents

## タスク
文書要約

## 貢献点
CNN/DailyMailよりも数倍長いコーパスの作成
sectionを加味する階層attentionモデルの提案


## モデル
![](https://i.imgur.com/T23ll69.png)
attentionはBahdanauのattentionを使用しており、
copy mechanismは、するか、しないかの0,1で行なっている。

## コーパス
arXivとPubMedから論文の要約コーパスを作成した。
![](https://i.imgur.com/q0v0bQ8.png)


## 結果
![](https://i.imgur.com/KQN7r2t.png)
2つのコーパスにおいてSOTA。

## future works
ROUGEでしか評価していないので、人手評価したい。
