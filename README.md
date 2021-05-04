# solafune 夜間光データからの土地価格予測  

## フォルダ構成  
* input  
  -> 必要データを格納（train, test, submission)
 
* notebook  
  ->jupyter-labで実施（RUN ALLで提出データまで作成します)
  
* output  
  ->提出データ格納
  
## 概要  
> 電気は人々の日々の生活に欠かせないインフラです。オフィス、商店街、街灯、スーパー、住宅街と生活の至る所に「光」を届けるための電気が行き渡っています。  
> 
> 特に夜間は光の量の違いが明確になります。人口が多い都市部では光の量も多く、地方や自然が多い地域では光の量は少なくなります。その特性を利用して、人工衛星から取得可能な夜間光のデータを活用するという取り組みが始まっています。夜間光データを経済指標として活用したり、経済動向を分析・予測するといった活用事例があります。  
> 
> 最近では新型コロナウイルスやその他の感染症の経済的影響を夜間光データから分析するなどの取り組みがありました。  
> 
> 今回のコンテストでは夜間光データを元に土地価格を予測するアルゴリズムを開発して頂きます。開発されたアルゴリズムは土地の評価や取引の際に役立てられることを想定しています。


## 結果  
Public：22位, Private：15位

## 特徴量  
* get_area_feature："SumLight"] / "MeanLight"
* get_agg_cumfeat_features
* Aggreration  
  * max, min, median, mean, std, var, max_min, q75_q25, q25 ,q50 ,q75  
  * PlaceID, Year、それぞれをGroup_keyに。
  * group内でのShift, diffをとることも実施
* get_place_id_vecs_features
* get_corr_features
* get_count63_feature


## モデル  
LightGBM, XGBoost, CatBoostのブレンディング（Weigthなどはいじらず）  
kfolf = 5  
