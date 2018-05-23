# Build Guide

## 部品
| 名前 | 数 |
|:-|:-|
| PCB | 2枚 | リバーシブルです
| プレート | 2セット |
| ProMicro | 2枚 |
| TRRSジャック | 2個 |
| TRRSケーブル | 1本 |
| タクトスイッチ | 2個 |
| ダイオード | 48本 |
| キースイッチ | 48個 |
| キーキャップ | 48個 |
| スペーサー M2 10mm | 8本 |
| ネジ M2 | 16本 |

![lrg_dsc03612](https://user-images.githubusercontent.com/736191/40373990-17bbb6ec-5e23-11e8-9a36-4016893d67cd.jpg)

## 実装

### TRRSジャック
写真の位置に設置してはんだ付けを行います。
![lrg_dsc03621](https://user-images.githubusercontent.com/736191/40375098-856a0aca-5e25-11e8-80c8-9bacaf7ab2fb.jpg)

TRRSジャックを設置した面の J1 および J3 をブリッジさせます。
はんだを多めに溶かすとブリッジがしやすくなります。
![lrg_dsc03627](https://user-images.githubusercontent.com/736191/40375334-40a9f9f8-5e26-11e8-85b5-863c82fcff76.jpg)

### ダイオード
写真の位置にダイオードを実装します。
どちらの面に実装するかは好みですが、Undergrow LEDを実装する場合は、干渉をさけるためTRRSジャックとは反対の面に実装することをおすすめします(写真のとおり)。
ダイオードは予めリードベンダー等で足を折っておくと綺麗に実装ができます。

![lrg_dsc03636](https://user-images.githubusercontent.com/736191/40375636-162edc92-5e27-11e8-8a1d-b6f0b2d0f0a0.jpg)

ダイオードには向きがあるので注意してください。

<- 実装後 | 実装前 ->

![lrg_dsc03636_sc](https://user-images.githubusercontent.com/736191/40375916-ee34983e-5e27-11e8-9871-83fc66706c4f.jpg)

### ピンヘッダ
ProMicro用のピンヘッダをTRRSジャックと同じ面に実装します。
この段階では __ProMicroは絶対に実装してはいけません__ 。
![lrg_dsc03648](https://user-images.githubusercontent.com/736191/40376274-e6fc64b0-5e28-11e8-84f2-b3a6fe936c20.jpg)

なおピンヘッダを実装する際は曲がってしまうことがよくあるので、下記のようにProMicroをはめた状態でマスキングテープで固定するとまっすぐに実装することが出来ます。
ついでにこの時点でピンヘッダの余分な足を切っておくとマスキングテープが貼りやすくなるのでおすすめです。
![lrg_dsc03650](https://user-images.githubusercontent.com/736191/40376576-9f5ab25a-5e29-11e8-8964-5750721bd61b.jpg)

###　タクトスイッチ(リセットスイッチ)
タクトスイッチをTRRSジャックと同じ面に実装します。
またプレートに干渉してしまうので余分な足は切っておきます。
![lrg_dsc03662](https://user-images.githubusercontent.com/736191/40376947-a03913d2-5e2a-11e8-8cad-b5af7de1e63f.jpg)

### キースイッチおよびトッププレート
キースイッチとPCBの間にトッププレートを挟んでTRRSジャックと反対の面に実装します。
写真のようにプレートにスイッチを全て付けてから実装してもいいですが、ポロポロと落ちてしまう場合はひとつひとつ実装するといいかもしれません。
![lrg_dsc03659](https://user-images.githubusercontent.com/736191/40377882-f4c82bd4-5e2c-11e8-9297-35312ac51d93.jpg)

### ProMicro
ProMicroを写真のとおりに実装します。
左右で向きが異なるので注意してください。
![lrg_dsc03664](https://user-images.githubusercontent.com/736191/40378122-96e1891a-5e2d-11e8-8507-8a7bbfb30bc2.jpg)

### ボトムプレート
左手側と右手側でボトムプレートの形状が異なります。
右手側はProMicroが出っ張っているため、MicroUSB部分が干渉しないように加工してあります。
写真のようにスペーサーとネジを付けます(お好みで四隅にゴム足を付けます)。

![lrg_dsc03699](https://user-images.githubusercontent.com/736191/40421857-41bfced8-5ec8-11e8-948c-e52313227dbb.jpg)

![lrg_dsc03706](https://user-images.githubusercontent.com/736191/40421545-40710fb6-5ec7-11e8-90fb-982ab76ec62c.jpg)

### キーキャップ
最後にキーキャップを付けて完成です。
![lrg_dsc03727](https://user-images.githubusercontent.com/736191/40422415-3a6dc9e4-5eca-11e8-956e-e07d1105848f.jpg)


### Underglow LED (オプション)

https://www.switch-science.com/catalog/1400/ 等のシリアルLEDテープを実装する場合は以下のように実装します。
ものによってVCCとGNDが反転しているものがあるので注意してください。

![led](https://user-images.githubusercontent.com/736191/40420981-21b60222-5ec5-11e8-9e1d-0ba6050762e2.jpg)


## ファームウェア
https://docs.qmk.fm/#/newbs_getting_started こちらを参照して頂き、ファームウェアを書き込む環境を用意します。

環境ができましたら、下記コマンドで Let's Split 用にファームウェアをビルドします。

```
make lets_split/rev2:default
```

ビルドが完了したら下記コマンドを実行します。

```
make lets_split/rev2:default:avrdude
```

実行すると下記のようなログがでて、`.` が増えていくことが確認出来ると思います。
この間にリセットスイッチを __2回__ 押すとファームウェアの書き込みが完了します。

```
Compiling: ./tmk_core/common/command.c                                                              [OK]
Linking: .build/lets_split_rev2_default.elf                                                         [OK]
Creating load file for flashing: .build/lets_split_rev2_default.hex                                 [OK]
Checking file size of lets_split_rev2_default.hex                                                   [OK]
 * File size is fine - 18578/28672
Copying lets_split_rev2_default.hex to qmk_firmware folder                                          [OK]
Detecting USB port, reset your controller now............
```

片側のProMicroにファームウェアの書き込みが完了したら、もう片方も同じ手順で書き込みを行います。

以上で完成です。
