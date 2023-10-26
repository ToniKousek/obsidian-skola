# Dobiveno
## Full-stack web developer

### 50

Ivica želi postati full-stack web developer kada odraste. Za sada još uči kako raditi web stranice te je nedavno napravio svoju prvu web stranicu. Uspješno je instalirao Linux na računalo, konfigurirao Nginx i složio web stranicu kombinacijom HTML-a, CSS-a i JavaScripta.

Jedna od stvari na koju je ponosan je dio stranice na kojoj se Ivica kao administrator može prijaviti. No Ivica je ipak oprezan, i prije puštanja stranice u produkciju zamolio je tebe da pogledaš njegovu web stranicu i provjeriš je li ona sigurna.

Je li web stranica spremna za objavu ili Ivica ipak treba još na nečemu poraditi?

Flag je u formatu CTF2020[brojevi]

[http://chal.platforma.hacknite.hr:11007](http://chal.platforma.hacknite.hr:11007/)

## Točno
`CTF2020[832127725255]`

# Walkthrough
U _početna stranica_ nema ničega posebnog. _Administracija web stranice_ izgleda kao ono što tražimo. U kodu pronalazimo 2 hardcoded stringa među kojim se nalazi flag. Pronalazimo u korištenje 2 funkcije. `atob()` i `btoa()` : _ascii to base_ i _base to ascii_. Nakon googlanja, nalazimo da je to funkcija koja pretvara ascii tekst u base64. Objasniti da je to način šifriranja podataka. Otići na stranicu base64decode i dekodirati _flag_ string. Objasniti kako lagano pronaći base64 stringove.

## Base64
Vrsta šifriranja podataka.
Lagano za prepoznati jer string ponekad ima **=** na kraju.