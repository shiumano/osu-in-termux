# osu-in-termux
Termuxでosuをやる方法 たぶんRaspberry Piでもできる

# やり方

https://qiita.com/karuakun/items/c8439d0aadb2e798cf08
https://www.reddit.com/r/termux/comments/r9jsvv/comment/ho59bvd/?utm_source=share&utm_medium=web2x&context=3

ここを参考にdotnetが動くprootを入れる

そしたらosu!lazer( https://github.com/ppy/osu )をダウンロードしてビルドする

まだライブラリが足りないので、いくつかダウンロードする

https://github.com/veldrid/veldrid-spirv

これはビルドがクソみたいに面倒なのでバイナリを置いときます

https://github.com/shiumano/osu-in-termux/releases/download/v0/libveldrid-spirv.so

これを/usr/libに入れてください

https://aur.archlinux.org/packages/libbass

https://aur.archlinux.org/packages/libbassmix

https://aur.archlinux.org/packages/libbass_fx

この３つは偉大なるAURにビルド済みバイナリがあるのでありがたく使いましょう

Package Detailsの枠の一番下にzipがあります

それを解凍してaarch64の中に入ってるやつを/usr/libに入れます


とりあえずこれで起動できるはずです

あとはzinkを入れましょう

https://www.reddit.com/r/termux/comments/16fmwb9/proot_only_dri3_patch_freedreno_turnip_driver_new/

VirGLでもできなくはないですがあんまりおすすめはしません

https://github.com/xDoge26/Proot-Setup#41-virgl-es-recommended

ここを参考にインストールしてください

# 発生するバグ・問題点
+ 動作が遅い
  + llvmpipeで10fps virgl or zinkで30~40fps zink der3で40~60fps
  + メニューではたまに90fps出たりもする zink dri3だとタイトル画面で240fps出た

+ 音がすごくずれてる
  + オフセットは-100msくらいがちょうどよかった
  + 音声は+200msずれてるので効果音の音量は0にするべき

+ いくつかのvirgl moment
  + 円グラフが腐ってる
  + 楽曲情報が白くなる
  + triangles effectが無い

+ 背景の動画が再生されない

+ あまり関係無いけど修正版prootだとwineが動かない
  + 公式リポジトリ版ではビルドはできないけど実行はできるのでビルドするときだけ修正版を使うべき
