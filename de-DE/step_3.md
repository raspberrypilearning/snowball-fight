## Einen Schneeball werfen

--- task ---

Füge einen Block zum _end_ (Ende) deines Schneeballcodes hinzu, um `eine Nachricht zu senden`{:class="block3control"}, dass du einen Schneeball wirfst:

![Schneeball Figur](images/snowball-sprite.png)

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

Füge diesen Code deinem Schneeball hinzu, um ihn zu bewegen, bis er den Rand der Bühne erreicht:

![Schneeball Figur](images/snowball-sprite.png)

```blocks3
when I receive [throw v]
switch costume to (snowball v)
repeat until < touching [edge v]? >
    move (power) steps
end
hide
```

Der Code verwendet die `Kraft`{:class="block3variables"} Variable um zu entscheiden, wie schnell er sich bewegen soll.

--- /task ---

--- task ---

Nun, da du den Schneeball versteckst, wenn er den Rand berührt, füge diesen Code hinzu, um den Schneeball zu `zeigen`{:class="block3looks"}, wenn die Flagge angeklickt wird, _genau_ nachdem der Schneeball zum `Schneeball-zielen`{:class="block3looks"}-Kostüm gewechselt hat.

![Schneeball Figur](images/snowball-sprite.png)

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

Teste deinen Schneeball ein paar Mal. Bewegt er sich in verschiedenen Winkeln und Geschwindigkeiten?

--- /task ---

--- task ---

Wenn du deinen Schneeball viele Male werfen möchtest, füge einfach eine `wiederhole fortlaufend`{:class="block3control"} Schleife um deinen Schneeball-Code, unter dem `Wenn Flagge angeklickt wird`{:class="block3events"}-Block hinzu.

![Schneeball Figur](images/snowball-sprite.png)

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
