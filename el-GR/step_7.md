## Αυτοκινούμενο κουνούπι

Εντάξει, τώρα ήρθε η ώρα να κάνεις τα κουνούπια να πετούν μόνα τους. Για να το κάνεις αυτό, θα χρειαστείς ένα νέο είδος μπλοκ από την κατηγορία **Έλεγχος**.

--- task ---

Επίλεξε το αντικείμενο κουνούπι και σύρε ένα μπλοκ `όταν γίνει κλικ σε πράσινη σημαία`{:class="block3events"} από τα **Συμβάντα**, ένα μπλοκ `για πάντα`{:class="block3control"} από τον **Έλεγχο**, και ένα μπλοκ `κινήσου 10 βήματα`{:class="block3motion"} από την **Κίνηση** στην **περιοχή του επιλεγμένου αντικειμένου**, ως εξής:

```blocks3
+    when green flag clicked
+    forever
        move (10) steps
    end
```

--- /task ---


--- collapse ---
---
title: Τι κάνει το νέο μπλοκ;
---

Τα μπλοκ **Ελέγχου** επιτρέπουν στο πρόγραμμά σας να κάνει πράγματα ορισμένες φορές ή υπό ορισμένες συνθήκες.

Εδώ, το κουνούπι εκτελεί όποια εντολή βρίσκεται μέσα στο μπλοκ `για πάντα`{:class="block3control"} ξανά και ξανά σε ένα βρόχο, για πάντα. Μόλις φτάσει στο τέλος, επιστρέφει στην κορυφή του μπλοκ και ξεκινά ξανά.

--- /collapse ---

--- task ---

Τώρα κάνε κλικ στην πράσινη σημαία και δες τι συμβαίνει!

--- /task ---

Λοιπόν, εκείνο το κουνούπι μόλις κουτούλησε στο πλάι της σκηνής και κινούνταν πολύ γρήγορα για να το πιάσει ο παπαγάλος.

Πρώτον, πρέπει να κάνεις το κουνούπι πιο αργό. Αυτό είναι πραγματικά πολύ εύκολο, απλά χρειάζεται να περιμένει λίγο αφού μετακινηθεί για 10 βήματα. Υπάρχει ένα μπλοκ στον **Έλεγχο** που θα σε βοηθήσει εδώ:

```blocks3
    wait (1) secs
```

--- task ---

Βάλε το μπλοκ `περίμενε`{:class="block3control"} στον κώδικά σου, και άλλαξε το νούμερο σε `0.5`, όπως:


```blocks3
    when green flag clicked
    forever
        move (10) steps
+        wait (0.5) secs
    end
```

--- /task ---

--- collapse ---
---
title: Κάνοντας προσαρμογές
---

Ο αριθμός που όρισες στο μπλοκ `περίμενε`{:class="block3control"} λέει πόσα **δευτερόλεπτα** θες να περιμένει το κουνούπι. Το `0.5` είναι μισό δευτερόλεπτο.

Μπορείς να δοκιμάσεις διαφορετικές τιμές για να δεις ποια είναι η καλύτερη για το παιχνίδι σου. Να θυμάσαι ότι μπορείς επίσης να αλλάξεις τον αριθμό των βημάτων!

--- /collapse ---

Το κουνούπι κινείται τώρα, αλλά πρέπει να αναπηδάει και από την άκρη της σκηνής. Και πάλι, υπάρχει ένα μπλοκ στην **Κίνηση ** γι' αυτό!

--- task ---

Βρες το μπλοκ `εάν σε όριο, αναπήδησε`{:class="block3motion"} και βάλε το μετά το μπλοκ `περίμενε`{:class="block3control"}.

--- /task ---

--- collapse ---
---
title: Τι κάνει το νέο μπλοκ;
---

