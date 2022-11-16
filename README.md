### Πρώτα απ'όλα είναι σημαντικό να σημειωθεί ότι αυτό το guide δε θα είχε φτιαχτεί χωρίς την καθοδήγηση της ομάδας: [second-time-is-the-charm](https://github.com/second-time-is-the-charm) <br> Πιο συγκεκριμένα του συμφοιτητή :
| github profile | ονοματεπωνυμο | ΑΜ |
| --- | --- | --- | 
|[artopodama](https://github.com/artopodama/) | Giannis Anastasopoulos | inf2021017 |
# ΕΙΝΑΙ ΣΗΜΑΝΤΙΚΟ ΟΙ ΠΑΡΑΚΑΤΩ ΟΔΗΓΙΕΣ ΝΑ ΑΚΟΛΟΥΘΗΘΟΥΝ ΑΚΡΙΒΩΣ ΧΩΡΙΣ ΝΑ ΠΡΟΣΠΕΡΑΣΤΕΙ ΚΑΠΟΙΟ ΒΗΜΑ:
# pandoc: `Eγκατάσταση και Set up` 
1. Eκτελείτε την εντολή `sudo pacman -S pandoc`
2. Τσεκάρετε αν σας έχει κατέβει με την εντολή `pandoc --version` (Αν σας δείχνει απο κάτω το version του pandoc σημαίνει ότι το έχετε κατεβάσει π.χ. `pandoc 2.19.2`)
3. Μετά εγκαταστείτε την εντολή pip εκτελόντας την εντολή `sudo pacman -S python-pip`
4. Μετά: `sudo pip install pandoc-fignos`
5. Eκτείλεται `which pandoc` και μετά `which python` και τσεκάρετε ότι βρίσκεται στο ίδιο directory π.χ. αν λέει `/usr/bin/pandoc` και μετά `/usr/bin/python` είστε εντάξει 
# OPTIONAL: `εγκατάσταση lua`
1. Kατεβάζεται το lua με την εντολή `sudo pacman -S lua` 
# Παραδοτέο 6
### Δημιουργία αποθετηρίου:
1. Μπαίνετε πρώτα στο συγκεκριμένο github αποθετήριο: [kallipos](https://github.com/mibook/kallipos)
2. Το κάνετε `fork` στο δικό σας αποθετήριο.
3. Πάτε στο terminal και εκτελείte την εντολή: `git clone https://github.com/'το username sas'/kallipos`
4. Μετά την εντολή `cd kallipos`
### Πρόσθεση των submodules:
5. Εκτελείται τις παρακάτω εντολές με την σειρά:
    ```
    git submodule update --remote --init
    git submodule update --remote --merge
    ```
### Έλεγχος στα settings:
6. Πηγαίνετε στα settings του υπολογιστή σας
7. Γράφετε στο search `fonts`
8. Πατάτε click πάνω στο fonts
9. Τσεκάρετε αν δίπλα από το `General:` λέει `Noto Sans 10pt`.
10. Αν `ναι` συνεχίστε κανονικά, αν `όχι` τότε αλλάξτε τα έτσι ώστε να είναι όπως παρακάτω: 
  ```
  General: Noto Sans 10pt
  Fixed width: Hack 10pt
  Small: Noto Sans 8pt
  Toolbar: Noto Sans 10pt
  Menu: Noto Sans 10pt
  Window title: Noto Sans 10pt
  ```

### Επεξεργασία του αρχείου `make-latex.sh`
11. Ανοίγετε τον φάκελο `kallipos`
12. Φτιάχνετε έναν νέο φάκελο με το όνομα `latex`
13. Ανοίγετε το αρχείο `make-latex.sh`
14. Εκεί που λέει `sed -i '' 's+Figure+Εικόνα+g' ./latex/ch0*` στο τέλος του αρχείου βάζετε το σήμα `#` ώστε να γίνει έτσι <br>
`# sed -i '' 's+Figure+Εικόνα+g' ./latex/ch0*`
15. Στη συνέχεια κάνετε copy-paste στο τέλος του αρχείου τα παρακάτω:
  ```
  pandoc -s latex/*.tex -o book.tex
pandoc -N --quiet --variable "geometry=margin=1.2in" --variable mainfont="Noto Sans Regular" --variable sansfont="Noto Sans Regular" --variable monofont="Noto Sans Regular" --variable fontsize=12pt --variable version=2.0 book.tex  --pdf-engine=xelatex --toc -o book.pdf
  ```
16. Βγαίνεται από το αρχείο `make-latex.sh` και ξαναπάτε πίσω στον φάκελο `kallipos`
### Επιλογή θέματος:
17. Μπαίνετε στον φάκελο `text` διαλέγεται ένα μόνο από τα `ch0(από το 1-8).txt` αρχεία και το ανοίγετε
18. Διαβάζεται κυρίως την περίληψη του κάθε κεφαλαίου (δηλαδή του κάθε `ch0(από το 1-8).txt` αρχείου)
19. Βλέπεται για το πάνω σε τι αναφέρεται το κεφάλαιο
20. Ψάχνεται ένα μέρος (κάτω απο κάποια παράγραφός) στο οποίο θα μπορούσατε να αναπτύξετε το κείμενο και να ταιριάζει με το περιεχόμενο του βιβλίου.
(π.χ. αν μιλάει για την apple θα πρέπει να γράψετε μία παράγραφος με πληροφορίες που να αφορούν την apple τροποποιώντας το ώστε να ταιριάζει με το κείμενο του βιβλίου ) <br> 
`Σαν δηλαδή μια υποσημείωση μέσα στο κείμενο του βιβλιου`
21. Δημιουργείται το περιεχόμενο σας με βάση το βήμα `20.` δηλαδή μία παράγραφος με έναν τίτλο.
22. Δημιουργείται ένα αρχείο `.md` με το όνομα του θέματος σας το οποίο θα περιέχει: 
    ```
    ---
    title: Ο τιτλος σας
    caption: 'Το περιεχομενό σας'
    name: το ονοματεπώνυμό σας 
    id: Ο αριθμος μητρωου σας 
    ---
    ```
### Πρόσθεση του θέματος στο βιβλίο:
23. Στο σημείο που επιλέξατε να το τοποθετήσετε πατήστε `enter` γράψτε `![](Το_Όνομα_Tου_MD_Αρχείου_σας.md){.Το_Όνομα_Tου_LUA_Αρχείου_σας}` <br>
π.χ `![](iphone.md){.iphone}` και μετα παλι `enter` αλλιως δε θα το δεχτει.
### Δημιουργία `.lua` αρχείου:
24. ξαναπάτε πίσω στον φάκελο `kallipos`
25. Δημιουργείτε έναν φάκελο με ένα όνομα της επιλογής σας 
27. Mέσα σε αυτόν τοποθετείτε το .md file σας
28. ξαναπάτε πίσω στον φάκελο `kallipos`
29. Φτιάχνετε ένα αρχείο `.lua` π.χ. MyFilter.lua (με ονομα της επιλογής σας)
30. το ανοίγετε και κάνετε copy-paste το παρακάτω: 
  ```
function Image(img)
      if img.classes:find('epigraph',1) then
        local f = io.open("quotes/" .. img.src, 'r')
        local doc = pandoc.read(f:read('*a'))
        f:close()
        local caption = pandoc.utils.stringify(doc.meta.caption) 
        local name = pandoc.utils.stringify(doc.meta.name)
        local am = pandoc.utils.stringify(doc.meta.id)
        local content = "> " .. caption .. "  \n>" .. "Ονοματεπωνυμο Φοιτητη:" .. name .. "Aριθμος Mητρωου:" .. am
        return pandoc.RawInline('markdown',content)
      end
end
  ```
 ΥΠΟΣΗΜΕΙΩΣΗ:
> Καλό θα ήταν στο παραπάνω φίλτρο γίνουν οι κατάλληλες αλλαγές έτσι ώστε το φίλτρο να μην είναι ίδιο με το αρχικό για παράδειγμα βάζοντας εκεί που λέει `local content = "> " .. caption .. "  \n>" .. "Ονοματεπωνυμο Φοιτητή:" .. name .. "Aριθμος Mητρωου:" .. AM `  να βάλετε ανάμεσα αντί για `..."> " .. caption .. " \n> "...` να γράψετε `..."> _" .. caption .. "_  \n> "...`  ώστε η παράγραφός σας να είναι bold italic κλπ .. Για περισσότερες πληροφορίες θα σας βοηθήσει το link [Pandoc markdown Syntax](https://garrettgman.github.io/rmarkdown/authoring_pandoc_markdown.html)    
31. Αλλάζετε το ` 'epigraph' ` στο όνομα του `.lua` αρχείου σας (χωρίς το `.lua`) και το `"quotes/"` στο όνομα του directory που έχετε μέσα το `.md` αρχείο σας
32. Μπαινετε στο αρχειο `make-latex.sh` και θα βρειτε αυτη την εντολη μεσα απο το αρχειο:
   ```
   for filename in text/ch*.txt; do
   [ -e "$filename" ] || continue
    pandoc --lua-filter=extras.lua "$filename" --to markdown | pandoc --lua-filter=extras.lua --to markdown | ΕΔΩ |pandoc --lua-filter=epigraph.lua --to markdown |  pandoc --lua-filter=figure.lua --to markdown | pandoc --lua-filter=footnote.lua --to markdown | pandoc --filter pandoc-fignos --to markdown | pandoc --metadata-file=meta.yml --top-level-division=chapter --citeproc --bibliography=bibliography/"$(basename "$filename" .txt).bib" --reference-location=section --wrap=none --to latex > latex/"$(basename "$filename" .txt).tex" 
done 
   ```
 33. Eκει που εχω γραψει τη λεξη `ΕΔΩ` θα γραψετε την εντολη `pandoc --lua-filter=Το_Όνομα_Tου_LUA_Αρχείου_σας.lua --to markdown`
 34. βαζοντας το `.lua` Αρχείο σας εκει που λεω `Το_Όνομα_Tου_LUA_Αρχείου_σας.lua`
 35. θα την κανετε `copy` και θα την αντικαταστησετε με την προηγουμενη εντολη. (την αρχικη)
 ### Δημιουργια του Βιβλιου σε pdf:
 36. θα δημιουργησετε ενα φακελο `mypictures/` μεσα στον φακελο `kallipos/`
 37. θα δημιουργησετε ενα φακελο `book/` μεσα στον φακελο `kallipos/`
 38. θα τρεξετε στο terminal την εντολη `./make-latex.sh`
 39. θα μεταφερεται το `book.pdf` απο τον φακελο `kallipos` στον φακελο `book`
 40. θα ανοιξετε το book.pdf και `θα κανετε screenshot το περιεχομενο σας` αλλα θα πρεπει να φαινεται η σελιδα και να πειτε ποιο κεφαλαιο επιλεξατε
 41. θα μεταφερεται το screenshot στον φακελο `mypictures/`
 42. και θα γραψετε στο terminal τις παρακατω εντολες μεσα απο το directory `kallipos/`:
     ```
     git add .
     git commit -m "update book"
     git push origin
     ```
 43. γραφετε το username και το token σας
# Optional: 
## PDF ENGINE Πρόβλημα κατά την εκτέλεσης της εντολής `./make-latex.sh`:
1. Αν δεν σας επιτρέπει να εκτελέσεται το `./make-latex.sh` λόγο του `--pdf-engine=Xelatex` τότε θα πρέπει να εκτελέσετε την παρακάτω εντολή 
```
sudo pacman -S texlive-core
```
 ### Δημιουργία παραδοτέου:
 44. Στη συνέχεια στο discussions θα βάλετε:
     - ως εικόνα την screenshot που βγάλατε 
     - link από το repository στο github στο οποίο έχετε το αρχείο `.lua` η αλλιώς το φίλτρο σας
     - link από το repository στο github στο οποίο έχετε το book.pdf
     - link από το repository στο github στο οποίο έχετε το αρχειο `.md` σας
     - link από το repository στο github στο οποίο έχετε το screenshot σας
     - link την αναφορά σας
 45. Τελος
made by: [OMADA12](https://github.com/OMADA12)
