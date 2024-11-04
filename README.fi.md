<p align="center" width="100%">
    <img width="33%" src="https://github.com/christian1980nrw/Spotmarket-Switcher/blob/main/SpotmarketSwitcherLogo.png?raw=true"> 
</p>

[Tšekki](README.cs.md)-[tanskalainen](README.da.md)-[saksaksi](README.de.md)-[englanti](README.md)-[espanja](README.es.md)-[virolainen](README.et.md)-[Finnish](README.fi.md)-[ranskalainen](README.fr.md)-[kreikkalainen](README.el.md)-[italialainen](README.it.md)-[hollantilainen](README.nl.md)-[norjalainen](README.no.md)-[Kiillottaa](README.pl.md)-[portugali](README.pt.md)-[ruotsinkielinen](README.sv.md)-[japanilainen](README.ja.md)

## Tervetuloa Spotmarket-Switcher-tietovarastoon!

Mitä tämä ohjelmisto tekee? 
Spotmarket-Switcher on helppokäyttöinen ohjelmistotyökalu, jonka avulla voit säästää rahaa energialaskuissasi. Jos sinulla on älykäs akkulaturi tai laitteita, kuten vedenlämmittimiä, jotka voivat käynnistyä ja sammua automaattisesti, tämä työkalu on täydellinen sinulle! Se käynnistää laitteesi älykkäästi, kun energian hinta on alhainen, mikä on erityisen hyödyllistä, jos energiakustannukset muuttuvat tunnin välein.

Tämä tyypillinen tulos osoittaa Spotmarket-Switcherin kyvyn automatisoida energiankäyttöä tehokkaasti säästäen kustannuksia, mutta myös optimoimalla uusiutuvien energialähteiden käytön. Se on loistava esimerkki siitä, kuinka älykästä teknologiaa voidaan käyttää energiankulutuksen hallintaan kestävämmin ja kustannustehokkaammin. (sininen = akun käyttö, punainen = verkko, keltainen = aurinko)

<p align="center" width="100%">
    <img width="50%" src="https://github.com/christian1980nrw/Spotmarket-Switcher/blob/main/Screenshot.jpg?raw=true"> 
</p>

-   Yökäyttö: Yön aikana, kun energian hinnat olivat alhaisimmillaan, Spotmarket-Switcher aktivoi älykkäästi kytkettävän pistorasian kuumavesilämpöpumpun käynnistämiseksi (piikki merkitty punaisella). Tämä osoittaa järjestelmän kyvyn tunnistaa ja hyödyntää edullisia energiajaksoja energiaintensiivisiin tehtäviin.
-   Taloudellinen tehokkuus akun latauksessa: Ohjelma päätti strategisesti olla lataamatta akun varastointia tänä aikana. Tämä päätös perustui taloudelliseen tarkastukseen, jossa otettiin huomioon laskutushäviöt ja verrattiin niitä päivän keskimääräisiin tai korkeimpiin energiahintoihin. Tämä lähestymistapa varmistaa, että akun lataus tapahtuu vain silloin, kun se on kustannustehokkainta.
-   Optimaalinen akun käyttö ruuhka-aikoina: Tänä päivänä kalleimmat energiatunnit olivat aamulla ja illalla. Tänä aikana Spotmarket-Switcher käytti varastoitua akkuenergiaa (esitetty sinisellä), jolloin vältyttiin korkeilta sähkökustannuksilta.
-   Akun varaus kalliille tunneille: Akun energiavarastojärjestelmä (ESS) sammutettiin kalliiden jaksojen jälkeen. Se ei ollut tyhjä illalla noin klo 20.00. Tällä toimenpiteellä varattiin riittävästi akkukapasiteettia seuraavan aamun tulevia kalliita tunteja varten. Tämä ennakoi tulevia korkeita kausia ja varmistaa, että varastoitua energiaa on saatavilla kustannusten minimoimiseksi.

Miksi käyttää Spotmarket-Switcheria?

-   Säästä rahaa: Se käynnistää laitteesi, kun energia on halvempaa, mikä pienentää laskujasi.
-   Säästä rahaa: Käytä varastoitua aurinkoenergiaa korkeimmalla hinnalla.
-   Energiatehokas: Käyttämällä energiaa, kun sitä on ylijäämäisinä (kuten tuulisina öinä), edistät planeetan vihreämpää.
-   Älykäs käyttö: Lataa akkuvarastosi automaattisesti tai käynnistä laitteita, kuten vedenlämmittimiä, parhaimmillaan.

Tuetut järjestelmät ovat tällä hetkellä:

