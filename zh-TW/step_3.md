## 扔雪球

--- task ---

添加一個積木在你的雪球程式 _結尾_，來`廣播`{:class="block3control"} 你正在扔一顆雪球：

![snowball sprite](images/snowball-sprite.png)

```blocks3
when flag clicked
set [力量 v] to (0)
wait (0.5) seconds
go to x:(-200) y:(-130)
point in direction (90)
switch costume to (雪球瞄準 v)
repeat until <mouse down?>
    point towards (mouse-pointer v)
end
repeat until < not <mouse down?> >
    point towards (mouse-pointer v)
    change [力量 v] by (1)
    wait (0.1) seconds
end
+ broadcast (丟 v) and wait
```

--- /task ---

--- task ---

添加這個程式碼到你的雪球來移動它，直到它接觸舞台邊緣：

![snowball sprite](images/snowball-sprite.png)

```blocks3
when I receive [throw v]
switch costume to (snowball v)
repeat until < touching [edge v]? >
    move (power) steps
end
hide
```

The code uses the `power`{:class="block3variables"} variable to decide how fast to move.

--- /task ---

--- task ---

Now that you're hiding the snowball when it touches the edge, add code to `show`{:class="block3looks"} the snowball when the flag is clicked, _just_ after the snowball switches to the `snowball-aim`{:class="block3looks"} costume.

![snowball sprite](images/snowball-sprite.png)

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

Test out your snowball a few times. Does it move at different angles and different speeds?

--- /task ---

--- task ---

If you want to be able to throw your snowball lots of times, just add a `forever`{:class="block3control"} loop around your snowball `when flag clicked`{:class="block3events"} code.

![snowball sprite](images/snowball-sprite.png)

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
