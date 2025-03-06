# Aktien-Website 
## Projekt-Dokumentation

**Autor**: Raul Gilardoni *(Einzelprojekt)*

---

| Datum     | Version | Zusammenfassung                                                                                               |
|-----------|---------|---------------------------------------------------------------------------------------------------------------|
|17.01.2025 | 0.0.1   | Projektidee formuliert, erste Planung                                                                         |
|24.01.2025 | 0.0.2   | API-Recherche, Grobentwurf der Backend-Architektur                                                            |
|31.01.2025 | 0.0.3   | Erste API-Aufrufe implementiert, grundlegende Datenverarbeitung                                               |
|07.02.2025 | 0.0.4   | Weitere Backend-Struktur, Tests mit Beispiel-Aktien, erste Frontend-Komponenten                               |
|14.02.2025 | 0.0.5   | Frontend-Oberfläche erweitert, Verbindung mit Backend gefestigt                                               |
|21.02.2025 | 0.0.6   | Such-/Filterfunktionen aufgebaut, Watchlist vorbereitet                                                       |
|28.02.2025 | 0.0.7   | Test- und Optimierungsphase, Sicherheitsaspekte (API-Key-Handling), Responsivität geprüft                     |
|07.03.2025 | 1.0.0   | Endversion, Projektdokumentation abgeschlossen                                                                |

---

## 1 Informieren

### 1.1 Ihr Projekt
Ich erstelle alleine eine **Website**, welche umfangreiche Informationen über **Aktien** anbietet:
- **Aktuelle Kurse** (inkl. Intraday-Daten)
- **Historische Kursverläufe** (Charts über verschiedene Zeiträume)
- **Finanzkennzahlen** (KGV, EPS, Dividenden, Marktkapitalisierung etc.)
- **Nachrichten** zu den jeweiligen Aktien
- **Suche, Filter und Sortierung** (z. B. nach Branchen, Marktkapitalisierung)
- **Watchlist** für favorisierte Titel

Ziel ist es, Nutzerinnen und Nutzern eine rasche und intuitive Möglichkeit zu bieten, sich einen Überblick über gewünschte Wertpapiere zu verschaffen.

### 1.2 User Stories

| US-№ | Verbindlichkeit | Typ         | Beschreibung                                                                                                                                   |
|------|-----------------|-------------|-----------------------------------------------------------------------------------------------------------------------------------------------|
| 1    | Muss           | Funktional  | Als User möchte ich, dass ich nach Aktien (Name/Tickersymbol) suchen kann, um schnell bestimmte Werte zu finden.                             |
| 2    | Muss           | Funktional  | Als User möchte ich, dass ich eine Watchlist führen kann, um interessante Aktien an einem Ort zu verwalten.                                  |
| 3    | Muss           | Funktional  | Als User möchte ich, dass ich historische Daten (Charts) einsehen kann, um den Kursverlauf beurteilen zu können.                            |
| 4    | Kann           | Qualität    | Als User möchte ich, dass die Website sich responsiv an verschiedene Bildschirmgrössen anpasst.                                              |
| 5    | Muss           | Funktional  | Als User möchte ich, dass wichtige Kennzahlen (KGV, EPS) auf der Detailseite sofort ersichtlich sind.                                        |
| 6    | Muss           | Rand        | Als User möchte ich, dass ich via Filter/Sortierung gezielt Aktien auswählen kann (z. B. nach Branche, Marktkapitalisierung).                |
| 7    | Muss           | Funktional  | Als User möchte ich, dass aktuelle Nachrichten zum Unternehmen angezeigt werden, damit ich schnell informiert bin.                           |
| 8    | Kann           | Qualität    | Als User möchte ich, dass die Website zügig lädt und performant arbeitet, damit ich nicht lange auf Daten warten muss.                       |

### 1.3 Testfälle