-   Shelly-tuotteet (esim[Shelly Plug S](https://shellyparts.de/products/shelly-plus-plug-s)tai[Shelly Plus](https://shellyparts.de/products/shelly-plus-1pm))
-   [AVMFritz!DECT200](https://avm.de/produkte/smart-home/fritzdect-200/)ja[210](https://avm.de/produkte/smart-home/fritzdect-210/)kytkettävät pistorasiat
-   [Victron](https://www.victronenergy.com/)Venus OS -energian varastointijärjestelmät, kuten[MultiPlus-II sarja](https://www.victronenergy.com/inverters-chargers)(Dbus at localhost ja MQTT by LAN ovat tuettuja)
-   [toinen MQTT laturi](http://www.steves-internet-guide.com/mosquitto_pub-sub-clients/)(laturit, joita ohjataan hyttysen MQTT-komennoilla)

Aloitus:

-   Lataa ja asenna: Asennusprosessi on yksinkertainen. Lataa skripti, säädä muutamia asetuksia ja olet valmis aloittamaan.
-   Ajoita ja rentoudu: Määritä se kerran, ja se toimii automaattisesti. Ei päivittäistä vaivaa!

Kiinnostunut?

-   Tutustu yksityiskohtaisiin ohjeisiimme eri järjestelmille, kuten Victron Venus OS, Windows- tai Linux-asennuksille. Olemme varmistaneet, että vaiheet ovat helppoja seurata.
-   Tule mukaan tekemään energiankäytöstä älykkäämpää ja kustannustehokkaampaa! Jos sinulla on kysyttävää, ehdotuksia tai palautetta, ota rohkeasti yhteyttä.

Koodi on yksinkertainen, joten se voidaan helposti sovittaa muihin energianvarastointijärjestelmiin, jos pystyt ohjaamaan latausta Linuxin komentotulkkikomennoilla.
Katso tiedosto controller.sh ja hae charger_command_turnon, jotta näet kuinka helppoa se voidaan mukauttaa.
Luo github-haarukka ja jaa mukauksesi, jotta muut käyttäjät voivat hyötyä siitä.

## Tietolähde

Ohjelmisto käyttää tällä hetkellä kolmen ilmaisen API:n (Tibber, aWATTar & Entso-E) tarjoamia EPEX Spot -tuntihintoja.
Integroitu ilmainen Entso-E API tarjoaa energian hintatietoja seuraavista maista:
Albania (AL), Itävalta (AT), Belgia (BE), Bosnia ja Herz. (BA), Bulgaria (BG), Kroatia (HR), Kypros (CY), Tšekki (CZ), Tanska (DK), Viro (EE), Suomi (FI), Ranska (FR), Georgia (GE), Saksa (DE), Kreikka (GR), Unkari (HU), Irlanti (IE), Italia (IT), Kosovo (XK), Latvia (LV), Liettua (LT), Luxemburg (LU), Malta (MT), Moldova (MD), Montenegro (ME), Alankomaat (NL), Pohjois-Makedonia (MK), Norja (NO), Puola (PL), Portugali (PT), Romania (RO), Serbia (RS), Slovakia (SK) , Slovenia (SI), Espanja (ES), Ruotsi (SE), Sveitsi (CH), Turkki (TR), Ukraina (UA), Yhdistynyt kuningaskunta (UK) ks.[Transparency Entso-E -alusta](https://transparency.entsoe.eu/transmission-domain/r2/dayAheadPrices/show).

![Screenshot 2023-12-15 221401](https://github.com/christian1980nrw/Spotmarket-Switcher/assets/6513794/25992602-b0a2-48ff-bd4c-64a6f8182297)Tarkempi loki voidaan nähdä seuraavalla komennolla shellissäsi:

     cd /data/etc/Spotmarket-Switcher
     DEBUG=1 bash ./controller.sh

## Asennus

Spotmarket-Switcherin määrittäminen on suoraviivainen prosessi. Jos käytät jo UNIX-pohjaista konetta, kuten macOS, Linux tai Windows, jossa on Linux-alijärjestelmä, asenna ohjelmisto seuraavasti:

1.  Lataa asennusskripti GitHub-arkistosta käyttämällä[tämä hyperlinkki](https://raw.githubusercontent.com/christian1980nrw/Spotmarket-Switcher/main/victron-venus-os-install.sh), tai suorita seuraava komento päätteessäsi:
        wget https://raw.githubusercontent.com/christian1980nrw/Spotmarket-Switcher/main/victron-venus-os-install.sh

2.  Suorita asennuskomentosarja lisäasetuksineen valmistaaksesi kaiken alihakemistossa tarkastusta varten. Esimerkiksi:
        DESTDIR=/tmp/foo sh victron-venus-os-install.sh
    Jos käytät Victron Venus OS -käyttöjärjestelmää, oikean DESTDIR:n pitäisi olla`/`(juurihakemisto). Voit vapaasti tutkia asennettuja tiedostoja`/tmp/foo`.
    Cerbo GX:ssä tiedostojärjestelmä on asennettu vain luku -tilassa. Katso<https://www.victronenergy.com/live/ccgx:root_access>. Jotta tiedostojärjestelmästä tulee kirjoitettava, sinun on suoritettava seuraava komento ennen asennuskomentosarjan suorittamista:
        /opt/victronenergy/swupdate-scripts/resize2fs.sh

Huomaa, että vaikka tämä ohjelmisto on tällä hetkellä optimoitu Venus-käyttöjärjestelmälle, sitä voidaan mukauttaa muihin Linux-malleihin, kuten Debian/Ubuntuun Raspberry Pi:llä tai muulla pienellä levyllä. Ensisijainen ehdokas on varmasti[OpenWRT](https://www.openwrt.org). Pöytäkoneen käyttö on hyvä testaustarkoituksiin, mutta 24/7 käytössä sen suurempi virrankulutus on huolestuttava.

### Pääsy Venus-käyttöjärjestelmään

Katso ohjeet Venus-käyttöjärjestelmän käyttämiseen osoitteesta<https://www.victronenergy.com/live/ccgx:root_access>.

### Asennuskomentosarjan suorittaminen

-   Jos käytät Victron Venus OS:ää:
    -   Muokkaa sitten muuttujia tekstieditorilla`/data/etc/Spotmarket-Switcher/config.txt`.
    -   Aseta ESS-latausaikataulu (katso mukana tulevaa kuvakaappausta). Esimerkissä akku latautuu yöllä jopa 50 %, jos se on aktivoitu, muut vuorokauden latausajat jätetään huomiotta. Jos et halua, luo aikataulu kaikille vuorokauden 24 tunnille. Muista poistaa se käytöstä luomisen jälkeen. Varmista, että järjestelmän aika (kuten näytön oikeassa yläkulmassa näkyy) on oikea.![grafik](https://user-images.githubusercontent.com/6513794/206877184-b8bf0752-b5d5-4c1b-af15-800b6499cfc7.png)

Kuvakaappaus näyttää automaattisen latauksen kokoonpanon käyttäjän määrittäminä aikoina. Oletusarvoisesti poistettu käytöstä, komentosarja voi aktivoida sen tilapäisesti.

-   Ohjeet Spotmarket-Switcherin asentamiseen Windows 10- tai 11-järjestelmään testausta varten ilman Victron-laitteita (vain kytkettävät pistorasiat).

    -   käynnistää`cmd.exe`järjestelmänvalvojana
    -   Enter`wsl --install -d Debian`
    -   Kirjoita uusi käyttäjätunnus kuten`admin`
    -   Anna uusi salasana
    -   Enter`sudo su`ja kirjoita salasanasi
    -   Enter`apt-get update && apt-get install wget curl`
    -   Jatka alla olevalla manuaalisella Linux-kuvauksella (asennusohjelma ei ole yhteensopiva).
    -   Muista, että jos suljet kuoren, Windows pysäyttää järjestelmän.


-   Jos käytät Linux-järjestelmää, kuten Ubuntua tai Debiania:
    -   Kopioi komentotulkin komentosarja (`controller.sh`) mukautettuun paikkaan ja säädä muuttujia tarpeidesi mukaan.
    -   komennot ovat`cd /path/to/save/ && curl -s -O "https://raw.githubusercontent.com/christian1980nrw/Spotmarket-Switcher/main/scripts/{controller.sh,sample.config.txt,license.txt}" && chmod +x ./controller.sh && mv sample.config.txt config.txt`ja muokataksesi asetuksiasi käytä`vi /path/to/save/config.txt`
    -   Luo crontab tai muu ajoitusmenetelmä suorittaaksesi tämän skriptin jokaisen tunnin alussa.
    -   Esimerkki Crontab:
          Käytä seuraavaa crontab-merkintää suorittaaksesi ohjauskomentosarjan tunnin välein:
          Avaa terminaali ja syötä sisään`crontab -e`, lisää sitten seuraava rivi:`0 * * * * /path/to/controller.sh`

### Tuki ja panos :+1:

Jos pidät tätä projektia arvokkaana, harkitse sponsorointia ja jatkokehityksen tukemista näiden linkkien kautta:

-   [Revolut](https://revolut.me/christqki2)
-   [PayPal](https://paypal.me/christian1980nrw)

Jos olet Saksasta ja olet kiinnostunut siirtymään dynaamiseen sähkötariffiin, voit tukea hanketta rekisteröitymällä tällä[Tibber (viittauslinkki)](https://invite.tibber.com/ojgfbx2e)tai syöttämällä koodi`ojgfbx2e`sovelluksessasi. Sekä sinä että projekti saavat**50 euron bonus laitteistolle**. Huomaa, että tuntitariffiin tarvitaan älymittari tai Pulse-IR (<https://tibber.com/de/store/produkt/pulse-ir>) .
Jos tarvitset maakaasutariffia tai haluat klassisen sähkötariffin, voit silti tukea hanketta[Octopus Energy (viittauslinkki)](https://share.octopusenergy.de/glass-raven-58).
Saat bonuksen (tarjous vaihtelee**50-120 euron välillä**) itsellesi ja myös projektille.
Octopusilla on se etu, että osa tarjouksista on ilman vähimmäissopimusta. Ne soveltuvat ihanteellisesti esimerkiksi pörssihintoihin perustuvan tariffin keskeyttämiseen.

Jos olet Itävallasta, voit tukea meitä käyttämällä[aWATtar Itävalta (viittauslinkki)](https://www.awattar.at/services/offers/promotecustomers). Ole hyvä ja käytä`3KEHMQN2F`koodina.

## Vastuuvapauslauseke

Huomioi käyttöehdot osoitteessa<https://github.com/christian1980nrw/Spotmarket-Switcher/blob/main/License.md>
