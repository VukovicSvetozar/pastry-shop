<h1 align="center">PastryShop</h1>

[English](README.md) | **Srpski**

**PastryShop** je desktop WPF aplikacija za rad pekare ili poslastičarnice: prodaja preko POS ekrana, upravljanje proizvodima i zalihama, korisnički nalozi i izvještaji. Postoje dvije uloge, menadžer i blagajnik, a svaka nakon prijave otvara vlastiti ekran sa svojim funkcijama. Ostatak dokumenta je korisničko uputstvo.

<p align="center">
  <img src="images/17_blagajnik_pos.png" alt="blagajnik pos" width="290"/>
  <img src="images/08_menadzer_proizvodi.png" alt="pregled proizvoda" width="290"/>
  <img src="images/14_menadzer_zalihe.png" alt="zalihe proizvoda" width="290"/>
</p>
<p align="center"><em>POS ekran blagajnika · pregled proizvoda · upravljanje zalihama</em></p>

## Ključne funkcionalnosti

- **Korisnički nalozi i uloge** – dvije uloge (menadžer i blagajnik); menadžer dodaje i uređuje naloge, mijenja ulogu, aktivira i deaktivira naloge i resetuje lozinke.
- **Proizvodi i zalihe** – pregled, dodavanje i uređivanje proizvoda (hrana, piće, pribor), praćenje količina, serija nabavki i rokova trajanja.
- **POS** – kreiranje porudžbina, rad sa korpom, plaćanje gotovinom, karticom ili odloženo, te otkazivanje već kreiranih porudžbina.
- **Izvještaji i statistika** – paneli i grafikoni za prodaju i zalihe (menadžer) i za rad prijavljenog blagajnika.
- **Postavke** – tri teme (svijetla, tamna i plava), srpski i engleski jezik, izmjena profila korisnika.
- **Tastaturne prečice** – za navigaciju i najčešće radnje.

---

## Uloge i prijava

### Uloge u sistemu

Aplikacija razlikuje dvije uloge korisnika.

**Menadžer**
- Ima administrativnu kontrolu nad cijelim sistemom.
- Kreira korisničke naloge i upravlja njima (dodavanje novih i deaktivacija postojećih naloga, resetovanje lozinki).
- Nadzire proizvode i zalihe.
- Ima pristup izvještajima i statistikama.

**Blagajnik**
- Koristi POS interfejs na prodajnom mjestu.
- Kreira porudžbine, naplaćuje ih i pregleda dnevne transakcije.

### Prijava

Menadžer kreira korisničke naloge za zaposlene, dodjeljuje im ulogu i početnu lozinku. Preporuka je da zaposleni lozinku promijene pri prvoj prijavi. Po pokretanju aplikacije otvara se ekran za prijavu sa poljima ***korisničko ime*** i ***lozinka***. Polja su obavezna, dozvoljeni su samo slova i cifre, a definisan je minimalni i maksimalni broj karaktera. Između polja se prelazi tasterom *Tab*.

<p align="center">
  <img src="images/01_prijava.png" alt="Dijagram" height="250" width="350"/>
</p>

Korisnik može promijeniti jezik; kombinacija *Ctrl + L* otvara padajući meni za izbor jezika. Odabrani jezik primjenjuje se samo na stranicu za prijavu.

Nakon klika na dugme ***Prijava*** *(Login)* ili pritiska na *Enter*, sistem provjerava pristupne podatke. Ako su ispravni, evidentira vrijeme prijave i otvara početni ekran u skladu sa ulogom: menadžer dolazi na ekran za rad sa korisničkim nalozima, a blagajnik na POS ekran.

Ako prijava nije uspješna, prikazuje se dijalog upozorenja sa razlogom. Razlozi mogu biti: netačno korisničko ime ili lozinka, nalog nije aktivan, ili nekorektne vrijednosti polja (tada se uz polja prikazuju poruke radi lakše korekcije).

Dugme ***„Otkaži"*** *(Cancel)* služi za izlaz iz aplikacije; prečica je *Escape (Esc)*.

---

## Menadžer

Glavne odgovornosti menadžera:
- upravljanje korisnicima,
- upravljanje proizvodima,
- kontrola zaliha,
- kreiranje izvještaja.

### Prijava i pristup

Po uspješnoj prijavi prikazuje se početni ekran za menadžere.