Το μπλοκ `εάν σε όριο, αναπήδησε`{:class="block3motion"} ελέγχει εάν το αντικείμενο αγγίζει την άκρη της σκηνής και, εάν αγγίζει, στρίβει αριστερά, δεξιά, πάνω ή κάτω, ανάλογα με την περίπτωση.

--- /collapse ---

Φυσικά, αυτό θα οδηγήσει σε κουνούπι που κινείται ανάποδα, οπότε χρειάζεσαι πάλι ένα μπλοκ `όρισε τρόπο περιστροφής`{:class="block3motion"}.

--- task ---

Ενημέρωσε τον κώδικά σου για να ορίσεις τον τρόπο περιστροφής του κουνουπιού `αριστερά-δεξιά`{:class="block3motion"}:

```blocks3
    when green flag clicked
+    set rotation style [left-right v]
    forever
        move (10) steps
        wait (0.5) secs
        if on edge, bounce
    end
```

--- /task ---

Το κουνούπι κινείται προς τα πίσω και προς τα εμπρός τώρα, αλλά μόνο σε ευθεία γραμμή - αρκετά εύκολο για να το πιάσει ο παίκτης με τον παπαγάλο! Πρέπει να κάνεις το κουνούπι λιγότερο προβλέψιμο.

Γνωρίζεις ήδη από ένα προηγούμενο βήμα πώς να κάνεις μια στροφή του αντικειμένου, οπότε ξεκίνα από εκεί!

--- task ---

Πρόσθεσε μια στροφή στο κουνούπι και κάνε κλικ στην πράσινη σημαία.

```blocks3
    when green flag clicked
    set rotation style [left-right v]
    forever
        move (10) steps
+        turn cw (10) degrees
        wait (0.5) secs
        if on edge, bounce
    end
```

--- /task ---

Είναι καλύτερα τώρα, αλλά ακόμα είναι προβλέψιμη η κατεύθυνση του κουνουπιού. Πρέπει να είναι πιο τυχαία η κίνηση. Ευτυχώς, το Scratch μπορεί να κάνει τυχαία πράγματα για σένα! Θα χρειαστείς απλώς μια νέα κατηγορία μπλοκ, που ονομάζονται **Τελεστές**.

--- collapse ---
---
title: Τι είναι ένας τελεστής;
---

Οι **Τελεστές** λαμβάνουν μία ή περισσότερες τιμές (όπως αριθμούς, κείμενο ή τιμές True - αληθές / False - ψευδές) και επιστρέφουν πίσω μία μόνο τιμή. Μπορείς να καταλάβεις τι είδους τιμή θα επιστρέψει βλέποντας το σχήμα του μπλοκ: τα στρογγυλά άκρα επιστρέφουν αριθμούς ή κείμενο, τα μυτερά άκρα επιστρέφουν True/False.

```blocks3
    (() + ())

    (join [γεια ] [κόσμε])

    <[] = []>
```

--- /collapse ---

--- task ---

Βρες το μπλοκ `επίλεξε τυχαίο`{:class="block3operators"} στους **Τελεστές** και βάλε το μέσα στο μπλοκ `στρίψε μοίρες`{:class="block3motion"} στην **Κίνηση**, κάνοντας κλικ και σύροντάς το στο αριθμητικό πεδίο όπου κανονικά ορίζεις τις μοίρες.

```blocks3
    when green flag clicked
    set rotation style [left-right v]
    forever 
        move (10) steps
+        turn cw (pick random (1) to (10)) degrees
        wait (0.5) secs
        if on edge, bounce
    end
```

--- /task ---

**Σημείωση**: μπορείς να αλλάξεις τους ελάχιστους και μέγιστους αριθμούς που θα επιστρέψει, αλλά οι προεπιλεγμένες τιμές (`1` και `10`) είναι αρκετά καλές για αυτό το παιχνίδι, οπότε μπορείς να τις κρατήσεις.

--- task ---

Κάνε κλικ στην πράσινη σημαία για να δοκιμάσεις το παιχνίδι σου!

--- /task ---
