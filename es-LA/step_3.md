## Lanzar una bola de nieve

--- task ---

Añade un bloque al _final_ de tu código bola de nieve, para `enviar`{: class="block3control"} aviso de que lanzas una bola de nieve:

![objeto bola de nieve](images/snowball-sprite.png)

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

Agrega este código a tu bola de nieve para que se mueva hasta que llegue al borde del escenario:

![objeto bola de nieve](images/snowball-sprite.png)

```blocks3
when I receive [throw v]
switch costume to (snowball v)
repeat until < touching [edge v]? >
    move (power) steps
end
hide
```

El código usa la variable `fuerza`{:class="block3variables"} para decidir qué tan rápido se mueve.

--- /task ---

--- task ---

Ahora que ocultas la bola de nieve cuando toca el borde, agrega el código para `mostrar`{: class = "block3looks"} la bola de nieve cuando se hace clic en la bandera, _solo_ después de que la bola de nieve cambie al disfraz `dirección bola de nieve`{: class = "block3looks"}.

![objeto bola de nieve](images/snowball-sprite.png)

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

Prueba tu bola de nieve varias veces. ¿Se mueve en distintos ángulos y velocidades?

--- /task ---

--- task ---

Si quieres lanzar tu bola de nieve muchas veces, solo agrega un bucle `por siempre`{:class="block3control"} alrededor de tu bola de nieve con el código `cuando se haga clic en la bandera`{: class="block3events"}.

![objeto bola de nieve](images/snowball-sprite.png)

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
