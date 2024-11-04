<p align="center" width="100%">
    <img width="33%" src="https://github.com/christian1980nrw/Spotmarket-Switcher/blob/main/SpotmarketSwitcherLogo.png?raw=true"> 
</p>

[czeski](README.cs.md)-[duński](README.da.md)-[niemiecki](README.de.md)-[angielski](README.md)-[hiszpański](README.es.md)-[estoński](README.et.md)-[fiński](README.fi.md)-[francuski](README.fr.md)-[grecki](README.el.md)-[włoski](README.it.md)-[Holenderski](README.nl.md)-[norweski](README.no.md)-[Polski](README.pl.md)-[portugalski](README.pt.md)-[szwedzki](README.sv.md)-[japoński](README.ja.md)

## Witamy w repozytorium Spotmarket-Switcher!

Co robi to oprogramowanie? 
Spotmarket-Switcher to łatwe w użyciu narzędzie programowe, które pomaga zaoszczędzić pieniądze na rachunkach za energię. Jeśli masz inteligentną ładowarkę do akumulatorów lub urządzenia takie jak podgrzewacze wody, które mogą włączać się i wyłączać automatycznie, to narzędzie jest idealne dla Ciebie! Inteligentnie włącza Twoje urządzenia, gdy ceny energii są niskie, co jest szczególnie przydatne, jeśli koszty energii zmieniają się co godzinę.

Ten typowy wynik pokazuje zdolność Spotmarket-Switcher do efektywnej automatyzacji zużycia energii, nie tylko oszczędzając koszty, ale także optymalizując wykorzystanie odnawialnych źródeł energii. To doskonały przykład tego, jak można wykorzystać inteligentną technologię do zarządzania zużyciem energii w bardziej zrównoważony i opłacalny sposób. (niebieski = użycie baterii, czerwony = siatka, żółty = energia słoneczna)

<p align="center" width="100%">
    <img width="50%" src="https://github.com/christian1980nrw/Spotmarket-Switcher/blob/main/Screenshot.jpg?raw=true"> 
</p>

-   Użycie w nocy: W nocy, kiedy ceny energii były najniższe, Spotmarket-Switcher w inteligentny sposób aktywował przełączane gniazdko, aby włączyć pompę ciepła do ciepłej wody (skok zaznaczony na czerwono). Pokazuje to zdolność systemu do identyfikowania i wykorzystywania okresów niskiego zużycia energii do zadań energochłonnych.
-   Efektywność ekonomiczna ładowania akumulatorów: w ramach programu strategicznie podjęto decyzję o nieładowaniu akumulatora w tym czasie. Decyzja ta została podjęta na podstawie analizy ekonomicznej, w której uwzględniono straty podczas ładowania i porównano je ze średnimi lub najwyższymi cenami energii w danym dniu. Takie podejście gwarantuje, że ładowanie baterii będzie miało miejsce tylko wtedy, gdy jest to najbardziej opłacalne.
-   Optymalne wykorzystanie baterii w godzinach szczytu: W tym dniu najdroższe godziny zużycia energii przypadały na poranek i wieczór. W tych okresach Spotmarket-Switcher wykorzystywał zmagazynowaną energię akumulatora (pokazaną na niebiesko), unikając w ten sposób wysokich kosztów energii elektrycznej.
-   Rezerwacja akumulatora na godziny o najwyższych kosztach: Po okresach o najwyższych kosztach system magazynowania energii (ESS) akumulatora został wyłączony. Wieczorem około 20:00 nie było pusto. Działanie to podjęto, aby zarezerwować wystarczającą pojemność baterii na nadchodzące drogie godziny następnego ranka. Pozwala to przewidzieć przyszłe okresy wysokich kosztów i zapewnić dostępność zmagazynowanej energii w celu zminimalizowania kosztów.

Dlaczego warto używać Spotmarket-Switcher?

-   Oszczędzaj pieniądze: Włącza Twoje urządzenia, gdy energia jest tańsza, obniżając rachunki.
-   Oszczędzaj pieniądze: Wykorzystaj zmagazynowaną energię słoneczną po najwyższych cenach.
-   Energooszczędność: Wykorzystując energię, gdy jest jej w nadmiarze (np. w wietrzne noce), przyczyniasz się do tworzenia bardziej ekologicznej planety.
-   Inteligentne użytkowanie: automatycznie ładuj akumulator lub włączaj urządzenia, takie jak podgrzewacze wody, w najlepszym momencie.

Obsługiwane systemy to obecnie:

