# Yleistä
Tämä [dmrconfig](https://github.com/sergev/dmrconfig) kooditulppa sisältää kaikki OH:n FM- sekä DMR-toistimet. Tiedot on poimittu sivuilta https://automatic.sral.fi sekä https://findmr.wordpress.com/findmr-puheryhmat/.

# Huomioita
Tulpan luonnissa on jouduttu käyttämään kompromisseja, esim. kontaktien määrä on tietyissä radioissa rajattu tuhanteen. Paikalliset DMR-toistimet on määritelty niin, että siellä ovat yleiset kansainväliset ryhmät, koko suomen OH-ryhmä sekä toistimen paikallinen ryhmä. Esim. Pasilan DMR toistimella on paikallinen OH2 puheryhmä ’2442 FI OH2’.

# Ohjeet
Lataa [dmrconfig](https://github.com/sergev/dmrconfig/wiki#releases) binäärit omalle käyttöjärjestelmällesi. Muokkaa kooditulpan loppuun oma DMR ID:si sekä mahdollinen tervehdysviesti.
```
# Unique DMR ID and name of this radio.
ID: 1234567
Name: GD-77

# Text displayed when the radio powers up.
Intro Line 1: OMAKUTSU
Intro Line 2: 
```

Ohjelmoi radio käyttäen koodiplugia. Ennen kirjoittamissa dmrconfig kirjoittaa sen hetkisen ohjelmoinnin tiedostoon "backup.img".
```
dmrconfig -c oh-repeaters.conf
Connect to Radioddity GD-77.
Read device: ############################# done.
Last Programmed Date: 2019-01-27 15:54
Write codeplug to file 'backup.img'.
Read configuration from file 'oh-repeaters.conf'.
Total 287 channels, 21 zones, 1 scanlists, 33 contacts, 2 grouplists.
```

Jos jokin menee pieleen, voit palauttaa radion takaisin alkuperäiseen tilaan:
```
dmrconfig -w backup.img
```
## Kontribuutiot
Mahdollisista virheistä tai ehdotuksista kannattaa luoda issue GitHubiin.
