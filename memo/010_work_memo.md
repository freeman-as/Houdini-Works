# Houdini Works 010

プロジェクトの説明

------

## メモ

- **`fuel (燃料)`**
  炎では`density`の代わりに`fuel`を使用
  `fuel`ボリュームをシュミレーションで燃焼させて炎をつくる

- **`Pyro Source/Combustionタブ`**
  `Fuel`の燃焼を制御するパラメーター

- **`Ignition Template`**
  発火温度。`Temperature`がこの値を超えると`Burn`フィールドが作られる

- **`Burn Rate`**
  1秒間に燃やされる燃料の比率

- **`Fuel Inefficiency`**
  `Fuel`の燃え残り
  基本的に燃焼に使われた`Fuel`はそのぶん減るが、このパラメーターで指定した割合の`Fuel`は燃焼後もなくならない

- **`$SF`**：シュミレーションフレーム
  
  ```c++
  // 現在のフレームがシュミレーションのはじめかどうか判定
  $SF==1
  ```

- **`Combustion/Flamesタブ`**
  炎を制御するパラメーター

- **`Combustion/Smokeタブ`**
  燃焼によって発生する煙を制御

- 

------

## 使用したノード (抜粋)

- 