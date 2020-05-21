## Lancer une boule de neige

--- task ---

Ajoute un bloc à la _fin_ de ton code de boule de neige, pour `diffuser`{:class="block3control"} que tu lances une boule de neige :

![sprite de boule de neige](images/snowball-sprite.png)

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

Ajoute ce code à ta boule de neige, pour te déplacer jusqu'à ce qu'elle atteigne le bord de la scène :

![sprite de boule de neige](images/snowball-sprite.png)

```blocks3
when I receive [throw v]
switch costume to (snowball v)
repeat until < touching [edge v]? >
    move (power) steps
end
hide
```

Le code utilise la variable `puissance`{:class="block3variables"} pour décider de la vitesse de déplacement.

--- /task ---

--- task ---

Maintenant que tu caches la boule de neige quand elle touche le bord, ajoute du code pour `montrer`{:class="block3looks"} la boule de neige quand le drapeau est cliqué, _juste_ après que la boule de neige passe au costume `Boule de neige-visée`{:class="block3looks"}.

![sprite de boule de neige](images/snowball-sprite.png)

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

Teste ta boule de neige plusieurs fois. Se déplace-t-elle à différentes inclinaisons et à différentes vitesses ?

--- /task ---

--- task ---

Si tu veux pouvoir lancer ta boule de neige plusieurs fois, il suffit d'ajouter un code `répéter indéfiniment`{:class="block3control"} autour de ta boule de neige `quand le drapeau est cliqué`{:class="block3events"}.

![sprite de boule de neige](images/snowball-sprite.png)

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
