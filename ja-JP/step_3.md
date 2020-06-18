## 雪玉を投げる

--- task ---

雪玉のコードの_さいごに_ブロックを追加して、雪玉を投げるという`メッセージを送ります`{:class="block3control"} 。

![雪玉のスプライト](images/snowball-sprite.png)

```blocks3
when flag clicked
set [power v] to (0)
wait (0.5) seconds
go to x:(-200) y:(-130)
point in direction (90)
switch costume to (snowball-aim v)
repeat until <mouse down?>
    point towards (mouse-pointer v)
end
repeat until < not <mouse down?> >
    point towards (mouse-pointer v)
    change [power v] by (1)
    wait (0.1) seconds
end
+ broadcast (throw v) and wait
```

--- /task ---

--- task ---

このコードを雪玉に追加して、雪玉がステージの端 (はし) まで移動 (いどう) するようにします。

![雪玉のスプライト](images/snowball-sprite.png)

```blocks3
when I receive [throw v]
switch costume to (snowball v)
repeat until < touching [edge v]? >
    move (power) steps
end
hide
```

このコードは、`力`{:class="block3variables"}変数を使って移動する速度を決定します。

--- /task ---

--- task ---

今は、雪玉がステージの端に触れる (ふれる) と隠れる (かくれる) ようになっています。 旗が押されたときに、コスチュームを`雪玉 (ねらい)`{:class="block3looks"}に切りかえた_すぐ_後で、雪玉が`表示`{:class="block3looks"} (ひょうじ) されるようにします。

![雪玉のスプライト](images/snowball-sprite.png)

```blocks3
when flag clicked
set [power v] to (0)
wait (0.5) seconds
go to x:(-200) y:(-130)
point in direction (90)
switch costume to (snowball-aim v)
+show
repeat until <mouse down?>
    point towards (mouse-pointer v)
end
repeat until < not <mouse down?> >
    point towards (mouse-pointer v)
    change [power v] by (1)
    wait (0.1) seconds
end
broadcast (throw v) and wait
```

--- /task ---

--- task ---

雪玉を何回かテストしましょう。 雪玉はちがう角度や速度で動きますか？

--- /task ---

--- task ---

雪玉を何回も投げたい場合は、雪玉の`旗が押されたとき`{:class="block3events"}のコードに`ずっと`{:class="block3control"}ループを追加します。

![雪玉のスプライト](images/snowball-sprite.png)

```blocks3
when flag clicked
+forever
set [power v] to (0)
wait (0.5) seconds
go to x:(-200) y:(-130)
point in direction (90)
switch costume to (snowball-aim v)
show
repeat until <mouse down?>
    point towards (mouse-pointer v)
end
repeat until < not <mouse down?> >
    point towards (mouse-pointer v)
    change [power v] by (1)
    wait (0.1) seconds
end
broadcast (throw v) and wait
end
```

--- /task ---
