# choreonoid_tactile_sensor_plugin

TactileSensorPlugin

## TactileSensorItem
接触センサのシミュレーション. 値を共有メモリに書き込む. シミュレーションエンジンが毎周期、接触情報削除->計算->接触情報書き込み、と処理を行うので、計算中に接触情報を読み込んでしまわないようにControllerItemの`isNoDelayMode: true`またはSimulatorItemの`controllerThreads: false`で使用せよ.

###parameters
- `shmKey` (int. default 6555): センサ値を書き込む共有メモリのキー.
- `configFileName` (String): センサの配置が書かれたyamlファイル名
```yaml
tactile_sensor:
  -
    name: tactile_sensor0 # センサの名前. 重複禁止
    link: RLEG_ANKLE_R # 親リンク名. (VRMLのjoint名ではなく、URDFのリンク名)
    translation: [ -0.065, -0.065, -0.06 ] # 親リンク相対
    rotation: [ 1, 0, 0, 0 ] # 親リンク相対. [axis-x, axis-y, axis-z, angle(rad)]
```
