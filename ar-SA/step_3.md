## رمي كرة ثلج

--- task ---

أضف كتلة إلى _نهاية_ التعليمة البرمجية كرة الثلج الخاص بك، لـ `بث `{:class="block3control"} أنك ترمى كرة الثلج:

![كائن كرة الثلج](images/snowball-sprite.png)

```blocks3
when flag clicked
set [قوة v] to (0)
wait (0.5) seconds
go to x:(-200) y:(-130)
point in direction (90)
switch costume to (هدف كرة الثلج v)
repeat until <mouse down?>
    point towards (mouse-pointer v)
end
repeat until < not <mouse down?> >
    point towards (mouse-pointer v)
    change [قوة v] by (1)
    wait (0.1) seconds
end
+ broadcast (رمي v) and wait
```

--- /task ---

--- task ---

أضف هذه التعليمات البرمجية إلى كرة الثلج الخاصة بك، لتتحرك حتى تصل إلى حافة المنصة:

![كائن كرة الثلج](images/snowball-sprite.png)

```blocks3
when I receive [رمي v]
switch costume to (كرة الثلج v)
repeat until < touching [edge v]? >
    move (قوة) steps
end
hide
```

التعليمة البرمجية تستخدم متغير `القوة`{:class="block3variables"} لتحديد سرعة التحرك.

--- /task ---

--- task ---

الآن بعد أن تخفي كرة الثلج عندما تلامس الحافة، أضف تعليمة برمجية لـ`عرض `{:class="block3looks"} كرة الثلج عند النقر على العلم، _فقط _ بعد تبديل كرة الثلج إلى المظهر `هدف كرة الثلج `{:class="block3looks"}.

![كائن كرة الثلج](images/snowball-sprite.png)

```blocks3
when flag clicked
set [قوة v] to (0)
wait (0.5) seconds
go to x:(-200) y:(-130)
point in direction (90)
switch costume to (هدف كرة الثلج v)
+show
repeat until <mouse down?>
    point towards (mouse-pointer v)
end
repeat until < not <mouse down?> >
    point towards (mouse-pointer v)
    change [قوة v] by (1)
    wait (0.1) seconds
end
broadcast (رمي v) and wait
```

--- /task ---

--- task ---

اختبر كرة الثلج عدة مرات. هل تتحرك بزوايا مختلفة وبسرعات مختلفة؟

--- /task ---

--- task ---

إذا كنت تريد أن تكون قادراً على رمي كرة الثلج الخاص بك مرات عديدة، فقط قم بإضافة حلقة `للأبد`{:class="block3control"} حول كرة الثلج الخاصة بك `عند النقر فوق العلم `{:class="block3events"}.

![كائن كرة الثلج](images/snowball-sprite.png)

```blocks3
when flag clicked
+forever
set [قوة v] to (0)
wait (0.5) seconds
go to x:(-200) y:(-130)
point in direction (90)
switch costume to (هدف كرة الثلج v)
show
repeat until <mouse down?>
    point towards (mouse-pointer v)
end
repeat until < not <mouse down?> >
    point towards (mouse-pointer v)
    change [قوة v] by (1)
    wait (0.1) seconds
end
broadcast (رمي v) and wait
end
```

--- /task ---
