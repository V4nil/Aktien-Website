# Krypto-Website 
## Projekt-Dokumentation

**Autor**: Raul Gilardoni *(Einzelprojekt)*

---

| Datum     | Version | Zusammenfassung                                                                                          |
|-----------|---------|----------------------------------------------------------------------------------------------------------|
|17.01.2025 | 0.0.1   | Projektidee formuliert, erste Planung                                                                    |
|24.01.2025 | 0.0.2   | Recherche zu CoinGecko-API, Grobentwurf der Backend-Architektur                                          |
|31.01.2025 | 0.0.3   | Erste API-Aufrufe implementiert, grundlegende Datenverarbeitung (Kryptos)                                |
|07.02.2025 | 0.0.4   | Weitere Backend-Struktur, Tests mit Beispiel-Kryptos, erste Frontend-Komponenten                         |
|14.02.2025 | 0.0.5   | Frontend-Oberfläche erweitert, Verbindung mit Backend gefestigt                                          |
|21.02.2025 | 0.0.6   | Sortierfunktion nach Marktkapitalisierung und Volumen (asc/desc), Watchlist vorbereitet                  |
|28.02.2025 | 0.0.7   | Test- und Optimierungsphase, Responsivität geprüft, verschiedene Layoutanpassungen                       |
|07.03.2025 | 1.0.0   | Endversion, Projektdokumentation abgeschlossen                                                           |

---

## 1 Informieren

### 1.1 Ihr Projekt
Ich habe alleine eine **Krypto-Website** entwickelt, die umfangreiche Informationen über **Kryptowährungen** anbietet:

- **Aktuelle Marktdaten** (aktueller Preis, Volumen, Preisänderung in letzter Stunde/24 Stunden/7 Tage)
- **Historische Marktdaten** (Charts über verschiedene Zeiträume)
- **Sortierfunktion** (z. B. nach Marktkapitalisierung oder Volumen, auf- oder absteigend)
- **Watchlist** (bevorzugte Kryptos speichern und zentral abrufen)
- **Responsive Design** (die Website passt sich verschiedenen Bildschirmgrössen an)

### 1.2 User Stories

| US-№ | Verbindlichkeit | Typ         | Beschreibung                                                                                                                                                                       |
|------|-----------------|-------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1    | Muss           | Funktional  | Als Nutzer möchte ich, dass ich Krypto-Coins (Name/Tickersymbol) suchen kann, um schnell bestimmte Werte zu finden.                                                                |
| 2    | Muss           | Funktional  | Als Nutzer möchte ich, dass ich eine Watchlist führen kann, um interessante Kryptos an einem Ort zu speichern.                                                                    |
| 3    | Muss           | Funktional  | Als Nutzer möchte ich, dass ich historische Marktdaten (z. B. Charts) einsehen kann, um den Kursverlauf zu beurteilen.                                                            |
| 4    | Kann           | Qualität    | Als Nutzer möchte ich, dass die Website sich an verschiedene Bildschirmgrössen anpasst, damit ich auch mobil eine gute Benutzererfahrung habe.                                      |
| 5    | Muss           | Funktional  | Als Nutzer möchte ich, dass wichtige Kennzahlen (aktueller Preis, Volumen, Preisänderung, maximale Supply, 24h-Tief und -Hoch) ersichtlich sind.                                   |
| 6    | Muss           | Rand        | Als Nutzer möchte ich, dass ich Kryptowährungen sortieren kann, damit ich nach Marktkapitalisierung oder Volumen (auf-/absteigend) schnell Vergleiche vornehmen kann.             |
| 7    | Muss           | Funktional  | Als Nutzer möchte ich, dass ich neben dem aktuellen Preis auch historische Daten sehen kann, um kurz- und langfristige Trends zu erkennen.                                         |
| 8    | Kann           | Qualität    | Als Nutzer möchte ich, dass die Seite ohne Login nutzbar ist und trotzdem performant läuft, damit ich schnell an Informationen über Kryptos gelange.                              |



### 1.3 Testfälle

