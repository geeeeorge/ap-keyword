# 基礎理論

## 集合と論理

- 差集合
- 対象差=排他的論理和
- カルノー図

## 情報理論と符号化

- 情報量
  - $I=-log_2P$
- 平均情報量
  - 曖昧さ，予測しにくさを表す
  - $H=\sum\{P×I\}$
- 情報源符号化
  - ハフマン符号化
    - 出現度に着目
  - ランレングス符号化
    - 冗長度に着目
- パルス符号変調(PCM: Pulse Code Modulation)
  - 標本化，量子化，符号化
  - DPCM，ADPCM

## オートマトン

- 順序機械
- 有限オートマトン
- プッシュダウンオートマトン
- チューリングマシン

## 形式言語

- 文脈自由文法(形式文法)
  - $G=\{N, T, P, S\}$
- 言語処理
  - 文字 < 字句(トークン) < 文 < 言語
- BNF記法
  - 構文規則の記法
  - 構文図
- 構文木
  - 構文解析法
  - 3つ組み，4つ組み，逆ポーランド表記法
- 正規表現

## グラフ理論

- 入次数，出次数，次数
- サイクリックグラフ
  - 有向グラフの話
  - トポロジカル順序
- 回路(circuit)と閉路(cycle)
  - 小道(trail)と経路(path)
- グラフの表現
  - 隣接行列，隣接リスト
- ダイクストラ法

## 確率と統計

- ベイズの定理
- マルコフ過程
  - 推移行列，2段階推移行列
- モンテカルロ法
- 正規分布
  - 標本平均の分布
    - $\bar{X}$ ~ $N(\mu, \frac{\sigma^2}{n})$
  - 標本合計の分布
    - $\sum x$ ~ $N(n\mu, n\sigma^2)$
  - 加法性

## 回帰分析

- 単回帰分析
  - 最小二乗法
  - 相関係数
- 重回帰分析
  - 最小二乗法
  - 単相関係数，偏相関係数
- ロジスティック回帰分析
  - 2値分類

## 数値計算

- 非線形方程式の数値的開放
  - 二分法
  - ニュートン法
  - はさみうち法
- 誤差
  - 丸め誤差
  - 情報落ち
  - 桁落ち
  - 打切り誤差
- 絶対誤差 $=$ |近似値 $-$ 真値|
- 相対誤差 $=$ |絶対誤差 $÷$ 真値|

## AI(人工知能)
