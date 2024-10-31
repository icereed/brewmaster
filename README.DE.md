# Brewmaster für Klarstein Brauheld Smart

Willkommen zur Brewmaster-App für Klarstein Brauheld Smart! Dieses Docker-Image wurde für Hobbybrauer entwickelt, die ein reibungsloses und angenehmes Brauerlebnis wünschen. Unsere benutzerfreundliche Anwendung, erstellt mit React und Go, ermöglicht es Ihnen, Ihre Brausitzungen mühelos zu verwalten. So starten Sie durch!

## Einführung

Unsere App verbindet sich direkt mit dem Klarstein Brauheld-System über die Tuya IoT-Plattform und ermöglicht eine programmierbare Steuerung Ihres Brauprozesses. Mit nur wenigen Einrichtungsschritten können Sie wie ein Profi brauen!

**Hinweis:** Die Tuya-Plattform ist derzeit nur in Englisch verfügbar. Dies betrifft insbesondere die Benutzeroberfläche und die Dokumentation. Dennoch ist die Nutzung der Plattform auch für nicht-englischsprachige Nutzer möglich.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Docker auf Ihrem Computer installiert ist. Docker ist eine Software, die es Ihnen ermöglicht, Anwendungen in Containern auszuführen, wodurch die Installation und Verwaltung vereinfacht wird.

**Docker installieren:**

