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

| US-№ | Verbindlichkeit | Beschreibung                                                                                                        |
|------|-----------------|---------------------------------------------------------------------------------------------------------------------|
| 1   | muss             | Als Spieler möchte ich mich registrieren können, um persönliche Statistiken und Highscores zu sichern und abzurufen.|
| 2    | muss            | Als Spieler möchte ich mich anmelden können.                                                                        |
| 3    | kann            | Als neuer Spieler möchte ich ein interaktives Tutorial nutzen, um das Spiel einfach zu erlernen.                    |
| 4    | kann            | Als Spieler möchte ich virtuelle Chips setzen, um Wetteinsätze zu platzieren.                                       |
| 5    | muss            | Als Spieler möchte ich Karten ziehen können.                                                                        |
| 6    | muss            | Als Spieler möchte ich, dass ungültige Aktionen abgefangen werden, um Fehler zu vermeiden.                          |
| 7    | muss            | Als Spieler möchte ich jederzeit meinen Punktestand der Karten sehen, um fundierte Spielentscheidungen zu treffen.             |
| 8    | muss            | Als erfahrener Spieler möchte ich „Stand“,„Double“, „Hit“ und „Split“ nutzen können.                                 |
| 9    | muss            | Als Spieler möchte ich nach jeder Runde wissen, ob ich gewonnen oder verloren habe, um den Spielausgang zu verstehen. |
| 10    | muss            | Als Spieler möchte ich jederzeit ein neues Spiel starten oder das aktuelle abbrechen können, um flexibel zu bleiben. |
| 11   | kann            | Als Spieler möchte ich meine In-Game-Währung verwalten (Ein-/Auszahlungen), um ein authentisches Casino-Feeling zu erhalten. |
| 12   | kann            | Als Spieler möchte ich eine Highscore-Liste sehen, um meine Leistung mit anderen Spielern zu vergleichen.          |
| 13   | muss            | Als Spieler möchte ich Einstellungen (z. B. Limits) vornehmen können, um das Spiel anzupassen.       |
| 14   | kann            | Als Spieler möchte ich animierte Kartenbewegungen und visuelle Effekte sehen, um ein ansprechendes Spielerlebnis zu genießen. |
| 15   | muss            | Als Entwickler möchte ich eine Datenbankanbindung, um Spielerprofile, Highscores und Statistiken langfristig zu speichern. |

### 1.3 Testfälle

| **TC-№** | **Ausgangslage**           | **Eingabe**                                   | **Erwartete Ausgabe**                                        | **Zugehörige US** |
|----------|----------------------------|-----------------------------------------------|---------------------------------------------------------------|-------------------|
| 1.1      | Anmeldeseite offen         | Benutzername und Passwort eingeben um sich registrieren           | Benutzer wird erfolgreich registriert                          | US-1              |
| 2.1      | Anmeldeseite offen         | Benutzername und Passwort eingeben            | Benutzer wird erfolgreich angemeldet                          | US-2              |
| 3.1      | Spielstart                 | Tutorial starten                              | Tutorial führt Schritt-für-Schritt durch das Spiel            | US-3              |
| 4.1      | Chipsystem aktiviert       | Spieler setzt Chips                           | Chips werden korrekt vom Guthaben abgezogen (Wetteinsatz)     | US-4              |
| 5.1      | Spielstart                 | Spieler zieht eine Karte                      | Eine Karte wird dem Spieler hinzugefügt                       | US-5              |
| 6.1      | Kartenstapel leer          | Karte ziehen                                  | Fehler wird abgefangen, Meldung erscheint                     | US-6              |
| 7.1      | Spieler hat Karten         | Punktestand der karten berechnen                         | Punktestand wird korrekt angezeigt                            | US-7              |
| 8.1      | Spieler hat Karten         | Aktion „Stop“ auswählen                | Einsatz wird verdoppelt und eine Karte gezogen                | US-8              |
| 9.1      | Spielende                  | Gewinn-/Verlustlogik prüfen                   | Spieler erhält Ergebnis „Gewonnen“ oder „Verloren“            | US-9              |
| 10.1      | Spielende                  | Spiel neu starten                             | Ein neues Spiel beginnt, Karten werden neu gemischt           | US-10              |
| 11.1     | In-Game-Währung aktiviert  | Chips ein- oder auszahlen                     | Transaktion wird korrekt ausgeführt, Guthaben wird aktualisiert | US-11             |
| 12.1     | Spielende                  | Highscore-Liste anzeigen                      | Highscore-Liste wird korrekt dargestellt                      | US-12             |
| 13.1     | Einstellungsseite offen    | Limits und Spieleranzahl bearbeiten           | Änderungen werden erfolgreich übernommen                      | US-13             |
| 14.1     | Animation aktiviert        | Karte ziehen                                  | Animation für Kartenbewegungen wird angezeigt                 | US-14             |
| 15.1     | Datenbankanbindung aktiv   | Spiel beenden / Highscore speichern           | Spielerprofil, Highscores und Statistiken werden persistiert   | US-15             |

