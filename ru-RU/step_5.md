## Цель

Давай добавим цель для твоих снежков!

--- task ---

Добавь ещё один спрайт в свой проект.

![спрайт мишень на сцене](images/snow-deer.png)

[[[generic-scratch3-sprite-from-library]]]

--- /task ---

--- task ---

Добавь следующий код к новому спрайту, теперь он говорит "Ты попал!" при удачном попадании снежка:

![спрайт мишень](images/target-sprite.png)

```blocks3
when flag clicked
forever
    if < touching [снежок v]? > then
        say [Ты попал!] for (1) seconds
    end
end
```

--- /task ---

--- task ---

Проверь свой новый код.

![спрайт мишень, говорящий что ты попал!](images/snow-hit.png)

--- /task ---

--- task ---

Давай добавим пару деталей, чтобы сделать игру сложнее. Для начала, пускай олень будет перемещаться каждый раз, когда игрок бросает снежок.

Для этого в верхней части `бесконечного`{:class="block3control"} цикла добавь команду `передать`{:class="block3control"} для снежка. Это позволит твоему оленю понять, что скоро произойдет выстрел.

![спрайт снежок](images/snowball-sprite.png)

```blocks3
when flag clicked
forever
set [сила v] to (0)
+broadcast (новый бросок v)
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

Добавь следующий код, чтобы переместить оленя в случайную позицию, после того, как он получит сообщение:

![спрайт мишень](images/target-sprite.png)

```blocks3
when I receive [новый бросок v]
set x to (pick random (0) to (200))
```

--- /task ---

--- task ---

Проверь свой проект, бросив несколько снежков. Перемещается ли цель после каждого броска?

--- /task ---

--- task ---

Ты также можешь усложнить свою игру, добавив перед снежком препятствие в виде камня.

![спрайт камень на сцене](images/snow-rock.png)

--- /task ---

--- task ---

Теперь ты можешь изменить код снежка таким образом, чтобы он останавливался при касании края экрана _или_ камня.

![спрайт снежок](images/snowball-sprite.png)

```blocks3
when I receive [бросок v]
switch costume to (снежок v)
+ repeat until << touching [edge v]? > or <touching [Камень v]?>>
    change y by (-5)
    move (сила) steps
    if <(сила) > [0]> then
    change [сила v] by (-0.25)
    end
end
hide
```

--- /task ---

--- task ---

Наконец, уменьшение снежка и оленя сделает твою игру еще более сложной.

![маленький спрайт снежка и мишени](images/snow-small.png)

--- /task ---
