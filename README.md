satysfi-zrbase
==============

SATySFiでのプログラミングをもっと快適にするためのパッケージ集

## 例

```text
@require: zmtdoc0
@require: zrbase0
@require: zrandom0
@require: list

% log messages with formatting
let (snowman, eight) = (9731, 56)
let () = z-infof (fun f -> % it's '%04X' form
  [`snowman = U+`; f#zw 4 f#ux snowman; `; eight = U+`; f#zw 4 f#ux eight])

% do some math
let sqrt2 = sqrt 2.
let () = z-infof (fun f -> [`sqrt 2 = `#;f#g sqrt2])
let logval = log 123456789.
let () = z-infof (fun f -> [`log 123456789 = `#;f#g logval])

% random numbers
let () = ZRandom0.init 129414 % seed
let rolls = List.map (fun k -> ZRandom0.int k + 1) [6;6;6;6;6;20;20;20]
let () = z-infof (fun f -> [`dice rolls: `#;f#bls f#d rolls])

in
% The PDF output is empty :-)
document ()
```

これを普通にコンパイルすると、**端末に**以下のように表示される。

```text
  [INFO] snowman = U+2603; eight = U+0038
  [INFO] sqrt 2 = 1.41421356237
  [INFO] log 123456789 = 18.6314017662
  [INFO] dice rolls: [2;4;5;3;5;13;7;14]
```

--------------------
Takayuki YATO (aka. "ZR")  
https://github.com/zr-tex8r
