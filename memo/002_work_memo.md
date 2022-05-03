# Houdini Works 002

### Reference

https://www.sidefx.com/tutorials/floating-particles-inside-of-an-animatedchanging-geometry-houdiniredshift-hip-file/

---

### Node

#### PolyExtrude

ポリゴンのフェースやエッジを押し出します
https://www.sidefx.com/ja/docs/houdini/nodes/sop/polyextrude.html

- Output Back
  裏面の描画

#### FLIP Object

FLIP Solverで動作するために必要なデータとパラメータを持ったパーティクル流体オブジェクトを作成
https://www.sidefx.com/ja/docs/houdini/nodes/dop/flipobject.html

- Closed Boundaries
  コリジョンが利くようになる

#### Static Object

SOPジオメトリから静的オブジェクトを作成
https://www.sidefx.com/ja/docs/houdini/nodes/dop/staticobject.html

- Collision Guide
  コリジョンを視覚的に確認できる
- Display Geometry
  使用するジオメトリの表示・非表示
- Invert Sign
  中が空洞のボックスが欲しい場合、1つのメソッドが他のボックスの内側に1つのボックスを構築して、 Laser Scan を使用しないことです。 より強固なメソッドは、内側のボックスを指定して、符号反転を使用することです。 これは、ボックスの外側のすべてを内側と見なし、より強固な Laser Scan メソッドを使用することができます
- Use Deforming Geometry
  オブジェクトのジオメトリをタイムステップ毎に、選択したSOPから引き出します。 SOPのジオメトリがアニメーションするなら、Staticオブジェクトのジオメトリもアニメーションします

#### Gas Particle Separate

ポイントポジションを調整することで隣接するパーティクルを分離するマイクロソルバ
https://www.sidefx.com/ja/docs/houdini/nodes/dop/gasparticleseparate.html

- Search Scale
  非常に近い隣接パーティクルを検索する時に、パーティクルのpscale値すべてに適用するスケール

#### Group

色々な条件に応じてポイント/プリミティブ/エッジ/頂点のグループを作成
https://www.sidefx.com/ja/docs/houdini/nodes/sop/groupcreate

- Keep in Bounding Regions / Enable
  境界ボリュームによるグループ化を有効
- Keep in Bounding Regions / Bounding Type
  境界ボリュームの形状

#### Dop Import

DOPシミュレーションから抽出した情報に基づいたジオメトリを取り込み、トランスフォーム
https://www.sidefx.com/ja/docs/houdini/nodes/sop/dopimport.html

- DOP Network
  トランスフォームとVelocityの情報の抽出元となるDOP Network
- Object Mask
  トランスフォームの抽出元となるDOP Network内のオブジェクトを指定

#### Blast

プリミティブ/ポイント/エッジ/ブレークポイントを削除
https://www.sidefx.com/ja/docs/houdini/nodes/sop/blast.html

- Delete Non Selected
  選択の意味を反転させます。選択したものを削除するのではなく、選択していないものを削除します。 これは、いくつかのジオメトリを孤立化させるのに非常に役に立ちます
- 

---

### One Point Memo

- Alt + 左クリック：キーフレーム打つ
- ビュー上でEnter：ジオメトリのハンドル操作
- FLIP Source と Flip ObjectのParticle Separationを同期させる
- 
- 
- 