Sa lijeve strane nalazi se vertikalni ***navigacioni meni*** sa ikonama i nazivima opcija. Svaka opcija ima tastatursku prečicu:

- **Zaposleni** – pregled i upravljanje korisničkim nalozima (*Ctrl + U*).
- **Proizvodi** – katalogizacija i uređivanje proizvoda (*Ctrl + P*).
- **Izvještaj** – pregled i generisanje prodajnih i inventarskih izvještaja (*Ctrl + R*).
- **Postavke** – podešavanje jezika i teme aplikacije (*Ctrl + S*).
- **Profil** – uređivanje profila korisnika (*Ctrl + M*).
- **Odjava** – odjava iz aplikacije (*Esc*).

Sa desne strane je glavni dio u kojem se prikazuje ***sadržaj izabranog modula***: evidencija zaposlenih, stanje zaliha, podaci o proizvodima i izvještaji.

### Upravljanje korisnicima

#### Pregled korisnika

<p align="center">
  <img src="images/03_menadzer_korisnici.png" alt="pregled korisnika" height="250" width="350"/>
</p>

Menadžer ima pristup svim korisnicima aplikacije. Tabela prikazuje *ID, korisničko ime* i *tip korisnika*, uz ikone za *detaljan pregled naloga, promjenu statusa, promjenu lozinke* i druge akcije.

***Polje za pretragu*** omogućava brzo pronalaženje korisnika (*Tab* ili *F3* prebacuje fokus na polje), a padajući meni omogućava ***filtriranje po statusu*** (*Ctrl + F*). Korisnici sa statusom *„neaktivan"* istaknuti su u prikazu.

#### Dodavanje korisnika

Dugme ***Dodaj*** u gornjem desnom uglu glavnog ekrana otvara prozor sa formularom za kreiranje novog korisničkog naloga (*Ctrl + N*). Formular sadrži *zajednička polja* za sve korisnike, dok se *specifična polja* pojavljuju zavisno od izabranog tipa korisnika.

<p align="center">
  <img src="images/04_menadzer_korisnici.png" alt="dodaj korisnika" height="280" width="370"/>
</p>

**Zajednička polja**

- *Tip korisnika* – padajući meni u kojem je obavezno odabrati *Manager* ili *Cashier*,
- *Korisničko ime* – obavezno tekstualno polje; provjerava se jedinstvenost imena, dozvoljeni su samo važeći znakovi, uz minimalnu i maksimalnu dužinu,
- *Lozinka* – obavezno maskirano polje sa sličnim ograničenjima kao korisničko ime,
- *Ime* – tekstualno polje koje dozvoljava samo slova, brojeve i razmake,
- *Prezime* – isto kao polje za ime,
- *Broj telefona* – tekstualno polje koje prihvata samo ispravan format telefonskog broja,
- *Adresa* – slobodno tekstualno polje,
- *Plata* – obavezno numeričko polje koje ne može biti negativno,
- *Putanja do slike (Izaberi sliku)* – dugme za odabir fajla; nakon odabira prikazuje se pregled slike. Dozvoljeni formati: *.jpg, .jpeg, .png*.

**Specijalna polja – Menadžer** (prikazuju se samo kada je izabran menadžer)

- *Odjeljenje* – tekstualno polje koje dozvoljava samo slova, brojeve i razmake.

**Specijalna polja – Blagajnik** (prikazuju se samo kada je izabran blagajnik)

- *ID kase* – numeričko polje koje prihvata samo cijele brojeve,
- *Početak smjene* – kalendar za odabir datuma i vremena; ne može biti u prošlosti,
- *Kraj smjene* – datum i vrijeme; mora biti poslije početka smjene, a smjena mora trajati najmanje jedan sat.

Unos se provjerava prije čuvanja; ako su svi podaci validni, novi korisnički nalog se čuva. U suprotnom se prikazuje dijalog upozorenja, a poruke o greškama prikazuju se i pored nevalidnih polja.

#### Prikaz detalja korisnika

<p align="center">
  <img src="images/05_menadzer_korisnici.png" alt="prikaz detalja korisnika" height="250" width="350"/>
</p>

Klikom na odgovarajuću ikonu za selektovanog korisnika otvara se prozor sa ***detaljnim informacijama***: profilna slika, tip korisnika, korisničko ime, ime i prezime, broj telefona i adresa, datum zaposlenja, plata i posljednja prijava, te dodatni podaci prema tipu korisnika (odjeljenje za menadžera, ID kase i smjene za blagajnika).

