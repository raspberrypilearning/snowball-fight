## 扔雪球

--- task ---

添加一個積木在你的雪球程式 _結尾_，來`廣播`{:class="block3control"} 你正在扔一顆雪球：

![雪球角色](images/snowball-sprite.png)

```blocks3
when flag clicked
set [力量 v] to (0)
wait (0.5) seconds
go to x:(-200) y:(-130)
point in direction (90)
switch costume to (雪球瞄準 v)
repeat until <mouse down?>
    point towards (鼠標 v)
end
repeat until < not <mouse down?> >
    point towards (鼠標 v)
    change [力量 v] by (1)
    wait (0.1) seconds
end
+ broadcast (丟 v) and wait
```

--- /task ---

--- task ---

添加這個程式碼到你的雪球來移動它，直到它接觸舞台邊緣：

![雪球角色](images/snowball-sprite.png)

```blocks3
when I receive [丟 v]
switch costume to (雪球 v)
repeat until < touching [邊緣 v]? >
    move (力量) steps
end
hide
```

這個程式碼使用`力量`{:class="block3variables"} 變數來決定移動的速度。

--- /task ---

--- task ---

現在，當雪球接觸到邊緣時，你要將它隱藏起來。當點擊旗子時，添加程式碼 `顯示`{:class="block3looks"} 到雪球， _正好_在雪球轉換成`雪球瞄準`{:class="block3looks"} 造型的後面。

![雪球角色](images/snowball-sprite.png)

```blocks3
when flag clicked
set [力量 v] to (0)
wait (0.5) seconds
go to x:(-200) y:(-130)
point in direction (90)
switch costume to (雪球瞄準 v)
+show
repeat until <mouse down?>
    point towards (鼠標 v)
end
repeat until < not <mouse down?> >
    point towards (鼠標 v)
    change [力量 v] by (1)
    wait (0.1) seconds
end
broadcast (丟 v) and wait
```

--- /task ---

--- task ---

測試你的雪球幾次。 它是否以不同的角度和速度移動？

--- /task ---

--- task ---

如果你想扔雪球很多次，只需要添加一個 `重複無限次`{:class="block3control"} 迴圈環繞`當旗子被點擊`{:class="block3events"} 程式碼。

![雪球角色](images/snowball-sprite.png)

```blocks3
when flag clicked
+forever
set [力量 v] to (0)
wait (0.5) seconds
go to x:(-200) y:(-130)
point in direction (90)
switch costume to (雪球瞄準 v)
show
repeat until <mouse down?>
    point towards (鼠標 v)
end
repeat until < not <mouse down?> >
    point towards (鼠標 v)
    change [力量 v] by (1)
    wait (0.1) seconds
end
broadcast (丟 v) and wait
end
```

--- /task ---
