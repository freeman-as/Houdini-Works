# Houdini Works 014

プロジェクトの説明

------

## メモ

- **`FLIP Objectのみでもモデル形状から水のパーティクル作成が可能`**
- **`ワイヤーフレーム表示にするとシーンビューでの挙動を早くできる`**
- **`FLIP Solver/Volume Motionタブ`**
  `Velocity Transfer:`
  `Swirly Kernel`は小規模なものに向いている
  標準の`Splash Kernel`は海や川などの大きなFLIPシュミレーションに適している
  `Surface Tensionタブ`
  表面張力に関するパラメーター
- **`FLIP Solver/Particle Motionタブ`**
  パーティクルを制御するパラメーター
  `Add ID Attribute:`
  オンにすると水の各パーティクルにidアトリビュート(パーティクル固有の識別番号)を付与する
  標準の`Splash Kernel`は海や川などの大きなFLIPシュミレーションに適している
  `Surface Tensionタブ`
  表面張力に関するパラメーター
- **`Hiddenフラグ`**
  シュミレーション時にシーンビューで非表示にする
  計算結果には反映される
- **`キーフレームをManualに変更`**
  パラメーターを変更してもシーンが更新されなくなるので、キーフレーム作成時にシュミレーションの計算をしなくて済む
  シーンを更新する際は隣の更新ボタンを押す
- 

------

## 使用したノード (抜粋)

- **``Static Object (DOP)``**
  シュミレーション内にStatic(静的)オブジェクトを作成
- **``DOP Import Field (SOP)``**
  DOPシュミレーション結果を読み込む
- **``Particle Fluid Surface (SOP)``**
  レンダリングや確認用のメッシュとパーティクルを作成する
- **``Time Blend (SOP)``**
  前後の整数フレームから間の小数点フレームの結果を補間する
- **``Peak (SOP)``**
  ポイントやポリゴンを法線方向に動かせる
- **``Smooth (SOP)``**
  メッシュを滑らかにする
- **``Basic Liquid (Mat)``**
  標準的な水のマテリアル
- 