#### Uređivanje korisnika

Klikom na odgovarajuću ikonu otvara se prozor za ***uređivanje osnovnih podataka*** vezanih za poslovanje. Moguće je mijenjati *platu*, a zavisno od tipa korisnika i *odjeljenje* (menadžer) ili *ID kase, početak i kraj smjene* (blagajnik).

Važe ista pravila kao pri dodavanju novog korisnika. Polja automatski provjeravaju unos, a čuvanje je onemogućeno dok vrijednosti nisu ispravne. Izmjene se potvrđuju klikom na dugme ili tasterom *Enter*.

#### Promjena tipa korisnika (Menadžer ↔ Blagajnik)

Menadžer može ***promijeniti ulogu*** odabranog korisnika klikom na odgovarajuću ikonu. Sistem prije izvršenja traži potvrdu. Ako se promjena potvrdi, uloga se ažurira, a polja specifična za novu ulogu se po potrebi popunjavaju ili resetuju.

Nije dozvoljeno mijenjati vlastitu ulogu niti ulogu neaktivnog naloga; u oba slučaja prikazuje se dijalog sa upozorenjem.

#### Aktiviranje / deaktiviranje korisnika

Menadžer može privremeno ***onemogućiti*** ili ponovo ***omogućiti*** pristup korisničkom nalogu bez brisanja podataka. Prije promjene statusa sistem traži potvrdu.

Neaktivni korisnik ne može pristupiti sistemu i pri pokušaju prijave dobija odgovarajuću poruku. Dok je nalog deaktiviran, menadžer nad njim ne može izvoditi određene akcije, poput resetovanja lozinke ili promjene uloge.

Nije dozvoljeno deaktivirati vlastiti nalog; takav pokušaj prikazuje dijalog sa upozorenjem da je operacija zabranjena.

#### Resetovanje lozinke

Menadžer može ***generisati privremenu lozinku*** za odabranog korisnika. Nakon uspješnog resetovanja prikazuje se poruka sa privremenom lozinkom koju menadžer može proslijediti korisniku.

Pri sljedećoj prijavi korisnik unosi privremenu lozinku, a zatim je obavezan da postavi novu, sopstvenu lozinku.

Nije dozvoljeno resetovati vlastitu lozinku niti lozinku neaktivnog naloga.

### Upravljanje proizvodima

#### Prikaz proizvoda

Menadžer pregleda sve proizvode asortimana. Pregled prikazuje *ID, naziv, tip proizvoda* (*Hrana, Piće, Pribor*) i *količinu na stanju*, uz ikone za *detaljan pregled*, *uređivanje podataka* proizvoda, *promjenu statusa* i otvaranje prozora za *upravljanje zalihama*.

***Polje za pretragu*** omogućava brzo pronalaženje artikala (*Tab* ili *F3* prebacuju fokus na pretragu). Za ***filtriranje*** služe padajući meni ***po tipu proizvoda*** (*Ctrl + F*) i ***meni Atributi*** (*Ctrl + L*), uključujući opcije *Sniženo*, *Istaknuto* i *Dostupno*.

#### Dodavanje novih proizvoda

Dugme ***Dodaj*** u gornjem desnom uglu glavnog ekrana otvara prozor sa formularom za kreiranje novog proizvoda (*Ctrl + N*). Forma ima osnovna polja za sve proizvode, a dodatna polja se prikazuju zavisno od tipa (Hrana, Piće ili Pribor).

<p align="center">
  <img src="images/10_menadzer_proizvodi.png" alt="dodaj proizvod" height="250" width="350"/>
</p>

**Zajednička polja**

- *Tip proizvoda* – padajući meni sa obaveznim izborom: *Hrana*, *Piće* ili *Pribor*,
- *Naziv* – tekstualno polje uz provjeru minimalnog i maksimalnog broja karaktera,
- *Opis* – prošireno tekstualno polje,
- *Cijena* – numeričko polje koje mora biti popunjeno i ne smije biti negativno,
- *Slika proizvoda* – dugme za odabir fotografije; nakon izbora prikazuje se pregled slike. Podržani formati: *.jpg, .jpeg, .png*.

**Polja za tip Hrana**

