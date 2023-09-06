# Spotmarket-Switcher-Repository

## README Tõlge

[taani keel](README.da.md)-[saksa keel](README.de.md)-[hollandi keel](README.nl.md)-[Inglise](README.md)-[hispaania keel](README.es.md)-[Estonian](README.et.md)-[soome keel](README.fi.md)-[prantsuse keel](README.fr.md)-[kreeka keel](README.el.md)-[itaalia keel](README.it.md)-[norra keel](README.no.md)-[portugali keel](README.pt.md)-[rootsi keel](README.sv.md)

## Tere tulemast Spotmarket-Switcheri hoidlasse!

Mida see tarkvara teeb?
See on Linuxi kestaskript, mis lülitab teie akulaadija ja/või lülitatavad pistikupesad õigel ajal sisse, kui teie tunnipõhised dünaamilised energiahinnad on madalad.
Seejärel saate pistikupesade abil sooja veepaagi palju soodsamalt sisse lülitada või saate akuhoidlat automaatselt laadida öösel, kui võrgus on saadaval odav tuuleenergia.
Oodatavat päikeseenergiat saab arvesse võtta ilmastiku API ja vastavalt reserveeritud aku salvestusruumi kaudu.
Toetatud süsteemid on praegu:

-   Shelly tooted (nt Shelly Plug S või Shelly Plus1PM)
-   AVM Fritz!DECT200 ja 210 lülitatavad pistikupesad
-   [Victron](https://www.victronenergy.com/)Venus OS-i energiasalvestussüsteemid nagu Multiplus II.

Kood on lihtne, nii et seda saab hõlpsasti kohandada muude energiasalvestussüsteemidega, kui saate laadimist juhtida linuxi shelli käskude abil.
Palun vaadake faili controller.sh esimesi ridu, et saaksite näha, mida kasutaja saab seadistada.

## Andmeallikas

Tarkvara kasutab praegu EPEX Spot tunnihindu, mida pakuvad kolm tasuta API-d (Tibber, aWATTar ja Entso-E).
Integreeritud tasuta Entso-E API pakub energiahinna andmeid järgmistest riikidest:
Albaania (AL), Austria (AT), Belgia (BE), Bosnia ja Herz. (BA), Bulgaaria (BG), Horvaatia (HR), Küpros (CY), Tšehhi Vabariik (CZ), Taani (DK), Eesti (EE), Soome (FI), Prantsusmaa (FR), Gruusia (GE), Saksamaa (DE), Kreeka (GR), Ungari (HU), Iirimaa (IE), Itaalia (IT), Kosovo (XK), Läti (LV), Leedu (LT), Luksemburg (LU), Malta (MT), Moldova (MD), Montenegro (ME), Holland (NL), Põhja-Makedoonia (MK), Norra (NO), Poola (PL), Portugal (PT), Rumeenia (RO), Serbia (RS), Slovakkia (SK) , Sloveenia (SI), Hispaania (ES), Rootsi (SE), Šveits (CH), Türgi (TR), Ukraina (UA), Ühendkuningriik (UK) vt.[Läbipaistvus Entso-E platvorm](https://transparency.entsoe.eu/transmission-domain/r2/dayAheadPrices/show).

![grafik](https://user-images.githubusercontent.com/6513794/224442951-c0155a48-f32b-43f4-8014-d86d60c3b311.png)

## Paigaldamine

Spotmarket-Switcheri seadistamine on lihtne protsess. Kui kasutate juba UNIX-põhist masinat (nt macOS, Linux või Windows koos Linuxi alamsüsteemiga), järgige tarkvara installimiseks järgmisi samme.

1.  Laadige installiskript alla GitHubi hoidlast, kasutades[see hüperlink](https://raw.githubusercontent.com/christian1980nrw/Spotmarket-Switcher/main/victron-venus-os-install.sh)või käivitage oma terminalis järgmine käsk:
        wget https://raw.githubusercontent.com/christian1980nrw/Spotmarket-Switcher/main/victron-venus-os-install.sh

2.  Käivitage installiskript koos lisavalikutega, et alamkataloogis kõik kontrollimiseks ette valmistada. Näiteks:
        DESTDIR=/tmp/foo sh victron-venus-os-install.sh
    Kui kasutate operatsioonisüsteemi Victron Venus, peaks DESTDIR olema õige`/`(juurkataloog). Tutvuge installitud failidega`/tmp/foo`.

Pange tähele, et kuigi see tarkvara on praegu Venus OS-i jaoks optimeeritud, saab seda kohandada teistele Linuxi seadmetele, näiteks Raspberry PI-le. Edasine arendus võib parandada ühilduvust teiste süsteemidega.

### Juurdepääs Venus OS-ile

Juhised Venus OS-ile juurdepääsu kohta leiate aadressilt<https://www.victronenergy.com/live/ccgx:root_access>.

### Installi skripti täitmine

-   Kui kasutate operatsioonisüsteemi Victron Venus:
    -   Käivitage`victron-venus-os-install.sh`Spotmarket-Switcheri allalaadimiseks ja installimiseks.
    -   Muutke muutujaid tekstiredaktoriga`/data/etc/Spotmarket-Switcher/controller.sh`.
    -   Seadistage ESS-i laadimisgraafik (vt kaasasolevat ekraanipilti). Näites laeb aku öösel kuni 50%, kui see on aktiveeritud, teisi päevaseid laadimisaegu eiratakse. Kui ei soovi, koosta ajakava kõigi 24 tunni jaoks. Ärge unustage seda pärast loomist deaktiveerida. Veenduge, et süsteemiaeg (nagu on näidatud ekraanipildil) on täpne.![grafik](https://user-images.githubusercontent.com/6513794/206877184-b8bf0752-b5d5-4c1b-af15-800b6499cfc7.png)

-   Kui kasutate teist OS-i:
    -   Kopeeri kestaskript (`controller.sh`) kohandatud asukohta ja kohandage muutujaid vastavalt oma vajadustele.
    -   Selle skripti käivitamiseks iga tunni alguses looge crontab või mõni muu ajastamismeetod.
    -   Crontabi näidis:
          Kasutage juhtskripti käivitamiseks iga tund järgmist crontab-kirjet:
          Avage oma terminal ja sisestage`crontab -e`, seejärel sisestage järgmine rida:
            0 * * * * /path/to/controller.sh

### Toetus ja panus

Kui leiate, et see projekt on väärtuslik, kaaluge sponsoreerimist ja edasise arengu toetamist järgmiste linkide kaudu:

-   [Revolut](https://revolut.me/christqki2)
-   [PayPal](https://paypal.me/christian1980nrw)

Lisaks, kui olete Saksamaal ja olete huvitatud dünaamilisele elektritariifile üleminekust, saate projekti toetada, registreerudes selle kaudu[Tibber (viitelink)](https://invite.tibber.com/ojgfbx2e). Nii sina kui projekt saavad 50 eurot riistvara boonust. Pange tähele, et tunnitariifi jaoks on vaja nutikat arvestit või Pulse-IR-i (<https://tibber.com/de/store/produkt/pulse-ir>) .

Kui vajate maagaasi tariifi või eelistate klassikalist elektritariifi, saate projekti siiski toetada[Octopus Energy (viitelink)](https://share.octopusenergy.de/glass-raven-58).
Saate endale ja ka projektile 50 eurot boonust.
Kaheksajala eeliseks on see, et lepingud on tavaliselt ainult igakuised. Need sobivad ideaalselt näiteks börsihindadel põhineva tariifi peatamiseks.

## Vastutusest loobumine

Palun tutvuge kasutustingimustega aadressil<https://github.com/christian1980nrw/Spotmarket-Switcher/blob/dev/License.md>