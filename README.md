# Projekt-Dokumentation

**Projektantrag zu LA_ILA3_0110**

**Projektteam**

| Name        | Vorname  | Klasse |
|-------------|----------|--------|
| Angelov     | Angel    | Im22d  |
| Marku       | Erik     | Im22d  |
| Jashari     | Denis    | Im22d  |

**Versionshistorie**

| **Datum**   | **Version** | **Zusammenfassung**                                                                 |
|-------------|------------|-------------------------------------------------------------------------------------|
| 08.11.2024 | 0.0.1      | Projekt Kickoff und initialen Projektplan festgelegt.                               |
| 15.11.2024 | 0.1.0      | Grundstruktur der Blackjack-Applikation erstellt und Basis-Gameplay implementiert.  |
| 22.11.2024 | 0.2.0      | "Double Down"- und "Split"-Funktionen implementiert, Highscore-Liste hinzugefügt.   |
| 29.11.2024 | 0.3.0      | Chipsystem erstellt und Datenbank für Highscores integriert.                        |
| 06.12.2024 | 0.4.0      | Code optimiert, interaktives Tutorial und Animationen für Kartenbewegungen ergänzt. |
| 13.12.2024 | 0.5.0      | Fehlerbehandlung erweitert, Doku weitergeführt und Programm kontrolliert.            |
| 20.12.2024 | 1.0.0      |    Doku fertiggestellt und Mahara-Portfolio geschrieben.                                   |


## 1. Informieren

### 1.1 Projektbeschreibung

Wir entwickeln eine **Blackjack-Applikation**, die es Spielern ermöglicht, das klassische Kartenspiel digital zu erleben. Die Anwendung umfasst alle wichtigen Spielfunktionen, von der Kartenausgabe bis zur Gewinnermittlung. Das Projekt wird in **C# WPF** umgesetzt und nutzt eine saubere, modular strukturierte Codebasis zur effizienten Handhabung der Spielmechanik und Benutzeroberfläche.

**Grundstruktur:**  
Projekt erstellen, WPF-Basislayout und Grundklassen definieren (Spieler, Dealer, Deck).

**Deck und Karten-Logik:**  
Karten mischen und an Spieler/Dealer ausgeben.

**Spielmechanik:**  
Spielablauf programmieren (Karten ziehen, halten) und Gewinnbedingungen implementieren.

**Benutzeroberfläche:**  
Kartendarstellung, Punktanzeige und Buttons für **Hit**, **Stand**, Neustart.

**Spielstand und Regeln:**  
Gewinn-/Verlustlogik und Limits integrieren.

**Fehlerbehandlung:**  
Ungültige Aktionen (z.B. leerer Kartenstapel) abfangen und testen.

**Zusätzliche Features (optional):** 
Chipsystem, Animationen und Soundeffekte.

### 1.2 User Stories

# User Stories

| US-№ | Verbindlichkeit | Beschreibung                                                                                                       |
|------|-----------------|---------------------------------------------------------------------------------------------------------------------|
| 1    | muss            | Als Spieler möchte ich mich anmelden können, um persönliche Statistiken und Highscores zu sichern und abzurufen.    |
| 2    | kann            | Als neuer Spieler möchte ich ein interaktives Tutorial nutzen, um das Spiel einfach zu erlernen.                  |
| 3    | kann            | Als Spieler möchte ich virtuelle Chips setzen, um Wetteinsätze zu platzieren.                                     |
| 4    | muss            | Als Spieler möchte ich Karten ziehen können.                                             |
| 5    | muss            | Als Spieler möchte ich, dass ungültige Aktionen abgefangen werden, um Fehler zu vermeiden.                          |
| 6    | muss            | Als Spieler möchte ich jederzeit meinen Punktestand sehen, um fundierte Spielentscheidungen zu treffen.             |
| 7    | muss            | Als erfahrener Spieler möchte ich „Stand“, „Double Down“ und „Split“ nutzen können.                                 |
| 8    | muss            | Als Spieler möchte ich nach jeder Runde wissen, ob ich gewonnen oder verloren habe, um den Spielausgang zu verstehen. |
| 9    | muss            | Als Spieler möchte ich jederzeit ein neues Spiel starten oder das aktuelle abbrechen können, um flexibel zu bleiben. |
| 10   | kann            | Als Spieler möchte ich meine In-Game-Währung verwalten (Ein-/Auszahlungen), um ein authentisches Casino-Feeling zu erhalten. |
| 11   | kann            | Als Spieler möchte ich eine Highscore-Liste sehen, um meine Leistung mit anderen Spielern zu vergleichen.          |
| 12   | muss            | Als Spieler möchte ich Einstellungen (z. B. Limits, Spieleranzahl) vornehmen können, um das Spiel anzupassen.       |
| 13   | kann            | Als Spieler möchte ich animierte Kartenbewegungen und visuelle Effekte sehen, um ein ansprechendes Spielerlebnis zu genießen. |
| 14   | muss            | Als Entwickler möchte ich eine Datenbankanbindung, um Spielerprofile, Highscores und Statistiken langfristig zu speichern. |


