# バンディット問題
複数のアームと呼ばれる候補から最も良いものを逐次的に探す問題である。報酬を最大化するという点で、バンディット問題は強化学習のカテゴリに属する。バンディット問題の予測者は、限られた試行回数において得られる総報酬を最大化したい。 このとき、強化学習の普遍的なテーマである探索と活用のトレードオフが発生する。 短期的には、現時点での経験期待報酬が高いアームを引くのが良い（情報の活用）。 しかし、真の期待報酬が高いアームが、これまでたまたま運悪く少ない期待報酬しか得られていなかったということが低確率で発生する。 これを防ぐためには、すべてのアームを全体的に引く必要がある（情報の探索）。 予測者は、良いアルゴリズムに従って情報の活用と探索をバランスする必要がある。

<img width="681" alt="スクリーンショット 2022-03-11 16 53 46" src="https://user-images.githubusercontent.com/95354321/157825791-330ebdd9-fdbe-4e6a-820f-0537d0eb9902.png">

# メタバンディットについて

# 期待値の更新
## 定常環境
定常環境では、各腕の報酬期待値は固定である。したがって以下の手法を用いて各腕の期待値を更新する。

![\begin{align*}
a &= \frac{1}{n_i} \\
E &= (1 - a)E + aE
\end{align*}
](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle+%5Cbegin%7Balign%2A%7D%0Aa+%26%3D+%5Cfrac%7B1%7D%7Bn_i%7D+%5C%5C%0AE+%26%3D+%281+-+a%29E+%2B+aE%0A%5Cend%7Balign%2A%7D%0A)

## 非定常環境
非定常環境では、各腕の報酬期待値がランダムに入れ替わるため今までの期待値の更新ではうまく学習することができない。しかし、今回のメタバンディットにおいては定常環境における期待値の更新と同じ更新を使う。

![\begin{align*}
a &= \frac{1}{n_i} \\
E &= (1 - a)E + aE
\end{align*}
](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle+%5Cbegin%7Balign%2A%7D%0Aa+%26%3D+%5Cfrac%7B1%7D%7Bn_i%7D+%5C%5C%0AE+%26%3D+%281+-+a%29E+%2B+aE%0A%5Cend%7Balign%2A%7D%0A)

# 方策
* UCB1T
* Tompson Sampling
* RS
* RS-OPT
* SRS
* SRS-OPT

# 引用文献
[Hartland 06] C. Hartland, S. Gelly, N. Baskiotis, O. Teytaud, and M. Sebag, Multi-armed bandit, dynamic environments and meta-bandits, In: Advances in Neural
Information Processing Systems(NIPS-2006) Workshop, Online Trading Exploration Exploitation. (2006)<br>
[高橋 16] 高橋 達二,甲野 佑,浦上大輔:認知的満足化 限定合理性の強化学習における効用,人工知能学会論文誌,31(6), AI30-M_1-11. (2016)<br>
[甲野 13] 甲野 佑,高橋 達二:価値推論ヒューリスティクスとし
ての規準学習と忘却,In: Proceedings of 30th Japanese
Congnitive Science Society(JCSS), 74-79. (2013)<br>
[甲野 18] 甲野 佑, 高橋 達二: 満足化を通じた最適な自律探索,
2018 年度 人工知能学会全国大会 (第 32 回) 論文集 (2018)<br>
[加藤 21]
加藤暦雄，甲野祐，高橋達二：満足化方策における非満足均衡を用いた確率的方策の検証，2021年度~人工知能学会全国大会(第35回)~論文集，(2021)<br>
