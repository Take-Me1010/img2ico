# img2ico

画像をicoに変換するコマンドラインツール
CLI tool to convert your file into ico file.

## 環境 / requirement

- Python 3.x
- pillow

## 機能 / feature

任意の画像からicoを生成します。
元画像が正方形でない場合、中心からできるだけ大きな正方形を切り出して使用します。

```
python -u img2ico .\example\hakase4_laugh.png -o .\example\hakase4_laugh.ico
```

Before <---> After
![example/hakase4_laugh.png](example/hakase4_laugh.png)![example/hakase4_laugh.ico](example/hakase4_laugh.ico)
(画像: いらすとや)

事前に正方形にトリミングしておくと良いかもしれません。


また、出力を各丸四角にすることができます。

```
python -u img2ico .\example\single_color.jpg --round -o .\example\single_color.ico
```

Before <---> After
![](example/single_color.jpg)    ![](example/single_color.ico)

この半径はオプション引数で変更できます。
--round-rateが2の時、円になります。数字が大きいと小さな半径になります。
なお半径の計算式は正方形の長さ`size`を`round-rate`で割る、つまり`r = size // round_rate`です。

```
python -u img2ico .\example\single_color.jpg --round --round-rate 2 -o .\example\single_color_rate_2.ico
```

![](example/single_color_rate_2.ico)

`--round-rate 10`の場合は以下。

![](example/single_color_rate_10.ico)
