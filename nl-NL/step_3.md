## Een sneeuwbal gooien

--- task ---

Voeg een blok toe aan het _einde_ van je sneeuwbal code, naar `zend signaal`{:class="block3control"} voor het gooien van een sneeuwbal:

![sneeuwbal sprite](images/snowball-sprite.png)

```blocks3
wanneer op groene vlag wordt geklikt
maak [kracht v] (0)
wacht (0.5) sec.
ga naar x:(- 200) y:(- 130)
richt naar (90) graden
verander uiterlijk naar (snowball-aim v)
herhaal tot <muis ingedrukt?>
    richt naar (muisaanwijzer v)
einde
herhaal tot < niet <muis ingedrukt?> >
    richt naar (muisaanwijzer v)
    verander [kracht v] met (1)
    wachten (0.1) sec.
einde
+ zend signaal (gooi v) en wacht
```

--- /task ---

--- task ---

Voeg deze code toe aan je sneeuwbal, zodat hij beweegt tot hij de rand van het speelveld bereikt:

![sneeuwbal sprite](images/snowball-sprite.png)

```blocks3
wanneer ik signaal [gooi v] ontvang
verander uiterlijk naar (snowball v)
herhaal tot < raak ik [rand v]? >
    neem (kracht) stappen
einde
verdwijn
```

De code gebruikt de variabele `kracht`{:class="block3variables"} om te beslissen hoe snel je je verplaatst.

--- /task ---

--- task ---

Nu je de sneeuwbal verbergt wanneer deze de rand raakt, voeg je code `verschijn`{:class="block3looks"} toe aan de sneeuwbal wanneer op de vlag wordt geklikt, _vlak_ nadat de sneeuwbal overschakelt naar het `snowball-aim`{:class="block3looks"} uiterlijk.

![sneeuwbal sprite](images/snowball-sprite.png)

```blocks3
wanneer op de groene vlag wordt geklikt
maak [kracht v] (0)
wacht (0.5) sec.
ga naar x:(- 200) y:(- 130)
richt naar (90) graden
verander uiterlijk naar (snowball-aim v)
+verschijn
herhaal tot <muis ingedrukt?>
    richt naar (muisaanwijzer v)
einde
herhaal tot < niet <muis ingedrukt?> >
    richt naar (muisaanwijzer v)
    verander [kracht v] met (1)
    wachten (0.1) sec.
einde
zend signaal (gooi v) en wacht
```

--- /task ---

--- task ---

Test je sneeuwbal een paar keer. Beweegt het onder verschillende hoeken en verschillende snelheden?

--- /task ---

--- task ---

Als je je sneeuwbal vaak wilt gooien, voeg je gewoon een `herhaal`{:class="block3control"} lus rond je sneeuwbal `wanneer op de groene vlag wordt geklikt`{:class="block3events"} code toe.

![sneeuwbal sprite](images/snowball-sprite.png)

```blocks3
wanneer op de groene vlag wordt geklikt
+herhaal
maak [kracht v] (0)
wacht (0.5) sec.
ga naar x:(- 200) y:(- 130)
richt naar (90) graden
verander uiterlijk naar (snowball-aim v)
verschijn
herhaal tot <muis ingedrukt?>
    richt naar (muisaanwijzer v)
einde
herhaal tot < niet <muis ingedrukt?> >
    richt naar (muisaanwijzer v)
    verander [kracht v] met (1)
    wachten (0.1) sec.
einde
zend signaal (gooi v) en wacht
einde
```

--- /task ---