| TC-№ | Ausgangslage                                          | Eingabe                                                      | Erwartete Ausgabe                                                                                                   |
|------|-------------------------------------------------------|--------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------|
| 1.1  | Website geladen, Nutzer möchte eine bestimmte Krypto suchen | Eingabe "BTC" in das Suchfeld und Klick auf "Suchen"         | Es erscheint die Bitcoin-Seite mit aktuellem Preis, Volumen, 24h-Änderung etc.                                      |
| 2.1  | Nutzer hat eine Detailseite eines Kryptos geöffnet    | Klick auf "Zur Watchlist hinzufügen"                        | Das Krypto wird für den Nutzer in der Watchlist gespeichert, Meldung "Zur Watchlist hinzugefügt" erscheint          |
| 3.1  | Nutzer betrachtet die Detailseite eines Kryptos       | Klick auf "Historische Daten anzeigen"                       | Chart mit Kursverlauf über den gewählten Zeitraum wird angezeigt                                                    |
| 4.1  | Nutzer öffnet die Website auf dem Smartphone          | Keine spezielle Eingabe                                      | Die UI passt sich an, Navigation bleibt bedienbar, keine Überlappungen oder unlesbare Texte                         |
| 5.1  | Nutzer sieht die Detailseite eines Kryptos            | Keine Eingabe                                               | Aktueller Preis, Volumen, Preisänderungen (1h/24h/7d), maximale Supply, 24h-Tief und -Hoch werden angezeigt         |
| 6.1  | Nutzer öffnet die Kryptoliste                         | Sortierung nach Marktkapitalisierung (absteigend)            | Liste zeigt alle Kryptos sortiert von höchster zur niedrigsten Marktkapitalisierung                                 |
| 7.1  | Nutzer öffnet erneut die Detailseite                  | Keine spezielle Eingabe                                      | Historische Kursdaten mit Zeitfenster (z. B. 7 Tage, 30 Tage) sind einsehbar                                        |
| 8.1  | Nutzer navigiert zwischen verschiedenen Seiten        | Keine spezifische Eingabe                                    | Seiten laden schnell (unter 2 Sekunden), kein Anmeldedialog nötig, keine relevanten Wartezeiten bei Datenabfragen    |

### 1.4 Diagramme



## 2 Planen