---

### 1.3 Testfälle

| **TC-№** | **Ausgangslage**           | **Eingabe**                                   | **Erwartete Ausgabe**                                        | **Zugehörige US** |
|----------|----------------------------|-----------------------------------------------|---------------------------------------------------------------|-------------------|
| 1.1      | Anmeldeseite offen         | Benutzername und Passwort eingeben            | Benutzer wird erfolgreich angemeldet                          | US-1              |
| 2.1      | Spielstart                 | Tutorial starten                              | Tutorial führt Schritt-für-Schritt durch das Spiel            | US-2              |
| 3.1      | Chipsystem aktiviert       | Spieler setzt Chips                           | Chips werden korrekt vom Guthaben abgezogen (Wetteinsatz)     | US-3              |
| 4.1      | Spielstart                 | Spieler zieht eine Karte                      | Eine Karte wird dem Spieler hinzugefügt                       | US-4              |
| 5.1      | Kartenstapel leer          | Karte ziehen                                  | Fehler wird abgefangen, Meldung erscheint                     | US-5              |
| 6.1      | Spieler hat Karten         | Punktestand berechnen                         | Punktestand wird korrekt angezeigt                            | US-6              |
| 7.1      | Spieler hat Karten         | Aktion „Double Down“ auswählen                | Einsatz wird verdoppelt und eine Karte gezogen                | US-7              |
| 8.1      | Spielende                  | Gewinn-/Verlustlogik prüfen                   | Spieler erhält Ergebnis „Gewonnen“ oder „Verloren“            | US-8              |
| 9.1      | Spielende                  | Spiel neu starten                             | Ein neues Spiel beginnt, Karten werden neu gemischt           | US-9              |
| 10.1     | In-Game-Währung aktiviert  | Chips ein- oder auszahlen                     | Transaktion wird korrekt ausgeführt, Guthaben wird aktualisiert | US-10             |
| 11.1     | Spielende                  | Highscore-Liste anzeigen                      | Highscore-Liste wird korrekt dargestellt                      | US-11             |
| 12.1     | Einstellungsseite offen    | Limits und Spieleranzahl bearbeiten           | Änderungen werden erfolgreich übernommen                      | US-12             |
| 13.1     | Animation aktiviert        | Karte ziehen                                  | Animation für Kartenbewegungen wird angezeigt                 | US-13             |
| 14.1     | Datenbankanbindung aktiv   | Spiel beenden / Highscore speichern           | Spielerprofil, Highscores und Statistiken werden persistiert   | US-14             |






### 1.4 Diagramme
# Planen

| AP-№  | Frist       | Zuständig | Beschreibung                                                             | Zugehörige US | Geplante Zeit |
|-------|-------------|-----------|--------------------------------------------------------------------------|---------------|---------------|
| 1.A   | 15.11.2024  | Marku     | Anmeldefunktion einbauen                                                 | US-1          | 150 min       |
| 2.A   | 06.11.2024  | Marku     | Interaktives Tutorial erstellen                                          | US-2          | 160 min       |
| 3.A   | 29.11.2024  | Angelov   | Chipsystem für virtuelle Einsätze entwickeln                             | US-3          | 180 min       |
| 4.A   | 15.11.2024  | Jashari   | Kartenmisch- und Ziehfunktion entwickeln                                 | US-4          | 150 min       |
| 5.A   | 13.12.2024  | Team      | Fehlerbehandlung erweitern (z. B. leeres Kartendeck)                     | US-5          | 120 min       |
| 6.A   | 22.11.2024  |           | Punktestand berechnen und anzeigen                                       | US-6          | 120 min       |
| 7.A   | 22.11.2024  |           | „Double Down“ und „Split“ implementieren                                 | US-7          | 150 min       |
| 8.A   | 29.11.2024  | Jashari   | Gewinn-/Verlustlogik prüfen und ausgeben                                 | US-8          | 180 min       |
| 9.A   | 29.11.2024  |           | Spiel-Neustart-Funktion einbauen                                         | US-9          | 120 min       |
| 10.A  | 20.11.2024  | Jashari   | In-Game-Währung entwickeln (Ein-/Auszahlungen)                           | US-10         | 140 min       |
| 11.A  | 06.12.2024  | Marku     | Highscore-Liste implementieren                                           | US-11         | 130 min       |
| 12.A  | 13.11.2024  | Angelov   | Einstellungsseite für Limits und Spieleranzahl hinzufügen                | US-12         | 150 min       |
| 13.A  | 06.12.2024  | Angelov   | Animationen für Kartenbewegungen hinzufügen                              | US-13         | 150 min       |
| 14.A  | 06.12.2024  | Jashari   | Datenbankanbindung implementieren (Spielerprofile, Highscores, Stats)    | US-14         | 150 min       |
| 15.A  | 20.12.2024  | Team      | Projektdokumentation fertigstellen                                       | -             | 120 min       |
| 16.A  | 20.12.2024  | Team      | Mahara-Portfolio schreiben                                               | -             | 120 min       |
| 17.A  | 20.12.2024  | Team      | Finale Tests und Debugging                                               | -             | 180 min       |
| 18.A  | 20.12.2024  | Team      | Tägliche Team-Sitzungen (5 Min/Tag)                                      | -             | 30 min total  |





