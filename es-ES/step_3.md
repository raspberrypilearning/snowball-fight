## Lanzando una bola de nieve

--- task ---

Añade un bloque al _final_ del código de tu bola de nieve, para enviar un `evento`{:class="block3control"} conforme estás lanzando una bola de nieve:

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

Añade este código a tu bola de nieve para moverte antes de que llegue al borde del escenario:

![objeto bola de nieve](images/snowball-sprite.png)

```blocks3
when I receive [throw v]
switch costume to (snowball v)
repeat until < touching [edge v]? >
    move (power) steps
end
hide
```

El código utiliza la variable `potencia`{:class="block3variables"} para decidir con qué rapidez debe moverse.

--- /task ---

--- task ---

Ahora que estás ocultando la bola de nieve cuando toca alguno de los bordes, añade código para `mostrar`{:class="block3looks"} la bola de nieve cuando hagas clic en la bandera, _justo_ después de que la bola de nieve cambie al disfraz de `objetivo de la bola de nieve`{:class="block3looks"}.

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

Prueba tu bola de nieve varias veces. ¿Se mueve a diferentes ángulos y velocidades?

--- /task ---

--- task ---

Si quieres poder lanzar tu bola de nieve muchas veces, simplemente añade un bucle `por siempre`{:class="block3control"} alrededor del código `al hacer clic en la bandera`{:class="block3events"} de tu bola de nieve.

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