- *Vrsta hrane* – padajući meni sa kategorijama (*torte, slatkiši, peciva, pekarski proizvodi*),
- *Težina* – numeričko polje (u gramima),
- *Kalorije* – numeričko polje koje očekuje cijeli broj,
- *Lako kvarljivo* – izborno polje (checkbox) koje označava da je proizvod lako kvarljiv.

**Polja za tip Piće**

- *Zapremina* – numeričko polje (u mililitrima), vrijednost ne može biti negativna,
- *Alkoholno* – izborno polje (checkbox) koje označava da li proizvod sadrži alkohol.

**Polja za tip Pribor**

- *Materijal* – obavezno tekstualno polje (npr. plastika, metal),
- *Dimenzije* – tekstualno polje u formatu „*broj*" ili „*broj × broj*"; brojevi mogu biti cijeli ili decimalni, a razmak je dozvoljen,
- *Višekratno* – izborno polje (checkbox) koje označava mogućnost ponovne upotrebe.

Dugme ***Dodaj*** pokreće provjeru svih vidljivih polja. Ako su podaci ispravni, proizvod se čuva u bazi i prikazuje se poruka o uspjehu. Ako postoje greške, korisnik dobija upozorenje, a neispravna polja su označena. Dugme ***Otkaži*** zatvara formu bez čuvanja.

#### Prikaz detalja proizvoda

<p align="center">
  <img src="images/11_menadzer_proizvodi.png" alt="detalji proizvoda" height="250" width="350"/>
</p>

Prozor sa detaljima prikazuje *naziv, tip, opis, cijenu* i *popust*, *datume kreiranja* i *posljednje izmjene* i *sliku proizvoda*. Oznake (chipovi) ističu status proizvoda: *dostupan, nedostupan* ili *istaknut*.

Specifični atributi zavise od tipa: za hranu (*vrsta hrane, težina, kalorije, kvarljivost*), za piće (*zapremina, alkoholno/bezalkoholno*), za pribor (*materijal, dimenzije, višekratna upotreba*).

#### Uređivanje osnovnih podataka proizvoda

<p align="center">
  <img src="images/12_menadzer_proizvodi.png" alt="uredi podatke proizvoda" height="250" width="350"/>
</p>

Klikom na odgovarajuću ikonu otvara se modalni prozor za izmjenu ***osnovnih podataka***. Menadžer može mijenjati *cijenu*, dodavati ili uklanjati *popust* i označiti proizvod kao *istaknut*. Polja prikazuju postojeće vrijednosti.

Važe ista pravila kao pri dodavanju proizvoda; čuvanje je onemogućeno dok vrijednosti nisu ispravne (npr. cijena i popust moraju biti numerički i ne smiju biti negativni). Izmjene se potvrđuju dugmetom ***Sačuvaj*** ili tasterom *Enter*, a dugme ***Otkaži*** zatvara prozor bez promjena.

#### Uređivanje detalja proizvoda

<p align="center">
  <img src="images/13_menadzer_proizvodi.png" alt="uredi profil proizvoda" height="250" width="350"/>
</p>

Odabirom proizvoda i klikom na odgovarajuću ikonu otvara se ***uređivanje profila proizvoda***. Moguće je mijenjati *naziv, opis, sliku* i specifične atribute zavisno od tipa proizvoda.

Sistem provjerava unos i ne dozvoljava čuvanje dok podaci nisu validni. Izmjene se potvrđuju dugmetom ***Sačuvaj*** ili tasterom *Enter*.

#### Aktiviranje / deaktiviranje proizvoda

Menadžer može privremeno ***sakriti*** ili ponovo ***prikazati*** proizvod u aktivnoj listi bez brisanja podataka. Prije promjene statusa sistem traži potvrdu.

Neaktivni proizvod se ne prikazuje u standardnom pregledu i nije dostupan za dodavanje u prodajne transakcije dok se ponovo ne aktivira. Neke radnje, poput uređivanja cijene, popusta ili istaknutog statusa, onemogućene su dok proizvod nije aktivan.

Deaktiviranje već neaktivnog proizvoda nije dozvoljeno; u tom slučaju prikazuje se dijalog sa upozorenjem.

### Upravljanje zalihama

Klikom na odgovarajuću ikonu pored proizvoda otvara se prozor za ***upravljanje zalihama***, u kojem menadžer prati i ažurira stanje zaliha. Prikazuju se *količine, serije nabavki* i *rok trajanja*, a kritične stavke su automatski istaknute.

