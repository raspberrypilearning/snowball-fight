## Кидання сніжки

--- task ---

Додай _в кінці_ коду сніжки блок для `оповіщення`{:class="block3control"} про те, що ти її кидаєш:

![спрайт сніжки](images/snowball-sprite.png)

```blocks3
when flag clicked
set [сила v] to (0)
wait (0.5) seconds
go to x:(-200) y:(-130)
point in direction (90)
switch costume to (сніжка з прицілом v)
repeat until <mouse down?>
    point towards (mouse-pointer v)
end
repeat until < not <mouse down?> >
    point towards (mouse-pointer v)
    change [сила v] by (1)
    wait (0.1) seconds
end
+ broadcast (кидок v) and wait
```

--- /task ---

--- task ---

Додай наступний код до сніжки, щоб вона летіла, поки не досягне краю сцени:

![спрайт сніжки](images/snowball-sprite.png)

```blocks3
when I receive [кидок v]
switch costume to (сніжка v)
repeat until < touching [edge v]? >
    move (сила) steps
end
hide
```

Цей код використовує змінну `сила`{:class="block3variables"}, щоб визначати, як швидко рухатися.

--- /task ---

--- task ---

Тепер як ти ховаєш сніжку, коли та досягає краю, додай код, щоб `показати`{:class="block3looks"} її, коли прапор натиснуто, _прямо_ після того, як сніжка перемикається на образ `сніжка з прицілом`{:class="block3looks"}.

![спрайт сніжки](images/snowball-sprite.png)

```blocks3
when flag clicked
set [сила v] to (0)
wait (0.5) seconds
go to x:(-200) y:(-130)
point in direction (90)
switch costume to (сніжка з приціломv)
+show
repeat until <mouse down?>
    point towards (mouse-pointer v)
end
repeat until < not <mouse down?> >
    point towards (mouse-pointer v)
    change [сила v] by (1)
    wait (0.1) seconds
end
broadcast (кидок v) and wait
```

--- /task ---

--- task ---

Протестуй свою сніжку декілька разів. Чи рухається вона під різними кутами та з різною швидкістю?

--- /task ---

--- task ---

Якщо ти хочеш мати можливість кидати сніжку багато разів, просто додай цикл `завжди`{:class="block3control"} навколо коду сніжки під блоком `коли прапор натиснуто`{:class="block3events"}.

![спрайт сніжки](images/snowball-sprite.png)

```blocks3
when flag clicked
+forever
set [сила v] to (0)
wait (0.5) seconds
go to x:(-200) y:(-130)
point in direction (90)
switch costume to (сніжка з прицілом v)
show
repeat until <mouse down?>
    point towards (mouse-pointer v)
end
repeat until < not <mouse down?> >
    point towards (mouse-pointer v)
    change [сила v] by (1)
    wait (0.1) seconds
end
broadcast (кидок v) and wait
end
```

--- /task ---
