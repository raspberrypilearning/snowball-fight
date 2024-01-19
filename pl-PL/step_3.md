## Rzucanie śnieżką

--- task ---

Dodaj blok na _końcu_ swojego kodu śnieżki, by `nadać komunikat`{:class="block3control"}, że rzucasz śnieżką:

![ikona śnieżki](images/snowball-sprite.png)

```blocks3
when flag clicked
set [moc v] to (0)
wait (0.5) seconds
go to x:(-200) y:(-130)
point in direction (90)
switch costume to (cel śnieżki v)
repeat until <mouse down?>
    point towards (wskaźnik myszy v)
end
repeat until < not <mouse down?> >
    point towards (wskaźnik myszy v)
    change [moc v] by (1)
    wait (0.1) seconds
end
+ broadcast (rzucać v) and wait
```

--- /task ---

--- task ---

Dodaj ten kod do śnieżki, aby poruszać się, aż do krawędzi sceny:

![ikona śnieżki](images/snowball-sprite.png)

```blocks3
when I receive [rzucać v]
switch costume to (śnieżka v)
repeat until < touching [krawędź v]? >
    move (moc) steps
end
hide
```

Kod wykorzystuje zmienną `moc`{:class="block3variables"} aby decydować o tym, jak szybko się poruszać.

--- /task ---

--- task ---

Teraz, gdy ukrywasz śnieżkę, gdy dotknie krawędzi, dodaj kod aby `pokazac`{:class="block3looks"} śnieżkę po kliknięciu flagi, _zaraz po tym_ jak śnieżka przełączy się na kostium `cel śnieżki`{:class="block3looks"}.

![ikona śnieżki](images/snowball-sprite.png)

```blocks3
when flag clicked
set [moc v] to (0)
wait (0.5) seconds
go to x:(-200) y:(-130)
point in direction (90)
switch costume to (cel śnieżki v)
+show
repeat until <mouse down?>
    point towards (wskaźnik myszy v)
end
repeat until < not <mouse down?> >
    point towards (wskaźnik myszy v)
    change [moc v] by (1)
    wait (0.1) seconds
end
broadcast (rzucać v) and wait
```

--- /task ---

--- task ---

Przetestuj swoją śnieżkę kilka razy. Czy porusza się pod różnymi kątami i z różnymi prędkościami?

--- /task ---

--- task ---

Jeśli chcesz być w stanie rzucić śnieżką wiele razy, po prostu dodaj `zawsze`{:class="block3control"} wokół twojej śnieżki `kiedy kliknięnto flagę`{:class="block3events"} Kod.

![ikona śnieżki](images/snowball-sprite.png)

```blocks3
when flag clicked
+forever
set [moc v] to (0)
wait (0.5) seconds
go to x:(-200) y:(-130)
point in direction (90)
switch costume to (cel śnieżki v)
show
repeat until <mouse down?>
    point towards (wskaźnik myszy v)
end
repeat until < not <mouse down?> >
    point towards (wskaźnik myszy v)
    change [moc v] by (1)
    wait (0.1) seconds
end
broadcast (rzucać v) and wait
end
```

--- /task ---