Na ekranu su istaknuti *naziv proizvoda* čije se zalihe uređuju i *ukupna količina* trenutno dostupnih stavki. Centralni dio prikazuje sve serije zaliha za izabrani proizvod: *ID serije, količinu, datum dodavanja* i *rok trajanja*.

Dostupne su akcije: ***Sačuvaj*** (potvrda izmjena), ***Odbaci*** (poništavanje izmjena) i ***Obriši*** (uklanjanje selektovane stavke). Kontrola za ***filtriranje*** omogućava prikaz serija prema statusu (*aktivno / neaktivno*).

Desni panel prikazuje ***detalje*** izabrane stavke (*količina, datum isteka, broj dana za upozorenje, datum dodavanja*). Polja se automatski validiraju:

- *Količina* – obavezno polje; mora biti cio broj veći od nule,
- *Datum isteka* – opciono; ako je unesen, mora biti najmanje 1 dan u budućnosti,
- *Dani upozorenja* – opciono; cio broj koji ne može biti negativan,
- *Datum dodavanja* – datum i vrijeme kada je stavka dodata,
- *Aktivno* – checkbox za aktivaciju ili deaktivaciju stavke.

Ispod panela nalazi se dugme ***Dodaj zalihe*** za kreiranje nove stavke i dugme ***Zatvori*** koje zatvara ekran bez čuvanja promjena.

Ako datum isteka postoji i nalazimo se unutar broja dana za upozorenje, stavka se automatski označava drugom bojom, što menadžeru omogućava da prepozna kritične zalihe.

Prikaz obuhvata i aktivne i neaktivne stavke, bez obzira na to da li im je promijenjen status, da li im je istekao rok ili su potrošene.

### Statistika i izvještaji kod menadžera

#### Proizvodi

Ova sekcija prikazuje ključne poslovne pokazatelje kroz panele i grafikone.

Na ekranu su polja za odabir datuma ***Od*** i ***Do*** i dugme ***Statistika*** za generisanje podataka za željeni period. Polja za datume su opciona: prazno polje znači da nema vremenskog ograničenja za taj kraj perioda; ako je unesen samo datum *Od*, prikazuju se podaci od tog datuma nadalje; ako je unesen samo datum *Do*, prikazuju se podaci zaključno s tim datumom.

Pritiskom na ***Statistika*** sistem prvo provjerava datume. Ako su validni, učitavaju se podaci i ažuriraju svi paneli, grafikoni i lista najprodavanijih proizvoda. U slučaju neispravnog unosa (npr. datum u budućnosti ili pogrešan interval), polja se označavaju greškom i prikazuje se dijalog upozorenja; pretraga se ne izvršava dok se greške ne isprave.

Ispod trake za filtriranje nalaze se paneli:

- ***Porudžbine*** – ukupan broj porudžbina, grupisan po statusima: *Kompletirane, Otkazane* i *Na čekanju*.
- ***Artikli*** – ukupan broj artikala, razvrstan po kategorijama: *Hrana, Piće* i *Pribor*.
- ***Prihod*** – ukupan prihod ostvaren u odabranom periodu.

Grafikoni:
- *Linijski grafikon* – kretanje prodaje artikala i broja porudžbina na sedmičnom nivou,
- *Stubičasti grafikon* – kretanje prihoda u istom periodu.

Na ekranu je i lista ***najprodavanijih proizvoda*** sa sličicama i nazivima, sortirana po broju prodatih artikala.

#### Zalihe

Sekcija *Zalihe* prikazuje stanje proizvoda u skladištu i sve izvršene promjene.

Korisnik bira proizvod, definiše period poljima *Od* i *Do* i pokreće generisanje klikom na dugme ***Izvještaj***. Sistem provjerava unos: datum ne smije biti u budućnosti, krajnji datum mora biti poslije početnog, a izbor proizvoda je obavezan za detaljne izvještaje. Nepravilni datumi ili neizabran proizvod onemogućavaju generisanje izvještaja, a pored polja se prikazuje indikator greške.

**Tabovi:**

- ***Zalihe*** – stavke kojima ističe rok trajanja, nezavisno od izbora proizvoda i perioda. Tabela sadrži *ID zaliha, ID proizvoda, naziv proizvoda, količinu, datum isteka* i *broj dana do upozorenja*,
- ***Transakcije*** – sve promjene stanja zaliha za odabrani proizvod i period: *ID transakcije, datum i vrijeme, tip transakcije* (*prijem, prodaja, korekcija*), *promjena količine, broj porudžbine* i *ID korisnika*,
- ***Izmjene*** – pregled svih promjena u zalihama: *datum, tip izmjene, prethodna i nova vrijednost* i *ID korisnika*,
- ***Sažetak*** – ukupni pregled za odabrani proizvod i period: *količina na skladištu, dodate i prodate količine* i *ukupan broj izmjena*.