## 5. Kontrollieren

### 5.1 Testprotokoll

| TC-№ | Datum       | Resultat | Tester      | Verknüpfte US |
|------|-------------|----------|-------------|---------------|
| 1.1  | 20.12.2024  | OK       | Marku       | US-1          |
| 2.1  | 20.12.2024  | OK       | Angelov     | US-2          |
| 3.1  | 20.12.2024  | OK       | Jashari     | US-3          |
| 4.1  | 20.12.2024  | OK       | Angelov     | US-4          |
| 5.1  | 20.12.2024  | OK       | Team        | US-5          |
| 6.1  | 20.12.2024  | OK       | Marku       | US-6          |
| 7.1  | 20.12.2024  | OK       | Angelov     | US-7          |
| 8.1  | 20.12.2024  | OK       | Jashari     | US-8          |
| 9.1  | 20.12.2024  | OK       | Marku       | US-9          |
| 10.1 | 20.12.2024  | OK       | Team        | US-10         |
| 11.1 | 20.12.2024  | OK       | Angelov     | US-11         |
| 12.1 | 20.12.2024  | OK       | Team        | US-12         |
| 13.1 | 20.12.2024  | OK       | Jashari     | US-13         |
| 14.1 | 20.12.2024  | OK       | Marku       | US-14         |

## 7. Teamsitzungsbericht

| Datum       | Erledigte Arbeitspakete                                                                                                                | Nächste Arbeitspakete                                                                                               | Verzögerungen | Änderungen                                                                           | Pro                                                           | Con                                              |
|------|---------------|---------------------------------------------------------------------------------------------------------------------|---------------|--------------------------------------------------------------------------------------|---------------------------------------------------------------|---------------------------------------------------|
| 08.11.2024  | Das Projekt wurde ausgewählt, aufgeteilt und Informationen wurden eingeholt.| Erste Umsetzungsschritte einleiten, Basis-Gameplay entwickeln | Keine         | Keine    | Klarer Projektplan, klare Rollenverteilung                     | Noch keine Umsetzung erfolgt                      |
| 15.11.2024  | Grundstruktur erstellt, Basis-Gameplay (Karten ziehen, Punkte berechnen)                                            | „Double Down“- & „Split“-Funktionen, UI-Optimierungen, Testen & Debugging, Punktesystem & Highscore-Liste            | Keine         | Keine                                                                                | Solide Basis und erster Spielablauf                              | Noch kein erweitertes Gameplay (Double Down, Split)            |
| 22.11.2024  | „Double Down“- und „Split“-Funktionen, UI-Optimierungen, Testen & Debugging, Punktesystem & Highscore-Liste                            | Chipsystem mit Einsätzen, Integration einer Datenbank für Highscores/Statistiken, Einstellungsseite für Limits/Anzahl | Keine         | Keine                                                                                | Erweiterte Spielmechaniken und stabilere UI                     | Noch kein Einsatzsystem, keine persistente Datenspeicherung     |
| 29.11.2024  | Chipsystem mit virtuellen Einsätzen, Datenbankanbindung (Highscores, Stats), Einstellungsseite für Limits und Spieleranzahl            | Code-Optimierung, Interaktives Tutorial, Animationen für Kartenbewegungen                                             | Keine         | Keine                                                                                | Wetten möglich, persistente Datenspeicherung, konfigurierbares Spiel | Code noch nicht optimiert, kein Tutorial, keine Animationen       |
| 06.12.2024  | Code-Optimierung, Interaktives Tutorial, Animationen für Kartenbewegungen                                                              | Fehlerbehandlung erweitern (ungültige Aktionen), Zeitlimit einbauen, Achievements hinzufügen                         | Keine         | Keine                                                                                | Strukturierter Code, verbessertes Spielerlebnis durch Tutorial & Animationen | Noch kein Zeitlimit, keine Achievements                        |
| 13.12.2024  | Fehlerbehandlung erweitert, Dokumentation fortgeführt, Programmablauf kontrolliert                                                     | Mahara-Portfolios schreiben, Dokumentation fertigstellen, letzte Anpassungen                                         | Keine         | Zeitlimit & Achievements entfallen, Entscheidung der Gruppe                         | Fehlerfreiere Anwendung, bessere Dokumentation                  | Keine neuen Herausforderungen wie Zeitlimit oder Achievements   |
| 20.12.2024  | Mahara-Portfolios fertiggestellt, Dokumentation abgeschlossen, letzte Anpassungen vorgenommen                                           | Produktübergabe                                                                            | Keine         | Keine                                                                                | Vollständiges Paket: Code, Doku, Portfolio                      | Keine weiteren Entwicklungsaufgaben geplant                     |




