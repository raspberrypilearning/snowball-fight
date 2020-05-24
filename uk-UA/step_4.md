## Реалістичний рух

Тепер в тебе є сніжка, але давай зробимо, щоб вона рухалася трохи більш реалістично.

--- task ---

Спочатку встановимо максимальну силу, щоб сніжку не можна було кинути занадто сильно.

В коді для сніжки `коли прапор натиснуто`{:class="block3events"} нам потрібно збільшувати силу, тільки якщо вона менша за 20. Зміни свій код:

![спрайт сніжки](images/snowball-sprite.png)

```blocks3
repeat until< not <mouse down?> >
+   if < (power) < [20] > then
        change [power v] by (1)
        wait (0.1) seconds
    end
end
```

--- /task ---

--- task ---

Протестуй сніжку знову, і ти побачиш, що сила ніколи не піднімається вище 20.

--- /task ---

--- task ---

Тепер, коли максимальна сила для сніжки дорівнює 20, ти також можеш встановити це значення як максимальне для змінної слайдера. Клацни правою кнопкою мишки на змінній сили і вибери "змінити діапазон слайдера".

![мінімальне та максимальне значення слайдера](images/snow-minmax.png)


--- /task ---

--- task ---

Також ти можеш сповільнювати сніжку, потроху знижуючи силу, поки вона летить у повітрі. Додай наступний блок до коду сніжки `коли я отримую [кидок]`{:class="block3events"}:

![спрайт сніжки](images/snowball-sprite.png)

```blocks3
when I receive [throw v]
switch costume to (snowball v)
repeat until < touching [edge v]? >
    move (power) steps
+   change [power v] by (-0.25)
end
hide
```

--- /task ---


--- task ---

Протестуй цей новий код, чи працює він так, як ти очікуєш? Ти можеш бачити, як сила продовжує знижуватися, і врешті-решт сніжка починає рухатися назад!

Щоб це виправити, ти можеш додати до свого коду блок `якщо`{:class="block3control"}, щоб сила знижувалася, лише коли вона більша 0:

![спрайт сніжки](images/snowball-sprite.png)

```blocks3
when I receive [throw v]
switch costume to (snowball v)
repeat until < touching [edge v]? >
    move (power) steps
+   if < (power) > (0) > then
        change [power v] by (-0.25)
    end
end
hide
```

--- /task ---

--- task ---

Вже майже готово, але тобі треба додати гравітацію для сніжки, щоб вона падала на землю. Ти можеш це зробити, просто переміщуючи сніжку рівномірно вниз за допомогою цього коду:

![спрайт сніжки](images/snowball-sprite.png)

```blocks3
when I receive [throw v]
switch costume to (snowball v)
repeat until < touching [edge v]? >
+   change y by (-5)
    move (power) steps
    if < (power) > (0) > then
        change [power v] by (-0.25)
    end
end
hide
```

--- /task ---

--- task ---

Протестуй свою сніжку знову, і ти маєш побачити, що вона рухається більш реалістично.

--- /task ---