Tabele podržavaju sortiranje, a prazni prikazi obavještavaju korisnika da nema podataka za trenutne kriterijume.

<p align="center">
  <img src="images/15_menadzer_izvjestaji.png" alt="izvjestaj" height="250" width="330"/>
  <img src="images/16_menadzer_izvjestaji.png" alt="izvjestaj" height="250" width="330"/>
</p>

---

## Blagajnik

Glavne odgovornosti blagajnika:
- kreiranje i naplata porudžbina,
- praćenje i pregled porudžbina,
- pregled finansijskih i operativnih izvještaja,
- upravljanje ličnim postavkama i profilom.

### Prijava i pristup

Po uspješnoj prijavi prikazuje se ***početni ekran za blagajnika (POS terminal)***. U gornjem dijelu su *profilna slika* i *korisničko ime* prijavljenog blagajnika.

Na lijevoj strani je vertikalni ***navigacioni meni***; svaka opcija ima tastatursku prečicu:

- ***POS (Blagajna)*** – ekran za kreiranje i naplatu porudžbina (*Ctrl + P*),
- ***Porudžbine*** – pregled svih transakcija i detalja o njima (*Ctrl + O*),
- ***Izvještaji*** – finansijski i operativni podaci vezani za rad blagajnika (*Ctrl + R*),
- ***Podešavanja*** – lične postavke naloga, uključujući jezik i temu (*Ctrl + S*),
- ***Profil*** – uređivanje ličnih podataka korisnika: korisničko ime, lozinka, broj telefona, adresa i slika (*Ctrl + M*),
- ***Odjava*** – odjava iz aplikacije (*Escape*).

Glavni dio ekrana prikazuje ***sadržaj izabranog modula***.

### POS ekran

#### Pretraga

U gornjem dijelu ekrana nalaze se alati za filtriranje i pretragu proizvoda: padajući meni za ***izbor tipa proizvoda*** (hrana, piće, pribor; *Ctrl + T*), tekstualno polje za ***pretragu po nazivu ili tipu*** proizvoda (fokus se aktivira tasterom *F3*) i tri ***prekidača za filtriranje***: *Dostupno* (*Ctrl + A*), *Istaknuto* (*Ctrl + F*) i *Sniženo* (*Ctrl + D*). Opcije se mogu kombinovati.

#### Lista proizvoda

U centralnom dijelu ekrana proizvodi su prikazani kao kartice koje se mogu skrolovati. Svaka kartica sadrži *naziv proizvoda, opis* (kao tooltip), *cijenu* i dugme za ***dodavanje u korpu*** (***+***). Pritiskom na „***+***" sistem provjerava da li je proizvod dostupan i da li ga ima na stanju, te sprečava dodavanje istog proizvoda više puta. Ako proizvod nije dostupan za prodaju, nema dovoljno zaliha ili je već u korpi, prikazuje se kratko obavještenje. Ako je dodavanje uspješno, korpa se odmah osvježava.

#### Korpa

U korpi se prikazuju odabrani proizvodi sa *slikom*, *nazivom* i *cijenom*. *Količina* se mijenja *plus/minus* dugmadima, a postoji i dugme za *uklanjanje proizvoda*. Promjene količine odmah se odražavaju na cijenu proizvoda i ukupan iznos korpe. Uklanjanjem proizvoda iz korpe ukupan iznos se automatski osvježava. Pokušaj povećanja količine iznad raspoloživog stanja prikazuje kratkotrajni popup da je dostignut limit zaliha.

#### Ukupan iznos i opcije plaćanja

<p align="center">
  <img src="images/18_blagajnik_pos.png" alt="blagajnik pos" height="250" width="350"/>
</p>

Ispod liste proizvoda prikazuje se ***ukupni iznos korpe*** uz oznaku valute. Blagajniku su dostupne tri opcije plaćanja:

- ***Kasnije*** (*Pay Later*) – plaćanje se odlaže (*Ctrl + L*),
- ***Keš*** (*Pay Cash*) – plaćanje gotovinom (*Ctrl + G*),
- ***Kartica*** (*Pay Card*) – otvara se dijalog za unos broja kartice; nakon potvrde evidentira se plaćanje karticom (*Ctrl + N*).

Bez obzira na odabranu opciju, svaka transakcija kreira porudžbinu i smanjuje količine proizvoda u zalihama; kod opcija Keš i Kartica evidentira se i plaćanje, a kod opcije Kasnije se plaćanje odlaže.

Prije izvršenja operacije potrebno je potvrditi je u dijalogu. Ako je uspješna, korpa se prazni i prikazuje se poruka o uspjehu. Ako je korpa prazna pri pokušaju plaćanja, korisnik dobija obavještenje.

### Porudžbine

<p align="center">
  <img src="images/20_blagajnik_porudzbine.png" alt="blagajnik porudžbine" height="250" width="350"/>
</p>

U centralnom dijelu ekrana je padajući meni za ***filtriranje porudžbina*** po statusu (*Sve, Kompletirane, Otkazane, Na čekanju*); prečica je *Ctrl + T*.

Porudžbine koje je blagajnik realizovao u posljednja 24 časa prikazane su u tabeli sa kolonama *ID, Datum, Ukupna cijena* i *Status*. Tabela podržava sortiranje kolona. Ako nema porudžbina, umjesto tabele prikazuje se poruka „*Nema podataka*".

Na desnoj strani je bočni panel za ***prikaz detalja***: odabirom reda u tabeli prikazuju se stavke porudžbine (*naziv proizvoda, količina, cijena po jedinici* i *ukupna cijena stavke*) i ukupan iznos porudžbine.

Za odabranu porudžbinu dostupne su sljedeće akcije:

- ***Otkaži*** (*Cancel*) – otkazivanje već kreirane porudžbine. Prikazuje se dijalog za potvrdu, nakon čega se vraćaju zalihe artikala za sve stavke. Ako je porudžbina bila na čekanju, status postaje „*Otkazana*"; ako je već bila kompletirana, status postaje „*Refundirana*" i izvršava se povrat sredstava (stanje novca se umanjuje). Već otkazanu porudžbinu nije dozvoljeno ponovo otkazati. Prečica: *Ctrl + L*.
- ***Gotovina*** (*Pay Cash*) – plaćanje gotovinom primjenjuje se na porudžbine u statusu „*Na čekanju*". Otkazanu ili već plaćenu porudžbinu nije moguće platiti; aplikacija sprječava takav pokušaj i prikazuje dijalog. Prečica: *Ctrl + G*.
- ***Kartica*** (*Pay Card*) – plaćanje karticom takođe se primjenjuje na porudžbine u statusu „*Na čekanju*". Otvara se dijalog za unos broja kartice (unos je obavezan i validira se); nakon potvrde evidentira se plaćanje i porudžbina se ažurira. Kao i kod gotovine, otkazanu ili već plaćenu porudžbinu nije moguće platiti. Prečica: *Ctrl + N*.

Ako se pokuša otkazivanje ili plaćanje bez odabrane porudžbine, prikazuje se dijalog o nedozvoljenoj operaciji. Za svaku uspješno izvršenu operaciju prikazuju se informativne poruke.

### Statistika i izvještaji kod blagajnika

Ekran ***Izvještaji*** prikazuje ključne metrike kroz panele i grafikone. Svi prikazi odnose se na prijavljenog blagajnika (prema *korisničkom ID-u*).

- Gornji dio: *ukupan broj porudžbina*, *ukupno prodatih stavki* i *ukupan prihod* ostvaren tokom rada prijavljenog korisnika.
- Donji lijevi dio: dnevne statistike – *broj današnjih porudžbina* po statusima (*Kompletirane, Otkazane, Na čekanju*), *dnevni prihod* i *broj prodatih artikala* po kategorijama (*hrana, piće, pribor*). Ako nema podataka, umjesto grafikona prikazuje se poruka „*Nema porudžbina*".
- *Linijski grafikon* prikazuje *sedmični broj stavki* i *porudžbina* vezanih za rad blagajnika, a *stubičasti grafikon* kretanje *prihoda* u istom periodu.
- Lista *najprodavanijih proizvoda*.

<p align="center">
  <img src="images/21_blagajnik_izvjestaji.png" alt="izvjestaj" height="280" width="380"/>
</p>

---

