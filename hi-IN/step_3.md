## बर्फ़गोला फेकना

--- task ---

एक ब्लॉक अपने बर्फ़गोले के कोड के _अंत_ में जोड़ें ताकि सबको `broadcast`{:class="block3control"} (प्रसारित) हो सके कि आप बर्फ़गोला फ़ेंक रहे हैं:

![snowball sprite](images/snowball-sprite.png)

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

इस कोड को अपने बर्फ़गोले में जोड़ें ताकि वो हिलता रहे जब तक वह मंच के किनारे न पहुँच जाए:

![snowball sprite](images/snowball-sprite.png)

```blocks3
when I receive [throw v]
switch costume to (snowball v)
repeat until < touching [edge v]? >
    move (power) steps
end
hide
```

यह कोड `power`{:class="block3variables"} (शक्ति) वेरिएबल का उपयोग करेगा यह तय करने के लिए कि कितनी तेजी से चलना चाहिए।

--- /task ---

--- task ---

क्योंकि अब आप बर्फ़गोले को छिपायेगा जब वह स्क्रीन के कोने को छूता है तो ज़रूरी है कि आप बर्फ़गोले पर `show`{:class="block3looks"} कोड जोड़ें जब हरे झंडे पर क्लिक किया जाये, _ठीक बाद_ जब बर्फ़गोला अपना पोशाक (costume) `snowball-aim`{:class="block3looks"} में बदलता है ।

![snowball sprite](images/snowball-sprite.png)

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

अपने बर्फ़गोले को कुछ दफे परिक्षण करें । क्या यह विभिन्न कोणों (angles) और अलग-अलग गति से चलता है?

--- /task ---

--- task ---

यदि आप अपना बर्फ़गोला बहुत बार फेंकना चाहते हैं तो बस `forever`{:class="block3control"} (हमेशा के लिए) लूप अपने बर्फ़गोले के चारों ओर `when flag clicked`{:class="block3events"} कोड में जोड़ें ।

![snowball sprite](images/snowball-sprite.png)

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
