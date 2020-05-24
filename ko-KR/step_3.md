## 눈덩이 던지기

--- task ---

눈덩이 코드의 _마지막 부분_에 블럭을 추가해서, 눈덩이를 던진다고 `방송`{:class="block3control"}합시다.

![눈덩이 스프라이트](images/snowball-sprite.png)

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

눈덩이에 이 코드를 추가하여 눈덩이가 스테이지의 가장자리에 닿기 전까지 움직이도록 하세요:

![눈덩이 스프라이트](images/snowball-sprite.png)

```blocks3
when I receive [throw v]
switch costume to (snowball v)
repeat until < touching [edge v]? >
    move (power) steps
end
hide
```

이 코드는 `세기`{:class="block3variables"} 변수를 사용해 얼마나 빨리 움직일 지를 결정합니다.

--- /task ---

--- task ---

눈덩이가 가장자리에 닿을 때 눈덩이는 숨겨지므로, 눈덩이를 `눈덩이 궤적 모양`{:class="block3looks"}으로 바꾼 _직후_, 깃발을 클릭하면 눈덩이를 `보여주는`{:class="block3looks"} 코드를 추가하세요.

![눈덩이 스프라이트](images/snowball-sprite.png)

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

눈덩이 던지기를 몇 번 테스트하세요. 다른 각도와 속도로 움직이나요?

--- /task ---

--- task ---

눈덩이를 많이 던질 수 있게 하고 싶다면 `깃발을 클릭했을 때`{:class="block3events"} 코드에 `반복하기`{:class="block3control"}를 추가하세요.

![눈덩이 스프라이트](images/snowball-sprite.png)

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