### 1.4 Diagramme

![Blackjack mit Anmeldefunktion](https://github.com/user-attachments/assets/9a6cc01c-567c-4f1e-9ea1-04a42690e7f9)

## 2Planen

| AP-№  | Frist       | Zuständig | Beschreibung                                                             | Zugehörige US | Geplante Zeit |
|-------|-------------|-----------|--------------------------------------------------------------------------|---------------|---------------|
| 1.A   | 15.11.2024  | Marku     | Registrierfunktion einbauen                                              | US-1          | 60 min       |
| 2.A   | 15.11.2024  | Marku     | Anmeldefunktion einbauen                                                 | US-2          | 60 min       |
| 3.A   | 06.11.2024  | Marku     | Interaktives Tutorial erstellen                                          | US-3          | 90 min       |
| 4.A   | 29.11.2024  | Angelov   | Chipsystem für virtuelle Einsätze entwickeln                             | US-4          | 90 min       |
| 5.A   | 15.11.2024  | Jashari   | Kartenmisch- und Ziehfunktion entwickeln                                 | US-5          | 70 min       |
| 6.A   | 13.12.2024  | Team      | Fehlerbehandlung erweitern (z. B. leeres Kartendeck)                     | US-6          | 60 min       |
| 7.A   | 22.11.2024  | Marku          | Punktestand berechnen und anzeigen                                       | US-7          | 60 min       |
| 8.A   | 22.11.2024  | Angelov, Jashari          | „Double Down“ und „Split“ implementieren                                 | US-8          | 90 min       |
| 9.A   | 29.11.2024  | Jashari   | Gewinn-/Verlustlogik prüfen und ausgeben                                 | US-9          | 60 min       |
| 10.A   | 29.11.2024  | Jashari     | Spiel-Neustart-Funktion einbauen                                         | US-10          | 30 min       |
| 11.A  | 20.11.2024  | Jashari   | In-Game-Währung entwickeln (Ein-/Auszahlungen)                           | US-11        | 60 min       |
| 12.A  | 06.12.2024  | Marku     | Highscore-Liste implementieren                                           | US-12         | 40 min       |
| 13.A  | 13.11.2024  | Angelov   | Einstellungsseite für Limits und Spieleranzahl hinzufügen                | US-13         | 60 min       |
| 14.A  | 06.12.2024  | Angelov   | Animationen für Kartenbewegungen hinzufügen                              | US-14         | 90 min       |
| 15.A  | 06.12.2024  | Marku  | Datenbankanbindung implementieren (Spielerprofile, Highscores, Stats)    | US-15         | 60 min       |
| 16.A  | 20.12.2024  | Team      | Projektdokumentation fertigstellen                                       | -             | 180 min       |
| 17.A  | 20.12.2024  | Team      | Mahara-Portfolio schreiben                                               | -             | 180 min       |
| 18.A  | 20.12.2024  | Team      | Finale Tests und Debugging                                               | -             | 120 min       |
| 19.A  | 20.12.2024  | Team      | Tägliche Team-Sitzungen (5 Min/Tag)                                      | -             | 30 min total  |

## 4.Realisieren

| AP-№ | Datum       | Zuständig       | Geplante Zeit | Tatsächliche Zeit |
|------|-------------|-----------------|---------------|-------------------|
| 1.A  | 16.11.2024  | Marku           | 60min      | 60 min           |
| 2.A  | 16.11.2024  | Marku           | 60 min       | 50 min           |
| 3.A  | 07.11.2024  | Marku           | 90 min       | 75 min           |
| 4.A  | 30.11.2024  | Angelov         | 90 min       | 70 min           |
| 5.A  | 16.11.2024  | Jashari         | 70 min       | 60 min           |
| 6.A  | 14.12.2024  | Team            | 60 min       | 70 min           |
| 7.A  | 23.11.2024  |  Marku          | 60 min       | 70 min            |
| 8.A  | 23.11.2024  | Jashari / Angelov  | 90 min       | 60 min            |
| 9.A  | 30.11.2024  | Jashari        | 60 min       |  min           |
| 10.A  | 30.11.2024  | Jashari        | 30 min       | 70 min            |
| 11.A | 21.11.2024  | Jashari         | 60 min       | 60 min            |
| 12.A | 07.12.2024  | Marku           | 40 min       | 80 min            |
| 13.A | 14.11.2024  | Angelov         | 60 min       | 60 min            |
| 14.A | 07.12.2024  | Angelov         | 90 min       | 160 min            |
| 15.A | 07.12.2024  | Jashari         | 60 min       | 70 min            |
| 16.A | 21.12.2024  | Team            | 180 min       | 120 min            |
| 17.A | 21.12.2024  | Team            | 180 min       | 200 min            |
| 18.A | 21.12.2024  | Team            | 120 min       | 100 min            |
| 19.A | 21.12.2024  | Team            | 30 min total  | 30 min            |



## 5. Kontrollieren

### 5.1 Testprotokoll

| TC-№ | Datum       | Resultat | Tester      | Verknüpfte US |
|------|-------------|----------|-------------|---------------|
| 1.1  | 20.12.2024  | OK       | Marku       | US-1          |
| 2.1  | 20.12.2024  | OK       | Marku       | US-2          |
| 3.1  | 20.12.2024  | OK       | Angelov     | US-3          |
| 4.1  | 20.12.2024  | OK       | Jashari     | US-4          |
| 5.1  | 20.12.2024  | OK       | Angelov     | US-5          |
| 6.1  | 20.12.2024  | OK       | Team        | US-6          |
| 7.1  | 20.12.2024  | OK       | Marku       | US-7          |
| 8.1  | 20.12.2024  | NOK   | Angelov     | US-8          |
| 9.1  | 20.12.2024  | OK       | Jashari     | US-9          |
| 10.1  | 20.12.2024  | OK       | Marku       | US-10          |
| 11.1 | 20.12.2024  | OK       | Team        | US-11         |
| 12.1 | 20.12.2024  | OK       | Angelov     | US-12         |
| 13.1 | 20.12.2024  | OK       | Team        | US-13         |
| 14.1 | 20.12.2024  | NOK       | Jashari     | US-14         |
| 15.1 | 20.12.2024  | OK       | Marku       | US-15         |

## 7. Teamsitzungsbericht

| Datum       | Erledigte Arbeitspakete                                                                                                                | Nächste Arbeitspakete                                                | Verzögerungen | Änderungen                                                                           | Pro                                                           | Con                                              |
|------|---------------|---------------------------------------------------------------------------------------------------------------------|---------------|--------------------------------------------------------------------------------------|---------------------------------------------------------------|---------------------------------------------------|
| 08.11.2024  | Das Projekt wurde ausgewählt, aufgeteilt und Informationen wurden eingeholt.| Erste Umsetzungsschritte einleiten, Basis-Gameplay entwickeln | Keine         | Keine    | Klarer Projektplan, klare Rollenverteilung                     | Noch keine Umsetzung erfolgt                      |
| 15.11.2024  | Grundstruktur erstellt, Basis-Gameplay (Karten ziehen, Punkte berechnen)                                            | „Double Down“- & „Split“-Funktionen, UI-Optimierungen, Testen & Debugging, Punktesystem & Highscore-Liste            | Keine         | Keine                                                                                | Solide Basis und erster Spielablauf                              | Noch kein erweitertes Gameplay (Double Down, Split)            |
| 22.11.2024  | „Double Down“- und „Split“-Funktionen, UI-Optimierungen, Testen & Debugging, Punktesystem & Highscore-Liste                            | Chipsystem mit Einsätzen, Integration einer Datenbank für Highscores/Statistiken, Einstellungsseite für Limits/Anzahl | Split funktioniert nicht vollständig        | Keine                                                                                | Erweiterte Spielmechaniken und stabilere UI                     | Noch kein Einsatzsystem, keine persistente Datenspeicherung     |
| 29.11.2024  | Chipsystem mit virtuellen Einsätzen, Datenbankanbindung (Highscores, Stats), Einstellungsseite für Limits und Spieleranzahl            | Code-Optimierung, Interaktives Tutorial, Animationen für Kartenbewegungen                                             | Keine         | Keine                                                                                | Wetten möglich, persistente Datenspeicherung, konfigurierbares Spiel | Code noch nicht optimiert, kein Tutorial, keine Animationen       |
| 06.12.2024  | Code-Optimierung, Interaktives Tutorial, Animationen für Kartenbewegungen                                                              | Fehlerbehandlung erweitern (ungültige Aktionen), Zeitlimit einbauen, Achievements hinzufügen                         | Karten werden zum Teil nicht richtig umgedreht.        | Keine                                                                                | Strukturierter Code, verbessertes Spielerlebnis durch Tutorial & Animationen | Noch kein Zeitlimit, keine Achievements                        |
| 13.12.2024  | Fehlerbehandlung erweitert, Dokumentation fortgeführt, Programmablauf kontrolliert                                                     | Mahara-Portfolios schreiben, Dokumentation fertigstellen, letzte Anpassungen                                         | Keine         | Zeitlimit & Achievements entfallen, Entscheidung der Gruppe                         | Fehlerfreiere Anwendung, bessere Dokumentation                  | Keine neuen Herausforderungen wie Zeitlimit oder Achievements   |
| 20.12.2024  | Mahara-Portfolios fertiggestellt, Dokumentation abgeschlossen, letzte Anpassungen vorgenommen                                           | Produktübergabe                                                                            | Keine         | Keine                                                                                | Vollständiges Paket: Code, Doku, Portfolio                      | Keine weiteren Entwicklungsaufgaben geplant                     |