## Zajedničke funkcionalnosti

Ove funkcije dostupne su i menadžeru i blagajniku: ***postavke jezika*** i ***teme*** te ***uređivanje korisničkog profila***.

### Postavke (jezik i tema)

Korisnik može podesiti temu i jezik interfejsa:

- ***Teme*** – ***svijetla***, ***tamna*** i ***plava***,
- ***Jezici*** – trenutno su podržani ***srpski*** i ***engleski***.

Padajući meniji za izbor jezika i teme imaju ikonice uz svaku opciju, a nazivi su prilagođeni trenutno aktivnom jeziku aplikacije.

Klikom na dugme ***Sačuvaj*** aplikacija upoređuje odabrane postavke sa prethodnim vrijednostima i odmah primjenjuje promjene. Moguće je promijeniti samo temu, samo jezik ili oboje.

<p align="center">
  <img src="images/22_zajednicke_teme.png" alt="teme" height="250" width="330"/>
  <img src="images/29_zajednicke_jezik.png" alt="jezik" height="250" width="330"/>
</p>

Korisnik dobija poruku o rezultatu („*Tema i jezik promijenjeni*", „*Tema promijenjena*", „*Jezik promijenjen*" ili „*Nema promjena*"). Odabrane postavke se čuvaju za datog korisnika, pa su pri svakoj sljedećoj prijavi dostupne prethodno odabrane opcije.

*Primjeri različitih tema:*

<p align="center">
  <img src="images/23_zajednicke_teme.png" alt="teme" height="250" width="330"/>
  <img src="images/26_zajednicke_teme.png" alt="teme" height="250" width="330"/>
</p>
<p align="center">
  <img src="images/24_zajednicke_teme.png" alt="teme" height="250" width="330"/>
  <img src="images/27_zajednicke_teme.png" alt="teme" height="250" width="330"/>
</p>
<p align="center">
  <img src="images/25_zajednicke_teme.png" alt="teme" height="250" width="330"/>
  <img src="images/28_zajednicke_teme.png" alt="teme" height="250" width="330"/>
</p>

*Primjer promjene jezika:*

<p align="center">
  <img src="images/30_zajednicke_jezik.png" alt="jezik" height="250" width="330"/>
  <img src="images/31_zajednicke_jezik.png" alt="jezik" height="250" width="330"/>
</p>

### Profil korisnika

Pri otvaranju stranice ***Profil korisnika*** trenutni podaci su već učitani, pa ih je moguće pregledati i izmijeniti.

<p align="center">
  <img src="images/32_zajednicke_profil.png" alt="profil korisnika" height="250" width="350"/>
</p>

Korisnik može promijeniti:

- ***Korisničko ime*** – obavezno polje; dozvoljena su slova i cifre, postoji ograničenje dužine, a ime mora biti jedinstveno,
- ***Lozinka*** – opciono; ako se unese, važe ista pravila kao za korisničko ime. Lozinka je maskirana,
- ***Broj telefona*** – obavezno polje; mora odgovarati formatu telefonskog broja,
- ***Adresa*** – polje bez dodatnih ograničenja,
- ***Izaberite sliku*** – otvara dijalog za odabir slike; podržani formati su *jpg, jpeg* i *png*.

Dostupna dugmad:

- ***Sačuvaj*** – validira unos i, ako su podaci ispravni, čuva izmjene u profilu (*Ctrl + S*),
- ***Poništi*** – vraća prethodno aktivne vrijednosti i poništava nedavne izmjene (*Ctrl + R*).

### Prilagodljiv raspored

Raspored interfejsa prilagođava se veličini ekrana na desktop i laptop računarima. Na većim ekranima liste proizvoda i navigacione ikone raspoređene su u više kolona, a na manjim se automatski prelazi na manji broj kolona. Na manjim širinama ekrana pojedine slike mogu biti sakrivene radi uštede prostora.

*Primjer prilagođavanja rasporeda:*

<p align="center">
  <img src="images/33_zajednicke_responzivnost.png" alt="responzivnost" height="250" width="330"/>
  <img src="images/34_zajednicke_responzivnost.png" alt="responzivnost" height="250" width="250"/>
</p>
<p align="center">
  <img src="images/35_zajednicke_responzivnost.png" alt="responzivnost" height="250" width="330"/>
  <img src="images/36_zajednicke_responzivnost.png" alt="responzivnost" height="250" width="250"/>
</p>
