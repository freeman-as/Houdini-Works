# Houdini Works 011

プロジェクトの説明

------

## メモ

- **`Advect`**
  流体の運動、移動

- 

------

## 使用したノード (抜粋)

- **``Name (SOP)``**
  `Name`アトリビュートの作成と変更に特化したノード
- **``Volume from Attribute (SOP)``**
  ポイントのアトリビュートの値をボリュームのボクセルにコピーすることが出来る
- **``Volume Visualization (SOP)``**
  シーンビューでボリューム情報を可視化できる
- **``Volume Blur (SOP)``**
  ボリュームの情報に対してぼかす機能
- **``SOP Vector Field (DOP)``**
  SOPネットワークのボリュームをDOPネットワークに読み込んで`Vector`フィールドを作成する
- **``Gas Advect Field (DOP)``**
  `Velocity`フィールドによって任意のフィールドを動かすことが出来る
- **``Gas Resize Fluid Dynamic (DOP)``**
  必要な部分だけをシュミレーションする。デフォルト設定でコネクトするだけで機能する
- **``Vortex Force (DOP)``**
  渦巻の力を作るフォースノード
  渦を指定するジオメトリが必要なので別途SOPで作る必要あり
- **``Vortex Force Attributes (SOP)``**
  `Vortex Force (DOP)`を使うのに必要なPointアトリビュートを作成するノード
- **``SOP Geometry (DOP)``**
  SOPからDOPへジオメトリを読み込む
- 