| TC-№ | Ausgangslage                                           | Eingabe                                                      | Erwartete Ausgabe                                                                                 |
|------|--------------------------------------------------------|--------------------------------------------------------------|---------------------------------------------------------------------------------------------------|
| 1.1  | Website geladen, Nutzer will Aktien suchen             | Suche nach "AAPL"                                           | Anzeige der Apple-Aktie mit Kurs, Kennzahlen, News etc.                                           |
| 2.1  | Nutzer ist eingeloggt, Detailseite einer Aktie offen   | Klick auf "Zur Watchlist hinzufügen"                        | Aktie wird für Nutzer in der Datenbank gespeichert, Meldung "Zur Watchlist hinzugefügt" erscheint |
| 3.1  | Nutzer auf Detailseite einer Aktie                     | Klick auf "Historische Daten anzeigen"                       | Chart zum Kursverlauf wird angezeigt                                                              |
| 4.1  | Nutzer öffnet Website am Smartphone                    | Keine spezielle Eingabe                                     | UI passt sich an, Navigation bleibt bedienbar, keine Überlappungen                                |
| 5.1  | Nutzer sieht Detailseite einer Aktie                   | Keine Eingabe                                               | KGV, EPS usw. werden direkt neben Kurs- und Basisinformationen angezeigt                          |
| 6.1  | Aktien-Übersichtsliste geladen                         | Filter: Branche "Tech", Sortierung: Marktkapitalisierung     | Nur Tech-Aktien, absteigend sortiert nach Marktkapitalisierung                                    |
| 7.1  | Detailseite zur Aktie                                  | Keine Eingabe                                               | Nachrichten zur Aktie werden angezeigt                                                            |
| 8.1  | Nutzer springt zwischen verschiedenen Seiten           | Keine spezifische Eingabe                                   | Seitenwechsel erfolgt rasch (unter 2 Sek.), keine spürbaren Ruckler                                |

### 1.4 Diagramme

*(Schematische Darstellung der Architektur mit Node.js/Express und React)*


---

## 2 Planen

Im Folgenden sind Arbeitspakete (AP) analog zum Casino-Beispiel mit entsprechender Zeitplanung (jeweils bis 07.03.2025) aufgeführt:

