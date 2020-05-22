## Hacer una bola de nieve

Hagamos una bola de nieve que puedas lanzar por todo el escenario.

--- task ---

Abre el proyecto inicial de Scratch.

**En línea**: abre el [proyecto inicial](http://rpf.io/snowball-fight-on){:target="_blank"}.

Si tienes una cuenta Scratch puedes hacer una copia al hacer clic en **Reinventar**.

**Sin conexión**: abre el [proyecto inicial](http://rpf.io/p/en/snowball-fight-go){:target=_blank"} en el editor sin conexión.

Si necesitas descargar e instalar el editor sin conexión de Scratch, puedes encontrarlo en [rpf.io/scratchoff](http://rpf.io/scratchoff){:target="_blank"}.

En el proyecto inicial, deberías ver un escenario en blanco y un objeto bola de nieve.

--- /task ---

--- task ---

El objeto «Bolanieve» contiene 2 disfraces, un disfraz normal y otro que muestra en qué dirección se dirige la bola de nieve.

![disfraces de bola de nieve](images/snow-costume.png)

--- /task ---

--- task ---

Primero, permitamos que el jugador cambie el angulo de dirección de la bola de nieve. Añade este código al objeto bola de nieve:

![objeto bola de nieve](images/snowball-sprite.png)

```blocks3
when flag clicked
wait (0.5) seconds
go to x:(-200) y:(-130)
point in direction (90)
switch costume to (snowball-aim v)
repeat until <mouse down?>
    point towards (mouse-pointer v)
end
```

--- /task ---

--- task ---

Prueba tu proyecto haciendo clic en la bandera verde. Deberías ver que tu bola de nieve sigue la dirección del mouse, hasta que hagas clic.

![snow ball aim sprite pointing at mouse pointed](images/snow-mouse.png)

--- /task ---

--- task ---

Let's also allow the player to decide on how powerful the snowball should be thrown. Create a new variable called `power`{:class="block3variables"}.

[[[generic-scratch3-add-variable]]]

--- /task ---

--- task ---

Drag your new variable display to the bottom of the stage, near the snowball. Right-click on the variable display and click 'slider'.

![variable changed to slider](images/snow-slider.png)

--- /task ---

--- task ---

Add code to set your new `power`{:class="block3variables"} variable to 0 when the flag is clicked.

![snowball sprite](images/snowball-sprite.png)

```blocks3
when flag clicked
+ set [power v] to (0)
```

--- /task ---

--- task ---

Now that you have a `power`{:class="block3variables"} variable, you can increase the power of the snowball _after_ the direction has been chosen with this code:

![snowball sprite](images/snowball-sprite.png)

```blocks3
repeat until <mouse down?>
    point towards (mouse-pointer v)
end
+repeat until < not <mouse down?> >
    point towards (mouse-pointer v)
    change [power v] by (1)
    wait (0.1) seconds
end
```

This code means that you have to _keep the mouse button held down_ after choosing the direction, to choose the snowball's power.

--- /task ---

--- task ---

Test your snowball, to see if you can choose its angle and power.

![power variable at 35 next to snowball aim](images/snow-test.png)

--- /task ---
