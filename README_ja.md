# Community detection of FF-data (2020)

リポジトリ内のデータセットは*FF-data*をクラスタリングした結果を保存しています。

*FF-data (Flow of Foreigners-Data)* とは、訪日外国人の国内移動経路を年ごとに集計したもので、国土交通省により[公開](https://www.mlit.go.jp/sogoseisaku/soukou/sogoseisaku_soukou_fr_000022.html)されています。
各データセットには47都道府県と、34の空港などの港が含まれています。2020年7月現在、2014年から2017年のデータが公開されています。
Memory networkと呼ばれる手法を用いてFF-dataをネットワーク情報として表し、map equation (Infomap)を用いてコミュニティ検出を行いました。

Memory networksとmap equationの詳細は以下の論文を参考にしてください。


[Rosvall, M., Esquivel, A., Lancichinetti, A. et al. "Memory in network flows and its effects on spreading dynamics and community detection," Nat. Commun. 5(1) (2014)](https://www.nature.com/articles/ncomms5630)


下の図は2017年の2nd-order Markov networksをmap equation用いて検出したモジュールの中で、大きさが上位4つのモジュールに含まれる、移動者数が特に多い経路を示しています。

<div align="center">
<img src="https://github.com/RyutaroHashimoto/community_detection_of_FF-data/blob/master/img/ModuleMapFigure.png"  width="500px" alt = "Japanese map showing a brief overview of the classified elements of traveler pathways.">
</div>

FF-dataやコミュニティ検出の方法のより詳細な情報は以下の論文を参考にしてください。

T. Kawamoto and R. Hashimoto, "Identifying macroscopic features in foreign visitor travel pathways," *in preparation* (2020).


##  コンテンツの内容
以下のファイルが含まれています。

1. Readme.txt 
2. Readme_ja.txt (本ファイル)
3. id_list.csv : データセットで使用されている都道府県と港の `id`のリスト。
	- `id` : 都道府県や港を表すコード
	- `name_j` : 日本語名
	- `name_e` : 英語名
4. 1st_order : map equationを用いた、1st-order Markov networksのコミュニティ検出の結果。
	- `id` : ノードのコード
	- `name` : ノードの英語名
	- `module_index` : ノードが所属するモジュールのインデックス。
5. 2nd_order : map equationを用いた、2nd-order Markov networksのコミュニティ検出の結果。
	- `prior_id` : prior nodeのコード
	- `prior_name` : prior nodeの英語名
	- `destination_id` : destination nodeのコード
	- `destination_name` : destination node の英語名

## 注釈
データセットの`module_index` は年ごとに独立に割り当てられています。
例えば1st-orderのデータセットでは、北海道は2014年と2015年両方ともでモジュール1に属しています。しかし、 これは北海道が2年間同じモジュールに所属しているという意味ではありません。

## 引用

このリポジトリのデータを利用する場合は、以下を引用してください。

T. Kawamoto and R. Hashimoto, "Identifying macroscopic features in foreign visitor travel pathways," *in preparation* (2020).