| AP-№ | Frist       | Zuständig | Beschreibung                                                                                                                        | geplante Zeit |
|------|------------|-----------|------------------------------------------------------------------------------------------------------------------------------------|---------------|
| 1.A  | 07.03.2025 | Raul      | **Initiales Projekt-Setup**<br>Github-Repo erstellen, Grundgerüst (Backend mit Node.js, Frontend mit React)                        | 100 min       |
| 2.A  | 07.03.2025 | Raul      | **API-Recherche und Einbindung**<br>Börsen-APIs (z. B. Finnhub) prüfen, API-Key-Handling, erste Testabfragen                       | 100 min       |
| 3.A  | 07.03.2025 | Raul      | **Grundlegende API-Endpunkte**<br>Kurse, Kennzahlen, Endpunkte für Basisinformationen                                              | 90 min        |
| 4.A  | 07.03.2025 | Raul      | **Datenbank-Einrichtung**<br>Mögliche Speicherung von Nutzerprofilen, Watchlists, Zwischenspeicherung von Aktiendaten             | 80 min        |
| 5.A  | 07.03.2025 | Raul      | **Erstellung erster React-Komponenten**<br>Startseite, Aktientabelle, Navigation                                                  | 80 min        |
| 6.A  | 07.03.2025 | Raul      | **Design/CSS-Grundlage**<br>Basisfarben, Responsivität, erste Layoutstrukturen                                                    | 80 min        |
| 7.A  | 07.03.2025 | Raul      | **Suchfunktion**<br>Frontend-Suche, Backend-Anfrage, Aufbereitung der Resultate                                                  | 90 min        |
| 8.A  | 07.03.2025 | Raul      | **Filter-/Sortierlogik**<br>Filter nach Branche, Sortierung nach Marktkapitalisierung etc.                                        | 100 min       |
| 9.A  | 07.03.2025 | Raul      | **Detailseite**<br>Kursdetails, Kennzahlen (KGV, EPS), Chart-Bereich                                                             | 100 min       |
| 10.A | 07.03.2025 | Raul      | **Chart-Implementierung**<br>Integration einer Chart-Bibliothek, Darstellung historischer Kursverläufe                           | 100 min       |
| 11.A | 07.03.2025 | Raul      | **Nachrichtenfeed**<br>Anbindung externer News-API (sofern verfügbar) oder Feed, Anzeige in der Detailansicht                    | 120 min       |
| 12.A | 07.03.2025 | Raul      | **Auth-System**<br>Login/Register mit JWT, Session-Handling, Passwortverschlüsselung                                             | 120 min       |
| 13.A | 07.03.2025 | Raul      | **Watchlist-Basis**<br>CRUD-Endpunkte, Nutzer kann Aktien hinzufügen/entfernen                                                   | 120 min       |
| 14.A | 07.03.2025 | Raul      | **Watchlist-UI**<br>Frontend-Seite mit übersichtlicher Darstellung der gespeicherten Aktien                                      | 100 min       |
| 15.A | 07.03.2025 | Raul      | **Fehlermeldungen/Form-Validierungen**<br>Ungültige Eingaben abfangen, aussagekräftige Fehlermeldungen                           | 100 min       |
| 16.A | 07.03.2025 | Raul      | **Erweiterte Fehlerbehandlung**<br>Abfangen von API-Ausfällen, Timeouts, Benutzerhinweise                                        | 120 min       |
| 17.A | 07.03.2025 | Raul      | **Performanceoptimierungen**<br>Caching, Minimierung der Requests, ggf. Paging bei sehr vielen Datensätzen                        | 120 min       |
| 18.A | 07.03.2025 | Raul      | **Erweiterte Kursdaten**<br>Mehr Zeiträume (1 Woche, 1 Monat, 1 Jahr etc.), Zoom-Funktion                                        | 140 min       |
| 19.A | 07.03.2025 | Raul      | **Responsives Layout**<br>Test auf Smartphone/Tablet, Anpassung von Layout/Styling                                               | 80 min        |
| 20.A | 07.03.2025 | Raul      | **Sortierfunktion verfeinern**<br>Kombination von Filter + Sortierung, mehrere Sortierkriterien parallel                          | 150 min       |
| 21.A | 07.03.2025 | Raul      | **Validierung der Dateneingänge**<br>Logik zur Prüfung von Zahlen, Ticker-Symbolen, API-Antworten                                | 120 min       |
| 22.A | 07.03.2025 | Raul      | **Benachrichtigungsfunktion** (optional)<br>Z. B. E-Mail-Alert bei bestimmten Kursänderungen                                     | 150 min       |
| 23.A | 07.03.2025 | Raul      | **UX-Optimierungen**<br>Animationen, Hover-Effekte, Ladeindikatoren                                                              | 90 min        |
| 24.A | 07.03.2025 | Raul      | **Usability-Tests**<br>Feedback von Testnutzern sammeln, UI-Anpassungen, Layoutoptimierungen                                     | 130 min       |
| 25.A | 07.03.2025 | Raul      | **Sicherheitsmassnahmen**<br>Komplexe Passwörter, Captcha (optional), Absicherung sensibler Endpunkte                           | 160 min       |
| 26.A | 07.03.2025 | Raul      | **Refactoring**<br>Aufräumen des Codes, Strukturverbesserungen, Modularisierung                                                 | 120 min       |
| 27.A | 07.03.2025 | Raul      | **SEO-Check**<br>Meta-Tags, Performance-Analyse mit Lighthouse, barrierearme Elemente                                           | 120 min       |
| 28.A | 07.03.2025 | Raul      | **Kompatibilitätstests**<br>Browser (Chrome, Firefox, Edge), Geräte (Desktop, Tablet, Smartphone), unterschiedliche Auflösungen  | 120 min       |
| 29.A | 07.03.2025 | Raul      | **Benutzeranleitung**<br>Screenshots, kurze Erklärung der Hauptfunktionen                                                       | 120 min       |
| 30.A | 07.03.2025 | Raul      | **Dokumentation fertigstellen**<br>Projektverlauf, Lessons Learned, Screenshots, Finale Abgabe                                   | 200 min       |

