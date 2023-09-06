# Spotmarket-Switcher-Repository

## README-Übersetzung

[dänisch](README.da.md)-[Deutsch](README.de.md)-[Niederländisch](README.nl.md)-[Englisch](README.md)-[Spanisch](README.es.md)-[estnisch](README.et.md)-[finnisch](README.fi.md)-[Französisch](README.fr.md)-[griechisch](README.el.md)-[Italienisch](README.it.md)-[norwegisch](README.no.md)-[Portugiesisch](README.pt.md)-[Schwedisch](README.sv.md)

## Willkommen im Spotmarket-Switcher-Repository!

Was macht diese Software?
Dies ist ein Linux-Shell-Skript, das Ihr Batterieladegerät und/oder Ihre schaltbaren Steckdosen zum richtigen Zeitpunkt einschaltet, wenn Ihre stündlichen dynamischen Energiepreise niedrig sind.
Über die Steckdosen können Sie dann deutlich günstiger einen Warmwasserspeicher anschalten oder den Batteriespeicher nachts automatisch aufladen, wenn günstiger Windstrom am Netz verfügbar ist.
Über eine Wetter-API kann der zu erwartende Solarertrag berücksichtigt und Batteriespeicher entsprechend reserviert werden.
Unterstützte Systeme sind derzeit:

