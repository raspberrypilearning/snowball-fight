## 真實的移動

你現在有了一個雪球，但讓它移動的更真實。

--- task ---

首先，讓我們設置最大力量等級，以免雪球扔得太用力。

在你的雪球`當旗子被點擊` {：class =“ block3events”}程式碼，僅當如果力量小於20時，我們才需要增加力量。 將你的程式更改為：

![雪球角色](images/snowball-sprite.png)

```blocks3
repeat until< not <mouse down?> >
+   if < (力量) < [20] > then
        change [力量 v] by (1)
        wait (0.1) seconds
    end
end
```

--- /task ---

--- task ---

再次測試你的雪球，你將看到力量永遠不會超過20。

--- /task ---

--- task ---

現在，雪球的最大力量為20，您也可以將其設置為變量滑桿的最大值。 右鍵點擊你的力量變數，然後點擊「設置滑桿的最小值和最大值」。

![滑桿範圍的最小值最大值](images/snow-minmax.png)


--- /task ---

--- task ---

你還可以通過在空中飛行時略微降低力量來減慢雪球運動的速度。 添加此程式積木到您的雪球` 當我收到 [丟]時` {：class =“ block3events”}程式碼：

![雪球角色](images/snowball-sprite.png)

```blocks3
when I receive [丟 v]
switch costume to (雪球 v)
repeat until < touching [邊緣 v]? >
    move (力量) steps
+   change [力量 v] by (-0.25)
end
hide
```

--- /task ---


--- task ---

測試此新程式-它是否如預期工作？ 你可能會注意到力量不斷降低，雪球最後向後移動！

要解決此問題，您可以添加` 如果` {：class =“ block3control”}積木到您的程式，以使力量僅在大於0時才會降低：

![雪球角色](images/snowball-sprite.png)

```blocks3
when I receive [丟 v]
switch costume to (雪球 v)
repeat until < touching [邊緣 v]? >
    move (力量) steps
+   if < (力量) > (0) > then
        change [力量 v] by (-0.25)
    end
end
hide
```

--- /task ---

--- task ---

你快要完成了，但是你還需要在雪球上添加一些重力，以使其落在地上。 您可以使用以下程式透過連續向下移動雪球來增加重力：

![雪球角色](images/snowball-sprite.png)

```blocks3
when I receive [丟 v]
switch costume to (雪球 v)
repeat until < touching [邊緣 v]? >
+   change y by (-5)
    move (力量) steps
    if < (力量) > (0) > then
        change [力量 v] by (-0.25)
    end
end
hide
```

--- /task ---

--- task ---

再次測試你的雪球，您應該看到雪球的運動更加真實。

--- /task ---