| AP-№ | Frist       | Zuständig | Beschreibung                                                                                                                      | geplante Zeit |
|------|------------|-----------|----------------------------------------------------------------------------------------------------------------------------------|---------------|
| 1.A  | 07.03.2025 | Raul      | **Initiales Projekt-Setup**<br>Repository, Grundgerüst (Backend mit Node.js, Frontend mit React, TailwindCSS-Integration)         | 100 min       |
| 2.A  | 07.03.2025 | Raul      | **Recherche und Einbindung CoinGecko-API**<br>API-Key-Handling (falls nötig), erste Testabfragen, Struktur für Daten              | 100 min       |
| 3.A  | 07.03.2025 | Raul      | **Grundlegende API-Endpunkte**<br>Kurse, Volumen, Preisänderungen (1h/24h/7d), Endpunkte für Basisinformationen                   | 90 min        |
| 4.A  | 07.03.2025 | Raul      | **Datenhaltung**<br>Optionales Zwischenspeichern von Kryptodaten, falls die API-Limits erreicht werden                            | 80 min        |
| 5.A  | 07.03.2025 | Raul      | **Erstellung erster React-Komponenten**<br>Startseite, Kryptotabelle, grundlegende Navigation                                    | 80 min        |
| 6.A  | 07.03.2025 | Raul      | **Design/CSS-Grundlage**<br>Layout mit TailwindCSS, Responsivität, Mobile-/Desktop-Ansichten                                     | 80 min        |
| 7.A  | 07.03.2025 | Raul      | **Suchfunktion**<br>Frontend-Eingabefeld, Backend-Anfrage, Aufbereitung der Resultate (Coin-Name, Symbol, etc.)                  | 90 min        |
| 8.A  | 07.03.2025 | Raul      | **Sortierlogik**<br>Sortierung nach Marktkapitalisierung oder Volumen auf- und absteigend                                         | 100 min       |
| 9.A  | 07.03.2025 | Raul      | **Detailseite**<br>Preis, Volumen, Preisänderungen, max. Supply, 24h-Tief/Hoch                                                   | 100 min       |
| 10.A | 07.03.2025 | Raul      | **Chart-Implementierung**<br>Historische Kursdaten über verschiedene Zeiträume (7 Tage, 30 Tage, etc.)                           | 100 min       |
| 11.A | 07.03.2025 | Raul      | **Watchlist-Basis**<br>Nutzer kann Kryptos hinzufügen/entfernen, Daten werden lokal oder im Backend gespeichert                  | 120 min       |
| 12.A | 07.03.2025 | Raul      | **Watchlist-UI**<br>Eigene Seite/Übersicht, auf der gespeicherte Kryptos angezeigt werden                                        | 120 min       |
| 13.A | 07.03.2025 | Raul      | **Fehlermeldungen/Form-Validierungen**<br>Ungültige Eingaben abfangen, sinnvolle Fehleranzeigen                                  | 120 min       |
| 14.A | 07.03.2025 | Raul      | **Erweiterte Fehlerbehandlung**<br>Abfangen von API-Ausfällen, Timeouts, Benutzerhinweise                                       | 100 min       |
| 15.A | 07.03.2025 | Raul      | **Performanceoptimierungen**<br>Caching, Minimierung unnötiger Requests, möglichst schnelles Laden                               | 100 min       |
| 16.A | 07.03.2025 | Raul      | **Erweiterte Kursdaten**<br>Optionale Zeitrahmen, Zoom-Funktion bei Charts                                                      | 140 min       |
| 17.A | 07.03.2025 | Raul      | **Responsives Layout finalisieren**<br>Test auf Smartphone/Tablet, Layout und Styling anpassen                                   | 80 min        |
| 18.A | 07.03.2025 | Raul      | **Sortierfunktion verfeinern**<br>Kombinierte Sortierung (z. B. zuerst Marktkapitalisierung, dann Volumen)                      | 150 min       |
| 19.A | 07.03.2025 | Raul      | **Validierung der Dateneingänge**<br>Logik zur Prüfung von Werten, API-Antworten, z. B. keine negativen Preise                  | 120 min       |
| 20.A | 07.03.2025 | Raul      | **UX-Optimierungen**<br>Animationen, Hover-Effekte, Ladeindikatoren                                                             | 150 min       |
| 21.A | 07.03.2025 | Raul      | **Usability-Tests**<br>Feedback von Testnutzern sammeln, UI-Anpassungen, Layout-Feinschliff                                      | 90 min        |
| 22.A | 07.03.2025 | Raul      | **Sicherheitsmassnahmen**<br>API-Aufrufe gegen Manipulation schützen, grundlegende Error-Handling (kein Login-System notwendig) | 130 min       |
| 23.A | 07.03.2025 | Raul      | **Refactoring**<br>Code-Struktur verbessern, Modularisierung, Dateien aufräumen                                                 | 160 min       |
| 24.A | 07.03.2025 | Raul      | **Kompatibilitätstests**<br>Browser (Chrome, Firefox, Edge), Geräte (Desktop, Tablet, Smartphone), unterschiedliche Auflösungen | 120 min       |
| 25.A | 07.03.2025 | Raul      | **Benutzeranleitung**<br>Screenshots, kurze Erklärung der Hauptfunktionen (Sortierung, Watchlist, Charts)                       | 120 min       |
| 26.A | 07.03.2025 | Raul      | **Dokumentation fertigstellen**<br>Projektverlauf, Lessons Learned, finale Abgabe                                               | 200 min       |

---

## 3 Entscheiden
1. **Technologie**: Node.js/Express als Backend, React als Frontend, TailwindCSS für schnelles Styling, JavaScript und HTML als Basistechnologien.  
2. **API**: Die CoinGecko-API liefert umfangreiche Daten zu Kryptowährungen (Preise, Marktkapitalisierung, Volumen, historische Daten).  
3. **Keine Login-Funktion**: Für diese Version der Website ist keine Registrierung oder Anmeldung notwendig.  
4. **Nur Sortierung**: Filterfunktion wurde nicht implementiert, jedoch können Nutzer Kryptos nach Marktkapitalisierung und Volumen sortieren (ascending/descending).  
5. **Deployment**: Vercel oder ein ähnlicher Hosting-Service für das Frontend, Backend ebenfalls bei einem Cloud-Anbieter.  

---

## 4 Realisieren