-   Shelly products (such as Shelly Plug S or Shelly Plus1PM)
-   AVM Fritz!DECT200 und 210 schaltbare Steckdosen
-   [Victron](https://www.victronenergy.com/)Venus OS Energiespeichersysteme wie Multiplus II.

Der Code ist einfach, sodass er problemlos an andere Energiespeichersysteme angepasst werden kann, wenn Sie in der Lage sind, den Ladevorgang über Linux-Shell-Befehle zu steuern.
Bitte werfen Sie einen Blick auf die ersten Zeilen der Datei controller.sh, damit Sie sehen können, was vom Benutzer konfiguriert werden kann.

## Datenquelle

Die Software nutzt derzeit EPEX Spot-Stundenpreise, die von drei kostenlosen APIs (Tibber, aWATTar und Entso-E) bereitgestellt werden.
Die integrierte kostenlose Entso-E API stellt Energiepreisdaten der folgenden Länder bereit:
Albanien (AL), Österreich (AT), Belgien (BE), Bosnien und Herz. (BA), Bulgarien (BG), Kroatien (HR), Zypern (CY), Tschechische Republik (CZ), Dänemark (DK), Estland (EE), Finnland (FI), Frankreich (FR), Georgien (GE), Deutschland (DE), Griechenland (GR), Ungarn (HU), Irland (IE), Italien (IT), Kosovo (XK), Lettland (LV), Litauen (LT), Luxemburg (LU), Malta (MT), Moldawien (MD), Montenegro (ME), Niederlande (NL), Nordmazedonien (MK), Norwegen (NO), Polen (PL), Portugal (PT), Rumänien (RO), Serbien (RS), Slowakei (SK) , Slowenien (SI), Spanien (ES), Schweden (SE), Schweiz (CH), Türkei (TR), Ukraine (UA), Vereinigtes Königreich (UK) siehe[Transparenz Entso-E-Plattform](https://transparency.entsoe.eu/transmission-domain/r2/dayAheadPrices/show).

![grafik](https://user-images.githubusercontent.com/6513794/224442951-c0155a48-f32b-43f4-8014-d86d60c3b311.png)

## Installation

Das Einrichten des Spotmarket-Switchers ist ein unkomplizierter Vorgang. Wenn Sie bereits einen UNIX-basierten Computer wie macOS, Linux oder Windows mit dem Linux-Subsystem ausführen, befolgen Sie diese Schritte, um die Software zu installieren:

1.  Laden Sie das Installationsskript mithilfe von aus dem GitHub-Repository herunter[dieser Hyperlink](https://raw.githubusercontent.com/christian1980nrw/Spotmarket-Switcher/main/victron-venus-os-install.sh), oder führen Sie den folgenden Befehl in Ihrem Terminal aus:
        wget https://raw.githubusercontent.com/christian1980nrw/Spotmarket-Switcher/main/victron-venus-os-install.sh

2.  Führen Sie das Installationsskript mit zusätzlichen Optionen aus, um alles in einem Unterverzeichnis für Ihre Inspektion vorzubereiten. Zum Beispiel:
        DESTDIR=/tmp/foo sh victron-venus-os-install.sh
    Wenn Sie Victron Venus OS verwenden, sollte das richtige DESTDIR sein`/`(das Stammverzeichnis). Schauen Sie sich gerne die installierten Dateien an`/tmp/foo`.

Bitte beachten Sie, dass diese Software derzeit zwar für das Venus-Betriebssystem optimiert ist, aber auch an andere Linux-Geräte wie einen Raspberry PI angepasst werden kann. Zukünftige Entwicklungen könnten die Kompatibilität mit anderen Systemen verbessern.

### Zugriff auf Venus OS

Anweisungen zum Zugriff auf das Venus-Betriebssystem finden Sie unter<https://www.victronenergy.com/live/ccgx:root_access>.

### Ausführung des Installationsskripts

-   Wenn Sie Victron Venus OS verwenden:
    -   Ausführen`victron-venus-os-install.sh`um den Spotmarket-Switcher herunterzuladen und zu installieren.
    -   Bearbeiten Sie die Variablen mit einem Texteditor in`/data/etc/Spotmarket-Switcher/controller.sh`.
    -   Richten Sie einen ESS-Ladeplan ein (siehe Screenshot). Im Beispiel lädt sich der Akku bei Aktivierung nachts bis zu 50 % auf, andere Ladezeiten am Tag werden ignoriert. Falls nicht gewünscht, erstellen Sie einen Zeitplan für alle 24 Stunden des Tages. Denken Sie daran, es nach der Erstellung zu deaktivieren. Stellen Sie sicher, dass die Systemzeit (wie im Screenshot gezeigt) korrekt ist.![grafik](https://user-images.githubusercontent.com/6513794/206877184-b8bf0752-b5d5-4c1b-af15-800b6499cfc7.png)

-   Wenn Sie ein anderes Betriebssystem verwenden:
    -   Kopieren Sie das Shell-Skript (`controller.sh`) an einen benutzerdefinierten Speicherort und passen Sie die Variablen entsprechend Ihren Anforderungen an.
    -   Erstellen Sie eine Crontab oder eine andere Planungsmethode, um dieses Skript zu Beginn jeder Stunde auszuführen.
    -   Beispiel-Crontab:
          Verwenden Sie den folgenden Crontab-Eintrag, um das Steuerskript stündlich auszuführen:
          Öffnen Sie Ihr Terminal und betreten Sie es`crontab -e`, dann fügen Sie die folgende Zeile ein:
            0 * * * * /path/to/controller.sh

### Unterstützung und Beitrag

Wenn Sie dieses Projekt wertvoll finden, denken Sie bitte darüber nach, die weitere Entwicklung über diese Links zu sponsern und zu unterstützen:

-   [Revolut](https://revolut.me/christqki2)
-   [PayPal](https://paypal.me/christian1980nrw)

Wenn Sie außerdem in Deutschland leben und an einem Wechsel zu einem dynamischen Stromtarif interessiert sind, können Sie das Projekt unterstützen, indem Sie sich hier anmelden[Tibber (Empfehlungslink)](https://invite.tibber.com/ojgfbx2e). Sowohl Sie als auch das Projekt erhalten einen 50-Euro-Bonus für Hardware. Bitte beachten Sie, dass für einen Stundentarif ein Smart Meter oder ein Pulse-IR erforderlich ist (<https://tibber.com/de/store/produkt/pulse-ir>) .

Wenn Sie einen Erdgastarif benötigen oder einen klassischen Stromtarif bevorzugen, können Sie das Projekt trotzdem unterstützen[Octopus Energy (Empfehlungslink)](https://share.octopusenergy.de/glass-raven-58).
Sie erhalten eine Prämie von 50 Euro für sich selbst und auch für das Projekt.
Octopus hat den Vorteil, dass die Verträge meist nur eine monatliche Laufzeit haben. Sie eignen sich beispielsweise ideal, um einen an Börsenkursen orientierten Tarif zu pausieren.

## Haftungsausschluss

Bitte beachten Sie die Nutzungsbedingungen unter<https://github.com/christian1980nrw/Spotmarket-Switcher/blob/dev/License.md>