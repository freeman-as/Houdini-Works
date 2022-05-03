# Houdini Works 036

プロジェクトの説明

---

### メモ

- dopnetノードの`Simulation/Reset Simulation`でリセットすると設定変えてもシミュレーションに反映されない場合などに実行する
- Glue Constraintに使うラインには「`constraint_name`」「`constraint_type`」アトリビュートが必要
- `constraint_type`：拘束する設定
  `all`：すべて（位置・回転）を拘束
  `position`：位置を拘束
  `rotation`：回転を拘束
- `Glue ConstraintRelationship`の`Data Name`パラメーターで拘束ラインを設定
- プロパティ欄の紫色
  Pythonによる記述を表す
- `Time Dependent`
  ノードの時間依存（フレームが進むにつれて状態が変化する）
  Node Infoで確認できる（Yes / No）
  Yesなら毎フレーム処理が計算される
  一旦ネットワークの上流でYesになると下流のネットワークも継承してYesになるので、
  不要な場合は**`Time Shift(SOP)`**でフレームを固定する
- 

------

### 使用したノード (抜粋)

- **``Glue Constraint Relationship(DOP)``**
  拘束の強さを調整することができる
- **``Constraint Network(DOP)``**
  外部から拘束に使う形状を読込、オブジェクト同士の結束関係を定義
- **``SOP Solver(DOP)``**
  内部でSOPネットワークを組むことができる
  ジオメトリを時間とともに変化させるときに使用
- **``DOP Import(SOP)``**
  指定したDOPネットワークからオブジェクトを読み込む
- **``Time Shift(SOP)``**
  現在のフレームとは異なるフレームとして処理できる
  スタートフレームに固定するなど
- **``Connect Adjacent Pieces(SOP)``**
  隣接するパーツ間にラインを生成する
- **``Assemble(SOP)``**
  バラバラに分割されたジオメトリを個別の破片として扱えるように必要な処理を行う
- **``Glue Constraint Relationship(DOP)``**
  `Constaraint Network(DOP)`とセットで機能する
- 
- **``Assemble(SOP)``**
- **``Assemble(SOP)``**
- **``Assemble(SOP)``**
- 
