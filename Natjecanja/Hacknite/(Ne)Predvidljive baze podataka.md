# Dobiveno
## (Ne)Predvidljive baze podataka

### 40

Ivica nije veliki fan baza podataka, ali su mu bile potrebne tijekom izrade njegove web stranice. Budući da mu je zabavnije baviti se htmlom i uređivati svoju stranicu, vrlo malo vremena je posvetio izradi baze podataka, i napravio je samo jednu tablicu za sve podatke koje su mu bili potrebni. Unutra je stavio i neke stvari koje ne pripadaju toj tablici, ali mu se više nije dalo išta mijenjati, htio je posvetiti još vremena uređivanju svoje stranice.

Kasnije je Ivica još jednom pregledao svoju bazu podataka, ali nije vidio nikakav sigurnosni propust.

[http://chal.platforma.hacknite.hr:10009](http://chal.platforma.hacknite.hr:10009/)

Flag je u formatu CTF2021[brojevi]

# Walkthrough
Otići na stranicu. [[Raspršeni podatci#Prvo pravilo]] ne dovodi do ničega. Probati funkcionalnost aplikacije. Upload-ati neki mali file. Source kod ne daje ništa. Probati ponovno funkcionalnost. Pogledati source kod međustranice. Id svih file-ova u DB se gleda pomoću id-a u URL-u. Mijenjati id-eve dok ne dođe onaj dobar. Id mora biti **8**. 

## Točno
`CTF2021[678150322801]`
