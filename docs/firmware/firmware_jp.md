# ファームウェア

## ファームウェアを書き込む

VIA用のファームウェアを下記からダウンロードします
- [lskbd_rev1_via.uf2](https://github.com/foostan/kbd_firmware/blob/main/keyboards/lskbd/qmk/qmk_firmware/.build/lskbd_rev1_via.uf2)

BOOTボタンを押しながらPCに接続するか、PCに接続した状態でBOOTボタンを押しながらリセットボタンを押します。
すると、RPI-PR2デバイスがマウントされます。

![btn](https://github.com/foostan/lskbd/assets/736191/91329a6a-8a0d-4d2d-9b1a-3d210b58bd99)

ダウンロードしたuf2ファイルをRPI-PR2デバイスにドロップすると書き込みが完了します。

![flash](https://github.com/foostan/lskbd/assets/736191/8de0f70a-ad3b-46c1-a0dc-98d4f70d812c)

片側にファームウェアの書き込みが完了したら、もう片方も同じ手順で書き込みを行います。

## (オプション) 自分でファームウェアをビルドする場合

[the QMK _getting started_ guide](https://docs.qmk.fm/#/newbs_getting_started) こちらを参照して頂き、ファームウェアを書き込む環境を用意します。

環境ができましたら、下記のファイルを利用して自身でビルドを行ってください。
https://github.com/foostan/kbd_firmware/tree/main/keyboards/crkbd/qmk/qmk_firmware

## Change your keymap

下記からjsonファイルをダウンロードし、VIAでロードしてください。
- [lskbd](https://github.com/foostan/kbd_firmware/blob/main/keyboards/lskbd/the-via/lskbd.json)

![load_json](https://github.com/foostan/kbd_firmware/assets/736191/67398174-0ef7-4698-9e39-6595b8320428)
![loaded_json](https://github.com/foostan/lskbd/assets/736191/a43ec9c7-5c84-4933-8bc3-a4a6ea5d1ca9)
