# Dobiveno
## Kemijske reakcije

### 45

Maja je profesorica kemije, nedavno je naučila Javascript pa je odlučila napraviti web aplikaciju na koju će stavljati nastavne materijale. Ipak, još nije skroz zadovoljna izgledom stranice pa je odlučila sakriti neke funkcionalnosti.

[http://chal.platforma.hacknite.hr:12001/](http://chal.platforma.hacknite.hr:12001/)

Flag je u formatu CTF2023[brojevi].

# Walkthrough
[[Raspršeni podatci#Prvo pravilo]] dovodi do 2 file-a. `2.010c019a.chunk.js` pogledati, `ctrl + F` _CTF_ ne vrača ništa, preveliki file, otići u drugi. `main.2cb89abf.chunk.js` ružno izgleda. Koristiti **Inspect source** tab. `fetch("/api/b3c865a0-4d24-420d-a055-34be59d0c8fb/flag");` izgleda zanimljivo, odi na tu stranicu.

## Točno
`CTF2023[041376109532]`