## Atirando uma bola de neve

--- task ---

Adicione um bloco ao _final_ do seu código da bola de neve para `transmitir`{:class="block3control"} que você está atirando uma bola de neve:

![ator bola de neve](images/snowball-sprite.png)

```blocks3
when flag clicked
set [energia v] to (0)
wait (0.5) seconds
go to x:(-200) y:(-130)
point in direction (90)
switch costume to (mira da bola de neve v)
repeat until <mouse down?>
    point towards (mouse-pointer v)
end
repeat until < not <mouse down?> >
    point towards (mouse-pointer v)
    change [energia v] by (1)
    wait (0.1) seconds
end
+ broadcast (atirar v) and wait
```

--- /task ---

--- task ---

Adicione esse código à sua bola de neve para mover até que atinja a borda do palco:

![ator bola de neve](images/snowball-sprite.png)

```blocks3
when I receive [atirar v]
switch costume to (bola de neve v)
repeat until < touching [edge v]? >
    move (power) steps
end
hide
```

O código usa a variável `energia`{:class="block3variables"} para decidir com que rapidez se mover.

--- /task ---

--- task ---

Agora que você está escondendo a bola de neve quando ela toca a borda, adicione código para que `mostre`{:class="block3looks"} a bola de neve quando a bandeira é clicada, _apenas_ depois que a bola de neve muda para a fantasia `mira da bola de neve`{:class="block3looks"}.

![ator bola de neve](images/snowball-sprite.png)

```blocks3
when flag clicked
set [energia v] to (0)
wait (0.5) seconds
go to x:(-200) y:(-130)
point in direction (90)
switch costume to (mira da bola de neve v)
+show
repeat until <mouse down?>
    point towards (mouse-pointer v)
end
repeat until < not <mouse down?> >
    point towards (mouse-pointer v)
    change [energia v] by (1)
    wait (0.1) seconds
end
broadcast (atirar v) and wait
```

--- /task ---

--- task ---

Teste sua bola de neve algumas vezes. Ela se move em diferentes ângulos e diferentes velocidades?

--- /task ---

--- task ---

Se você quiser ser capaz de atirar sua bola de neve muitas vezes, basta adicionar um loop `sempre`{:class="block3control"} ao redor do código `quando ⚑ for clicado`{:class="block3events"}.

![ator bola de neve](images/snowball-sprite.png)

```blocks3
when flag clicked
+forever
set [energia v] to (0)
wait (0.5) seconds
go to x:(-200) y:(-130)
point in direction (90)
switch costume to (mira da bola de neve v)
show
repeat until <mouse down?>
    point towards (mouse-pointer v)
end
repeat until < not <mouse down?> >
    point towards (mouse-pointer v)
    change [energia v] by (1)
    wait (0.1) seconds
end
broadcast (atirar v) and wait
end
```

--- /task ---
