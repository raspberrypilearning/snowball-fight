## Δημιουργώντας μία χιονόμπαλα

Ας φτιάξουμε μια χιονόμπαλα, που μπορείς να ρίξεις στο σκηνικό σου.

--- task ---

Άνοιξε το αρχικό έργο Scratch.

**Σε σύνδεση**: άνοιξε το [αρχικό έργο]https://scratch.mit.edu/projects/399207135){:target="_blank"}.

Αν έχεις λογαριασμό Scratch μπορείς να κάνεις ένα αντίγραφο, κάνοντας κλικ στο κουμπί **Ανάμειξη**.

**Εκτός σύνδεσης**: άνοιξε το [αρχικό έργο](https://rpf.io/p/el-GR/snowball-fight-go){:target="_blank"} στον επεξεργαστή εκτός σύνδεσης.

Αν χρειαστεί να κατεβάσεις και να εγκαταστήσεις τον offline editor για το Scratch, μπορείς να το βρεις στο [rpf.io/scratchoff](https://rpf.io/scratchoff){:target="_blank"}.

Στο αρχικό έργο, θα δεις ένα λευκό σκηνικό και ένα αντικείμενο χιονόμπαλα.

--- /task ---

--- task ---

Το αντικείμενο «Χιονόμπαλα» περιέχει 2 ενδυμασίες, μία κανονική και μία που δείχνει προς ποια κατεύθυνση είναι στραμμένη η χιονόμπαλα.

![ενδυμασίες χιονόμπαλα](images/snow-costume.png)

--- /task ---

--- task ---

Αρχικά, ας επιτρέψουμε στον παίκτη να αλλάξει τη γωνία ρίψης της χιονόμπαλας. Πρόσθεσε αυτόν τον κώδικα στο αντικείμενο της χιονόμπαλας:

![αντικείμενο χιονόμπαλα](images/snowball-sprite.png)

```blocks3
when flag clicked
wait (0.5) seconds
go to x:(-200) y:(-130)
point in direction (90)
switch costume to (χιονόμπαλα-στόχος v)
repeat until <mouse down?>
    point towards (mouse-pointer v)
end
```

--- /task ---

--- task ---

Δοκίμασε το έργο σου κάνοντας κλικ στην πράσινη σημαία. Θα δεις ότι η χιονόμπαλα ακολουθεί το ποντίκι, μέχρι να πατήσεις το κουμπί του ποντικιού.

![αντικείμενο χιονόμπαλα-στόχος που δείχνει προς το ποντίκι](images/snow-mouse.png)

--- /task ---

--- task ---

Ας επιτρέψουμε επίσης στον παίκτη να αποφασίσει με πόση δύναμη θα εκτοξευτεί η χιονόμπαλα. Δημιούργησε μία νέα μεταβλητή με όνομα `δύναμη`{:class="block3variables"}.

[[[generic-scratch3-add-variable]]]

--- /task ---

--- task ---

Σύρε το νέο παράθυρο της μεταβλητής στο κάτω μέρος του σκηνικού, κοντά στη χιονόμπαλα. Κάνε δεξί κλικ στο παράθυρο της μεταβλητής και ξανά κλικ στη "γραμμή κύλισης".

![αλλαγή μεταβλητής στη γραμμή κύλισης](images/snow-slider.png)

--- /task ---

--- task ---

Πρόσθεσε κώδικα για να ορίσεις τη νέα σου μεταβλητή `δύναμη`{:class="block3variables"} ίση με 0 όταν γίνεται κλικ στη σημαία.

![αντικείμενο χιονόμπαλα](images/snowball-sprite.png)

```blocks3
when flag clicked
+ set [δύναμη v] to (0)
```

--- /task ---

--- task ---

Τώρα που έχεις τη μεταβλητή `δύναμη`{:class="block3variables"}, μπορείς να αυξήσεις τη δύναμη εκτόξευσης της χιονόμπαλας _μετά_ την επιλογή κατεύθυνσης, με αυτόν τον κώδικα:

![αντικείμενο χιονόμπαλα](images/snowball-sprite.png)

```blocks3
repeat until <mouse down?>
    point towards (mouse-pointer v)
end
+repeat until < not <mouse down?> >
    point towards (mouse-pointer v)
    change [δύναμη v] by (1)
    wait (0.1) seconds
end
```

Αυτός ο κώδικας σημαίνει ότι πρέπει να _κρατήσεις πατημένο το κουμπί του ποντικιού_ αφού επιλέξεις την κατεύθυνση, για να επιλέξεις τη δύναμη εκτόξευσης της χιονόμπαλας.

--- /task ---

--- task ---

Δοκίμασε τη χιονόμπαλά σου, για να δεις αν μπορείς να επιλέξεις τη γωνία και τη δύναμη της εκτόξευσης.

![μεταβλητή δύναμης στην τιμή 35 κοντά στη χιονόμπαλα-στόχος](images/snow-test.png)

--- /task ---
