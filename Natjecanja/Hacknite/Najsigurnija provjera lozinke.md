# Dobiveno
## Najsigurnija provjera lozinke

### 40

Ivan je oduvijek htio znati kako najbolje provjeriti je li upisana lozinka točna ili ne. Nakon dugo istraživanja, otkrio je na koji način bi to mogao napraviti. U tu svrhu, smislio je jednu jako dobru lozinku i napravio stranicu kako bi testirao tu svoju ideju.

Flag je u formatu CTF2021[brojevi]

[http://chal.platforma.hacknite.hr:10006](http://chal.platforma.hacknite.hr:10006/)

# Walkthrough
Zbog [[Raspršeni podatci#Prvo pravilo]] otići u source kod. U `<script>` se nalazi logika provjeravanja lozinke. Objasniti kod. Postaviti pitanje kako sada. Otići u file koji se nalazi u logici kada je točno napisana šifra. Objasniti što je hash funkcija

## Točno
`CTF2021[999135193693]`
# Hash function
Funkcija koja je jako jednostavna za napraviti, ali jako teško za napraviti inverznu funkciju.
Za dešifriranje hash funkcije nema _pametnog_ načina. nego se treba koristiti [[Najsigurnija provjera lozinke#Bruteforce]]

# Bruteforce
Pokušati sve moguće šifre, i gledati koja je točna.