---

## 3 Entscheiden
1. **Technologie**: Node.js/Express für Backend, React für Frontend, MongoDB als flexible NoSQL-Datenbank.  
2. **API**: Einbindung von externen Börsen-APIs (z. B. Finnhub) mit stündlichen oder täglichen Anfragen.  
3. **Authentifizierung**: JWT-basierte Lösung (einfach, flexibel).  
4. **Trennung**: Frontend und Backend in separaten Repos, um Entwicklungsprozesse zu entkoppeln.  
5. **Deployment**: Vercel (Frontend) und Cloud-Service (Backend), Datenbank als Managed Service (z. B. MongoDB Atlas).

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
|16.A  | 28.02.   | Raul      | 120 min       | 110 min           |
|17.A  | 28.02.   | Raul      | 120 min       | 120 min           |
|18.A  | 28.02.   | Raul      | 140 min       | 150 min           |
|19.A  | 28.02.   | Raul      | 80 min        | 120 min           |
|20.A  | 28.02.   | Raul      | 150 min       | 150 min           |
|21.A  | 28.02.   | Raul      | 120 min       | 120 min           |
|22.A  | 28.02.   | Raul      | 150 min       | 150 min           |
|23.A  | 28.02.   | Raul      | 90 min        | 100 min           |
|24.A  | 28.02.   | Raul      | 130 min       | 100 min           |
|25.A  | 28.02.   | Raul      | 160 min       | 180 min           |
|26.A  | 28.02.   | Raul      | 120 min       | 120 min           |
|27.A  | 28.02.   | Raul      | 120 min       | 130 min           |
|28.A  | 28.02.   | Raul      | 120 min       | 110 min           |
|29.A  | 07.03.   | Raul      | 120 min       | 140 min           |
|30.A  | 07.03.   | Raul      | 200 min       | 210 min           |



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
Das Projekt **Aktien-Website** war eine vielseitige Erfahrung, die sämtliche Phasen von der Idee bis zur Fertigstellung umfasste. Jeden Freitag konnte ich gezielt an Teilaufgaben arbeiten und schrittweise Fortschritte erzielen, sodass der geplante Endtermin **07.03.2025** eingehalten wurde.

- **Herausforderungen**:  
  - Integration externer Börsen-APIs (teils begrenztes Kontingent, unterschiedliches Datenformat).  
  - **Performance**-Optimierungen bei vielen Daten (Caching, Minimierung redundanter Requests).  
  - **Responsives Design**, um auf Desktop und mobilen Endgeräten reibungslos zu funktionieren.

- **Ergebnisse**:  
  - Eine **intuitive**, optisch ansprechende Plattform, welche Aktienkurse, Kennzahlen, Nachrichten und Watchlist-Funktionen vereint.  
  - Eine solide **Backend-Struktur** (Node.js/Express) mit sauber dokumentierten API-Endpunkten.  
  - Ausgedehnte **Testphase**, bei der alle wichtigen User Stories und Testfälle erfolgreich validiert wurden.

Durch diese Arbeit habe ich in kurzer Zeit sehr viel über **Webentwicklung** (Frontend/Backend), **API-Nutzung** und **Projektorganisation** im Alleingang gelernt. Diese Kompetenzen werde ich in künftigen Projekten weiter ausbauen.

*(c) 2025, Raul Gilardoni*  