1. **Download:** Besuchen Sie die [offizielle Docker-Website](https://docs.docker.com/get-docker/) und laden Sie Docker für Ihr Betriebssystem herunter.
2. **Installation:** Folgen Sie den Installationsanweisungen auf der Webseite.
3. **Starten:** Nach der Installation starten Sie Docker und stellen sicher, dass es ordnungsgemäß läuft.

**Hinweis für Windows- und Mac-Nutzer:** Docker Desktop ist die empfohlene Version und bietet eine benutzerfreundliche Oberfläche.

## Einrichtungsanleitung

### Kopplung des Klarstein Brauheld mit Tuya

Folgen Sie diesen Schritten, um Ihren Klarstein Brauheld mit der Tuya-App zu koppeln:

1. **Tuya-App installieren:**
   - Laden Sie die Tuya-App aus dem [App Store](https://apps.apple.com/de/app/tuya-smart/id1295203464) oder [Google Play Store](https://play.google.com/store/apps/details?id=com.tuya.smart) auf Ihr Smartphone herunter und installieren Sie sie.

2. **Tuya-Konto erstellen:**
   - Öffnen Sie die Tuya-App und registrieren Sie ein neues Konto, falls Sie noch keines haben.

3. **Pairing-Modus aktivieren:**
   - Nehmen Sie Ihren Klarstein Brauheld und halten Sie die Reset-Taste für 5 Sekunden gedrückt, bis das Gerät in den Pairing-Modus wechselt.

4. **Gerät hinzufügen:**
   - In der Tuya-App wählen Sie **"Gerät hinzufügen"** -> **"Andere"** -> **"Andere (Wi-Fi)"**.
   - Folgen Sie den Anweisungen in der App, um Ihr Brauheld-Gerät mit Ihrem WLAN zu verbinden.

5. **App-Konto mit Cloud-Projekt verknüpfen:**
   - Öffnen Sie einen Webbrowser und gehen Sie zur [Tuya IoT Entwicklungsplattform](https://iot.tuya.com/).
   - **Hinweis:** Die Tuya IoT Plattform ist nur in Englisch verfügbar. Es kann hilfreich sein, einen Browser mit automatischer Übersetzungsfunktion zu verwenden oder Unterstützung von jemandem mit Englischkenntnissen zu erhalten.
   - Melden Sie sich mit demselben Konto an, das Sie in der Tuya-App verwendet haben.
   - **Cloud-Projekt erstellen:**
     - Klicken Sie auf **"Cloud"** -> **"Develop"** -> **"Create Cloud Project"**.
     - Wählen Sie **"Smart Home"** als Projekttyp und geben Sie einen Projektnamen ein.
   - **APIs autorisieren:**
     - Aktivieren Sie APIs wie **"IoT Core"**, um die Interaktion mit Ihrem Gerät zu ermöglichen.
   - **Tuya-App-Konto verknüpfen:**
     - Gehen Sie zu den Projekteinstellungen und wählen Sie **"Link Tuya App Account"**.
     - Ein QR-Code wird angezeigt. Öffnen Sie die Tuya-App auf Ihrem Smartphone, gehen Sie zu **"Me" > "Account and Security" > "Link with Tuya IoT Platform Account"** und scannen Sie den QR-Code.
     - Bestätigen Sie die Verknüpfung in der App.

6. **Zugangsdaten abrufen:**
   - **Access ID und Access Key:**
     - Nach der Erstellung des Projekts finden Sie Ihre **Access ID** und **Access Key** im Abschnitt **"Authorization Key"** unter **"Overview"**.
   - **Device ID:**
     - Öffnen Sie die Tuya-App, gehen Sie zu den Geräteeinstellungen, wählen Sie **"Device Information"** und notieren Sie die angezeigte **Device ID**.

## Anwendung starten

Um die Brewmaster-App zu starten, führen Sie folgenden Befehl in Ihrem Terminal aus. Ersetzen Sie dabei `<Ihr Tuya Access ID>`, `<Ihr Tuya Access Key>` und `<Ihr Tuya Device ID>` durch Ihre tatsächlichen Tuya-Zugangsdaten.

```bash
docker run -p 8080:8080 -e TUYA_ACCESS_ID="<Ihr Tuya Access ID>" -e TUYA_ACCESS_KEY="<Ihr Tuya Access Key>" -e TUYA_DEVICE_ID="<Ihr Tuya Device ID>" icereed/brewmaster
```

**Schritt-für-Schritt-Anleitung:**

1. **Terminal öffnen:**
   - Auf Windows: Öffnen Sie die Eingabeaufforderung oder PowerShell.
   - Auf macOS/Linux: Öffnen Sie das Terminal.

2. **Befehl eingeben:**
   - Kopieren Sie den obigen Befehl und fügen Sie Ihre Zugangsdaten ein.

3. **Befehl ausführen:**
   - Drücken Sie **Enter**, um den Befehl auszuführen.
   - Docker wird die Brewmaster-Anwendung starten und sie ist anschließend unter Port 8080 auf Ihrem Computer erreichbar.

## Auf die Anwendung zugreifen

Nachdem der Docker-Container gestartet ist:

1. **Webbrowser öffnen:**
   - Starten Sie Ihren bevorzugten Webbrowser (z.B. Chrome, Firefox, Edge).

2. **Adresse eingeben:**
   - Geben Sie [http://localhost:8080](http://localhost:8080) in die Adresszeile ein und drücken Sie **Enter**.

3. **Brau-Abenteuer beginnen:**
   - Die Brewmaster-Oberfläche wird angezeigt. Folgen Sie den Anweisungen auf dem Bildschirm, um Ihre Brausitzungen zu verwalten und zu starten.

### **Zusätzliche Unterstützung**

**Was ist Docker?**
Docker ist eine Software, die es ermöglicht, Anwendungen in sogenannten Containern zu betreiben. Diese Container sorgen dafür, dass die Anwendung auf jedem Computer gleich funktioniert, unabhängig vom Betriebssystem oder installierten Programmen.

**Hilfe bei der Installation:**
Falls Sie Schwierigkeiten bei der Installation von Docker oder beim Ausführen der Brewmaster-App haben, können Sie die folgenden Ressourcen nutzen:
- **Docker Dokumentation auf Deutsch:** [Docker Docs](https://docs.docker.com/get-started/)
- **Support-Forum:** Besuchen Sie den [Hobbybrauer-Forum](https://hobbybrauer.de/forum/viewtopic.php?p=519277) für weitere Hilfe und Austausch mit anderen Nutzern.

**Tipps:**
- Stellen Sie sicher, dass Ihr Computer mit dem Internet verbunden ist.
- Überprüfen Sie, ob Ihr WLAN stabil ist, um eine reibungslose Verbindung mit dem Brauheld zu gewährleisten.
- Starten Sie Ihren Computer und Docker neu, falls die Anwendung nicht wie erwartet funktioniert.

**Umgang mit der englischen Tuya-Plattform:**
Da die Tuya-Plattform nur in Englisch verfügbar ist, hier einige hilfreiche Tipps:
- **Browser-Übersetzung:** Nutzen Sie die automatische Übersetzungsfunktion Ihres Browsers (z.B. Google Chrome bietet eine automatische Übersetzung von Webseiten an).
- **Übersetzungstools:** Verwenden Sie Übersetzungstools wie [DeepL](https://www.deepl.com/translator) oder [Google Translate](https://translate.google.com/) zur Übersetzung spezifischer Texte.
- **Hilfe von Englischsprachigen:** Bitten Sie Freunde oder Familienmitglieder mit Englischkenntnissen um Unterstützung bei der Einrichtung.

Mit diesen Anleitungen und Ressourcen sollte es auch weniger technisch versierten Nutzern möglich sein, die Brewmaster-App erfolgreich zu nutzen und ihr Hobby weiter zu genießen.

## Viel Spaß beim Brauen!

Haben Sie Fragen? Treten Sie den Diskussionen bei und erhalten Sie Tipps im [originalen Forumsthread](https://hobbybrauer.de/forum/viewtopic.php?p=519277).

**Viel Spaß beim Brauen!**

## Bonus: Screenshot

![Screenshot](./images/screenshot.png)
