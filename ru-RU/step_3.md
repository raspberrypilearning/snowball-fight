## Метание снежка

--- task ---

Добавь блок в _конец_ кода для снежка, чтобы обеспечить `передачу`{:class="block3control"} информации о том, что ты бросаешь снежок:

![спрайт снежка](images/snowball-sprite.png)

```blocks3
when flag clicked
set [сила v] to (0)
wait (0.5) seconds
go to x:(-200) y:(-130)
point in direction (90)
switch costume to (прицеливание снежка v)
repeat until <mouse down?>
    point towards (mouse-pointer v)
end
repeat until < not <mouse down?> >
    point towards (mouse-pointer v)
    change [сила v] by (1)
    wait (0.1) seconds
end
+ broadcast (бросок v) and wait
```

--- /task ---

--- task ---

Добавь следующий код для снежка, чтобы обеспечить его движение до момента пересечения края сцены:

![спрайт снежка](images/snowball-sprite.png)

```blocks3
when I receive [бросок v]
switch costume to (снежок v)
repeat until < touching [edge v]? >
    move (сила) steps
end
hide
```

Код использует переменную `сила`{:class="block3variables"} для определения скорости полета.

--- /task ---

--- task ---

Теперь, когда снежок исчезает при достижении края сцены, добавь код, для того чтобы `показать`{:class="block3looks"} снежок при нажатии на флажок _сразу_ после того, как снежок меняет костюм на `прицеливание снежка`{:class="block3looks"}.

![спрайт снежка](images/snowball-sprite.png)

```blocks3
when flag clicked
set [сила v] to (0)
wait (0.5) seconds
go to x:(-200) y:(-130)
point in direction (90)
switch costume to (прицеливание снежка v)
+show
repeat until <mouse down?>
    point towards (mouse-pointer v)
end
repeat until < not <mouse down?> >
    point towards (mouse-pointer v)
    change [сила v] by (1)
    wait (0.1) seconds
end
broadcast (бросок v) and wait
```

--- /task ---

--- task ---

Протестируйте свой снежок несколько раз. Перемещается ли он под разными углами и с разными скоростями?

--- /task ---

--- task ---

Если ты хочешь бросать снежок бесконечное количество раз, просто помести код для `когда нажат флажок`{:class="block3events"} в тело `бесконечного`{:class="block3control"} цикла.

![спрайт снежка](images/snowball-sprite.png)

```blocks3
when flag clicked
+forever
set [сила v] to (0)
wait (0.5) seconds
go to x:(-200) y:(-130)
point in direction (90)
switch costume to (прицеливание снежка v)
show
repeat until <mouse down?>
    point towards (mouse-pointer v)
end
repeat until < not <mouse down?> >
    point towards (mouse-pointer v)
    change [сила v] by (1)
    wait (0.1) seconds
end
broadcast (бросок v) and wait
end
```

--- /task ---