-   Produkty Shelly (np[Shelly Plug S](https://shellyparts.de/products/shelly-plus-plug-s)Lub[Shelly Plus](https://shellyparts.de/products/shelly-plus-1pm))
-   [AVMFritz!DECT200](https://avm.de/produkte/smart-home/fritzdect-200/)I[210](https://avm.de/produkte/smart-home/fritzdect-210/)przełączalne gniazda
-   [Victron](https://www.victronenergy.com/)Systemy magazynowania energii Venus OS, takie jak[Seria MultiPlus-II](https://www.victronenergy.com/inverters-chargers)(Obsługiwane jest Dbus na localhost i MQTT przez LAN)
-   [inna ładowarka MQTT](http://www.steves-internet-guide.com/mosquitto_pub-sub-clients/)(ładowarki sterowane za pomocą poleceń Mosquitto MQTT)

Pierwsze kroki:

-   Pobierz i zainstaluj: Proces instalacji jest prosty. Pobierz skrypt, dostosuj kilka ustawień i gotowe.
-   Zaplanuj i zrelaksuj się: skonfiguruj raz, a będzie działać automatycznie. Żadnych codziennych kłopotów!

Zainteresowany?

-   Zapoznaj się z naszymi szczegółowymi instrukcjami dotyczącymi różnych systemów, takich jak konfiguracje Victron Venus OS, Windows lub Linux. Upewniliśmy się, że kroki są łatwe do wykonania.
-   Dołącz do nas, aby zużycie energii było mądrzejsze i bardziej opłacalne! W przypadku jakichkolwiek pytań, sugestii lub opinii prosimy o kontakt.

Kod jest prosty, dzięki czemu można go łatwo dostosować do innych systemów magazynowania energii, jeśli potrafisz kontrolować ładowanie za pomocą poleceń powłoki Linux.
Spójrz na plik Controller.sh i wyszukaj Charger_command_turnon, aby zobaczyć, jak łatwo można go dostosować.
Utwórz widelec Github i udostępnij swoją personalizację, aby inni użytkownicy mogli z niej skorzystać.

## Źródło danych

Oprogramowanie obecnie wykorzystuje ceny godzinowe EPEX Spot dostarczane przez trzy bezpłatne interfejsy API (Tibber, aWATTar i Entso-E).
Zintegrowany bezpłatny interfejs API Entso-E dostarcza dane o cenach energii w następujących krajach:
Albania (AL), Austria (AT), Belgia (BE), Bośnia i Herz. (BA), Bułgaria (BG), Chorwacja (HR), Cypr (CY), Czechy (CZ), Dania (DK), Estonia (EE), Finlandia (FI), Francja (FR), Gruzja (GE), Niemcy (DE), Grecja (GR), Węgry (HU), Irlandia (IE), Włochy (IT), Kosowo (XK), Łotwa (LV), Litwa (LT), Luksemburg (LU), Malta (MT), Mołdawia (MD), Czarnogóra (ME), Holandia (NL), Macedonia Północna (MK), Norwegia (NO), Polska (PL), Portugalia (PT), Rumunia (RO), Serbia (RS), Słowacja (SK) , Słowenia (SI), Hiszpania (ES), Szwecja (SE), Szwajcaria (CH), Turcja (TR), Ukraina (UA), Wielka Brytania (UK) patrz[Przejrzystość platformy Entso-E](https://transparency.entsoe.eu/transmission-domain/r2/dayAheadPrices/show).

![Screenshot 2023-12-15 221401](https://github.com/christian1980nrw/Spotmarket-Switcher/assets/6513794/25992602-b0a2-48ff-bd4c-64a6f8182297)Bardziej szczegółowy dziennik można wyświetlić za pomocą następującego polecenia w powłoce:

     cd /data/etc/Spotmarket-Switcher
     DEBUG=1 bash ./controller.sh

## Instalacja

Konfiguracja Spotmarket-Switcher jest prostym procesem. Jeśli używasz już komputera z systemem UNIX, na przykład macOS, Linux lub Windows z podsystemem Linux, wykonaj następujące kroki, aby zainstalować oprogramowanie:

1.  Pobierz skrypt instalacyjny z repozytorium GitHub za pomocą[to hiperłącze](https://raw.githubusercontent.com/christian1980nrw/Spotmarket-Switcher/main/victron-venus-os-install.sh)lub wykonaj następujące polecenie w terminalu:
        wget https://raw.githubusercontent.com/christian1980nrw/Spotmarket-Switcher/main/victron-venus-os-install.sh

2.  Uruchom skrypt instalacyjny z dodatkowymi opcjami, aby przygotować wszystko w podkatalogu do kontroli. Na przykład:
        DESTDIR=/tmp/foo sh victron-venus-os-install.sh
    Jeśli używasz systemu operacyjnego Victron Venus, powinien to być prawidłowy DESTDIR`/`(katalog główny). Zachęcamy do eksploracji zainstalowanych plików w`/tmp/foo`.
    Na Cerbo GX system plików jest montowany tylko do odczytu. Widzieć<https://www.victronenergy.com/live/ccgx:root_access>. Aby umożliwić zapis w systemie plików, przed uruchomieniem skryptu instalacyjnego należy wykonać następującą komendę:
        /opt/victronenergy/swupdate-scripts/resize2fs.sh

Należy pamiętać, że chociaż to oprogramowanie jest obecnie zoptymalizowane pod kątem systemu operacyjnego Venus, można je dostosować do innych wersji Linuksa, takich jak Debian/Ubuntu na Raspberry Pi lub innej małej płycie. Z pewnością jest to główny kandydat[OtwórzWRT](https://www.openwrt.org). Korzystanie z komputera stacjonarnego jest w porządku do celów testowych, ale w przypadku pracy 24 godziny na dobę, 7 dni w tygodniu, jego większe zużycie energii może budzić obawy.

### Dostęp do systemu operacyjnego Venus

Instrukcje dotyczące dostępu do systemu operacyjnego Venus znajdują się w sekcji<https://www.victronenergy.com/live/ccgx:root_access>.

### Wykonanie skryptu instalacyjnego

-   Jeśli używasz systemu operacyjnego Victron Venus:
    -   Następnie edytuj zmienne za pomocą edytora tekstu`/data/etc/Spotmarket-Switcher/config.txt`.
    -   Skonfiguruj harmonogram opłat ESS (patrz dostarczony zrzut ekranu). W przykładzie akumulator ładuje się w nocy do 50%, jeśli jest aktywowany, inne pory ładowania w ciągu dnia są ignorowane. Jeśli nie jest to pożądane, utwórz harmonogram na wszystkie 24 godziny w ciągu dnia. Pamiętaj, aby dezaktywować go po utworzeniu. Sprawdź, czy czas systemowy (jak pokazano w prawym górnym rogu ekranu) jest dokładny.![grafik](https://user-images.githubusercontent.com/6513794/206877184-b8bf0752-b5d5-4c1b-af15-800b6499cfc7.png)

Zrzut ekranu przedstawia konfigurację automatycznego ładowania w godzinach zdefiniowanych przez użytkownika. Domyślnie dezaktywowana, może zostać tymczasowo aktywowana przez skrypt.

-   Instrukcje instalacji Spotmarket-Switcher w systemie Windows 10 lub 11 w celu przeprowadzenia testów bez urządzeń Victron (tylko gniazda przełączalne).

    -   początek`cmd.exe`jako Administrator
    -   Wchodzić`wsl --install -d Debian`
    -   Wprowadź nową nazwę użytkownika, np`admin`
    -   Wprowadź nowe hasło
    -   Wchodzić`sudo su`i wpisz swoje hasło
    -   Wchodzić`apt-get update && apt-get install wget curl`
    -   Kontynuuj, korzystając z poniższego opisu ręcznego systemu Linux (skrypt instalatora nie jest kompatybilny).
    -   Nie zapomnij, że jeśli zamkniesz powłokę, system Windows zatrzyma system.


-   Jeśli używasz systemu Linux, takiego jak Ubuntu lub Debian:
    -   Skopiuj skrypt powłoki (`controller.sh`) do niestandardowej lokalizacji i dostosuj zmienne do swoich potrzeb.
    -   polecenia są`cd /path/to/save/ && curl -s -O "https://raw.githubusercontent.com/christian1980nrw/Spotmarket-Switcher/main/scripts/{controller.sh,sample.config.txt,license.txt}" && chmod +x ./controller.sh && mv sample.config.txt config.txt`i do edycji ustawień użyj`vi /path/to/save/config.txt`
    -   Utwórz plik crontab lub inną metodę planowania, aby uruchamiać ten skrypt na początku każdej godziny.
    -   Przykładowy Crontab:
          Użyj następującego wpisu crontab, aby wykonać skrypt sterujący co godzinę:
          Otwórz terminal i wejdź`crontab -e`, a następnie wstaw następujący wiersz:`0 * * * * /path/to/controller.sh`

### Wsparcie i wkład :+1:

Jeśli uznasz ten projekt za wartościowy, rozważ sponsorowanie i wspieranie dalszego rozwoju za pośrednictwem tych linków:

-   [Revolut](https://revolut.me/christqki2)
-   [PayPal](https://paypal.me/christian1980nrw)

Jeśli jesteś z Niemiec i jesteś zainteresowany przejściem na dynamiczną taryfę za energię elektryczną, możesz wesprzeć projekt, rejestrując się za pomocą tego[Tibber (link polecający)](https://invite.tibber.com/ojgfbx2e)lub wpisując kod`ojgfbx2e`w Twojej aplikacji. Otrzymacie Państwo i projekt**Bonus 50 euro za sprzęt**. Należy pamiętać, że w przypadku taryfy godzinowej wymagany jest inteligentny licznik lub Pulse-IR (<https://tibber.com/de/store/produkt/pulse-ir>) .
Jeśli potrzebujesz taryfy na gaz ziemny lub wolisz klasyczną taryfę na energię elektryczną, nadal możesz wesprzeć projekt[Octopus Energy (link polecający)](https://share.octopusenergy.de/glass-raven-58).
Otrzymujesz bonus (oferta jest zróżnicowana**od 50 do 120 euro**) dla siebie i dla projektu.
Octopus ma tę zaletę, że niektóre oferty nie zawierają minimalnego okresu obowiązywania umowy. Idealnie nadają się np. do wstrzymania taryfy opartej na cenach giełdowych.

Jeśli jesteś z Austrii, możesz nas wesprzeć za pomocą[aWATTar Austria (link polecający)](https://www.awattar.at/services/offers/promotecustomers). Proszę skorzystać`3KEHMQN2F`jako kod.

## Zastrzeżenie

Prosimy o zapoznanie się z warunkami korzystania pod adresem<https://github.com/christian1980nrw/Spotmarket-Switcher/blob/main/License.md>
