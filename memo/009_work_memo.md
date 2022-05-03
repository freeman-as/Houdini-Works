# Houdini Works 009

プロジェクトの説明

------

## メモ

- **`Fluid Source`**をH17以降で表示するには
  Houdini 17から非推奨になった
  以下のコマンドで隠されている`fluidsourceノード`を表示出来る
  https://www.sidefx.com/forum/topic/59092/?page=1#post-265812
  
  ```bash
  opunhide Sop fluidsource
  ```

- 何も接続しないNULLノードを作成してレンダーフラグを立てることでその階層で何もレンダリングしないように指定できる

- **`Source Volume`**をH17以降で表示するには
  Houdini 17から非推奨になった
  以下のコマンドで隠されている`sourcevolumeノード`を表示出来る
  https://www.sidefx.com/forum/topic/59092/?page=1#post-265812
  
  ```bash
  opunhide Sop sourcevolume
  ```

- シュミレーション領域を変更することで処理を軽くできる
  基本的には流体シュミレーションは領域が広いほど計算時間がかかるので、必要な範囲にシュミレーション領域を限ればそのぶん計算時間が短くて済む

- 

------

## 使用したノード (抜粋)

- **``Fluid Source (SOP)``**
  ジオメトリを流体シュミレーションで使用するのに適したボリュームに変換できる
  さまざまなタイプの流体シュミレーションで利用可能な発生源を作成可能
  一つで複数のボリュームが作成可能
- **``Source Volume (DOP)``**
  流体シュミレーションに必要なボリューム情報を読込み、シュミレーション内のフィールド情報として割り当てる
- **``Pyro Solver (DOP)``**
  煙の挙動を計算する。`Smoke Solver (DOP)`を機能拡張したもの
- **``Gas Resize Fluid Dynamic (DOP)``**
  シュミレーション領域を必要な範囲に調整する機能を持つ
- **``DOP Import (SOP)``**
  DOPネットワークからシュミレーション結果を読み込むことができる
- **``DOP I/O (SOP)``**
  DOPネットワークからフィールド情報を読み込む
  `DOP Import`を機能拡張したもので、複数のフィールド情報をDOPネットワークから読み込み、さらにそれをキャッシュファイルとして書き出し／読み込みができる
- 