| AP-№ | Datum    | Zuständig | geplante Zeit | tatsächliche Zeit |
|------|---------|-----------|---------------|-------------------|
|1.A   | 17.01.   | Raul      | 100 min       | 120 min           |
|2.A   | 24.01.   | Raul      | 100 min       | 110 min           |
|3.A   | 31.01.   | Raul      | 90 min        | 100 min           |
|4.A   | 31.01.   | Raul      | 80 min        | 80 min            |
|5.A   | 07.02.   | Raul      | 80 min        | 90 min            |
|6.A   | 07.02.   | Raul      | 80 min        | 90 min            |
|7.A   | 07.02.   | Raul      | 90 min        | 80 min            |
|8.A   | 07.02.   | Raul      | 100 min       | 110 min           |
|9.A   | 14.02.   | Raul      | 100 min       | 90 min            |
|10.A  | 14.02.   | Raul      | 100 min       | 90 min            |
|11.A  | 14.02.   | Raul      | 120 min       | 120 min           |
|12.A  | 14.02.   | Raul      | 120 min       | 120 min           |
|13.A  | 21.02.   | Raul      | 120 min       | 120 min           |
|14.A  | 21.02.   | Raul      | 100 min       | 120 min           |
|15.A  | 21.02.   | Raul      | 100 min       | 110 min           |
|16.A  | 28.02.   | Raul      | 140 min       | 150 min           |
|17.A  | 28.02.   | Raul      | 80 min        | 120 min           |
|18.A  | 28.02.   | Raul      | 150 min       | 150 min           |
|19.A  | 28.02.   | Raul      | 120 min       | 120 min           |
|20.A  | 28.02.   | Raul      | 150 min       | 150 min           |
|21.A  | 28.02.   | Raul      | 90 min        | 100 min           |
|22.A  | 28.02.   | Raul      | 130 min       | 100 min           |
|23.A  | 28.02.   | Raul      | 160 min       | 180 min           |
|24.A  | 28.02.   | Raul      | 120 min       | 110 min           |
|25.A  | 07.03.   | Raul      | 120 min       | 140 min           |
|26.A  | 07.03.   | Raul      | 200 min       | 210 min           |

---

## 5 Kontrollieren

| TC-№ | Datum      | Resultat      | Tester |
|------|-----------|---------------|--------|
|1.1   | 07.02.2025 | Funktioniert  | Raul   |
|2.1   | 07.02.2025 | Funktioniert  | Raul   |
|3.1   | 14.02.2025 | Funktioniert  | Raul   |
|4.1   | 14.02.2025 | Funktioniert  | Raul   |
|5.1   | 21.02.2025 | Funktioniert  | Raul   |
|6.1   | 21.02.2025 | Funktioniert  | Raul   |
|7.1   | 28.02.2025 | Funktioniert  | Raul   |
|8.1   | 28.02.2025 | Funktioniert  | Raul   |



---

## Fazit
Die **Krypto-Website** bietet eine übersichtliche Plattform, um Informationen zu Kryptowährungen abzurufen. 
Dank der **CoinGecko-API** können aktuelle Marktdaten (Preis, Volumen, Preisveränderungen) und historische Kursverläufe abgerufen werden. Die **Sortierfunktion** nach Marktkapitalisierung oder Volumen funktioniert zuverlässig, obwohl eine Filterfunktion in dieser Version noch nicht umgesetzt wurde. Eine **Watchlist** ermöglicht es, ausgewählte Kryptos zu speichern und sie jederzeit gesammelt einzusehen.

- **Herausforderungen**:
  - Sicherstellen einer **verlässlichen Performance**, da Live-Daten teils in grösseren Mengen abgerufen werden.
  - **Responsive Design** mit TailwindCSS so zu gestalten, dass auch auf Mobilgeräten ein optimales Nutzererlebnis gewährleistet ist.
  
- **Ergebnisse**:
  - Eine **intuitive** Website, bei der kein Login benötigt wird.
  - Eine **Watchlist**, die den aktuellen Status der Krypto-Preise abbildet.
  - **Historische Kursdaten** zur Verfolgung von Trends über verschiedene Zeiträume.
  - **Sortierbare Kryptoliste** (Marktkapitalisierung, Volumen, auf-/absteigend).

Ich konnte wertvolle Erfahrungen in der Webentwicklung sammeln, insbesondere im Umgang mit einer externen Datenquelle (API) und der Umsetzung eines klar strukturierten Frontends mit **React** und **TailwindCSS**. Das gesteckte Ziel, die Website bis zum 07.03.2025 abzuschliessen, wurde erfolgreich erreicht.

*(c) 2025, Raul Gilardoni*  

