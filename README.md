アイドル相関図
====

## これは何？

DOT言語で記述したアイドル相関図です。

## 必要なソフトウェア
[Graphviz](https://graphviz.org/)

## 出力方法
PDF出力
```
$ dot -Tpdf idol_diagram.dot > idol_diagram.pdf
```
PNG出力
```
$ dot -Tpng idol_diagram.dot > idol_diagram.png
```

## 記述方法
グループの追加
```
    "グループ名" [ label=<
        <table border="0" cellspacing="0" cellborder="1">
        <tr><td colspan="3" bgcolor="#000000"><font color="#ffffff">グループ名</font></td></tr>
        <tr><td colspan="3" bgcolor="#ffffff" port="メンバー名">メンバー名<br/><font point-size="8">(加入年月 - )</font></td></tr>
        <tr><td colspan="3" bgcolor="#dddddd" port="卒業したメンバー名">卒業したメンバー名<br/><font point-size="8">(加入年月 - 卒業年月)</font></td></tr>
        </table>>
    ];
```

グループが改名している場合は改行してカッコ書きで改名前のグループ名を書きます。
```
...
        <tr><td colspan="3" bgcolor="#000000"><font color="#ffffff">グループ名<br/>(改名前のグループ名)</font></td></tr>
...
```

相関は全グループの記述の後に追加します。
```
    "前のグループ":"メンバー名" -> "現在のグループ":"メンバー名";
```

3つ以上渡り歩いている場合でも１行にまとめて記述できます。
```
    "前の前のグループ":"メンバー名" -> "前のグループ":"メンバー名" -> "現在のグループ":"メンバー名";
```

## TODO
- メンバーの記述順は加入日順にしたい
- メンバーの加入年月、卒業年月を記載したい

## Licence

[MIT](https://github.com/tcnksm/tool/blob/master/LICENCE)

## Author

[tora-tiger](https://github.com/tora-tiger)