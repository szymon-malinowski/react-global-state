# Individuelle Learning Phase: Globalen Zustand mit der React Context API aufbauen

## Dein Ziel

Du baust eine kleine React-19-Anwendung, in der mehrere Komponenten auf gemeinsame Daten zugreifen. Dabei entscheidest du bewusst, welche Daten lokal bleiben und welche global verwaltet werden. Am Ende hast du eine funktionierende Context-basierte Zustandsverwaltung für ein kleines Dashboard mit Benutzerinfos, Theme und Benachrichtigungen.

## Das brauchst du

- Ein laufendes React-19-Projekt
- Node.js und npm
- Einen Editor wie VS Code
- Einen Browser mit DevTools
- Grundkenntnisse zu Komponenten, Props, `useState` und `useContext`

## Zeitplanung

- 10 Minuten: Projekt anlegen oder bestehendes React-Projekt vorbereiten
- 20 Minuten: Basis-Aufgabe 1
- 20 Minuten: Basis-Aufgabe 2
- 25 Minuten: Basis-Aufgabe 3
- 25 Minuten: Basis-Aufgabe 4
- 20 Minuten: Basis-Aufgabe 5
- Optional 20–30 Minuten: Erweiterungsaufgaben

## Basis-Aufgaben

### Aufgabe 1:

Ausgangsanwendung mit lokalem Zustand erstellen  
**Ziel:** Du erstellst eine kleine Anwendung, in der zunächst noch nicht-globaler Zustand in mehreren Komponenten vorkommt.  
**Arbeitsauftrag:** Erstelle eine Anwendung mit mindestens diesen Komponenten:
- `App`
- `Header`
- `Dashboard`
- `SettingsPanel`
- `NotificationBar`

Baue folgende Daten ein:
- Benutzername
- aktuelles Theme (`light` oder `dark`)
- Anzahl ungelesener Benachrichtigungen

Verwalte diese Daten zunächst lokal oder über Props, sodass du spürst, wo Weiterreichen von Daten unpraktisch wird. Baue außerdem eine kleine Interaktion ein:
- Theme umschalten
- Benutzername ändern
- Benachrichtigungszähler erhöhen oder zurücksetzen

**Erwartetes Ergebnis / Soll-Zustand:** Deine Anwendung läuft und zeigt, dass gemeinsame Daten aktuell noch umständlich zwischen Komponenten weitergegeben werden oder mehrfach verwaltet werden.

### Aufgabe 2:

Lokalen und globalen Zustand sauber trennen  
**Ziel:** Du entscheidest bewusst, welche Daten global sein sollen und welche lokal bleiben.  
**Arbeitsauftrag:** Analysiere deine Anwendung praktisch im Code und triff für jeden Zustand eine Entscheidung:
- Was soll global verfügbar sein?
- Was bleibt lokal in einer einzelnen Komponente?

Setze diese Trennung direkt um. Mindestens ein Zustand soll lokal bleiben, zum Beispiel:
- der Eingabewert eines Formularfelds
- ein geöffnet/geschlossen-Status eines kleinen UI-Elements

Dokumentiere deine Entscheidung kurz in Kommentaren oder in einer `README.md` mit 3–5 Stichpunkten.

**Erwartetes Ergebnis / Soll-Zustand:** Deine Anwendung enthält sowohl lokalen als auch global vorgesehenen Zustand, und du hast eine klare, nachvollziehbare Trennung umgesetzt.

### Aufgabe 3:

Eigenen Context erstellen und bereitstellen  
**Ziel:** Du richtest einen eigenen React Context für globale Daten ein.  
**Arbeitsauftrag:** Erstelle einen eigenen Context, zum Beispiel `AppContext`, und einen passenden Provider, zum Beispiel `AppProvider`. Lege darin die globalen Daten ab:
- Benutzername
- Theme
- Benachrichtigungen

Stelle zusätzlich Funktionen bereit, mit denen du diese Werte verändern kannst, zum Beispiel:
- Benutzername aktualisieren
- Theme umschalten
- Benachrichtigungen erhöhen
- Benachrichtigungen zurücksetzen

Wickle deine Anwendung so ein, dass alle benötigten Komponenten Zugriff auf den Context haben.

**Erwartetes Ergebnis / Soll-Zustand:** Es gibt einen funktionierenden Context mit Provider, und die globalen Daten werden zentral an einer Stelle verwaltet.

### Aufgabe 4:

Globale Daten in mehreren Komponenten verwenden  
**Ziel:** Du liest globale Daten in verschiedenen Komponenten aus und nutzt sie sichtbar in der Oberfläche.  
**Arbeitsauftrag:** Ersetze das bisherige Prop-Weiterreichen an mindestens drei Stellen durch `useContext`. Nutze die globalen Daten in mehreren Komponenten, zum Beispiel so:
- `Header` zeigt Benutzername und Theme an
- `NotificationBar` zeigt die Anzahl ungelesener Benachrichtigungen an
- `SettingsPanel` bietet Schaltflächen oder Eingabefelder zum Ändern der Werte

Achte darauf, dass Änderungen in einer Komponente sofort in den anderen betroffenen Komponenten sichtbar werden.

**Erwartetes Ergebnis / Soll-Zustand:** Mehrere Komponenten lesen dieselben globalen Daten aus dem Context, ohne dass du sie über mehrere Ebenen per Props durchreichen musst.

### Aufgabe 5:

Anwendung aufräumen und Context sinnvoll einsetzen  
**Ziel:** Du überprüfst, ob dein Context sinnvoll eingesetzt ist, und verbesserst die Struktur deiner Anwendung.  
**Arbeitsauftrag:** Räume deinen Code auf und prüfe dabei:
- Gibt es Props, die du jetzt nicht mehr brauchst?
- Gibt es Daten, die doch besser lokal bleiben sollten?
- Ist dein Provider übersichtlich aufgebaut?
- Sind die Namen für Context, Werte und Funktionen klar verständlich?

Ergänze außerdem einen kleinen Bereich in der Anwendung mit dem Titel „Warum global?“, in dem du in 2–4 kurzen Sätzen direkt in der UI erklärst, warum genau diese Daten global sind und andere Daten lokal bleiben.

**Erwartetes Ergebnis / Soll-Zustand:** Deine Anwendung ist strukturiert, nachvollziehbar und zeigt praktisch, wann Context sinnvoll ist und wann nicht.

## Erweiterungsaufgaben

### Erweiterungsaufgabe 1: Eigenen Hook für den Context anlegen

**Ziel:** Du vereinfachst den Zugriff auf den Context.  
**Arbeitsauftrag:** Erstelle einen eigenen Hook, zum Beispiel `useAppContext`, der den Zugriff auf deinen Context kapselt. Nutze diesen Hook statt direktem `useContext` in deinen Komponenten. Sorge dafür, dass du eine klare Fehlermeldung bekommst, falls der Hook außerhalb des Providers verwendet wird.

**Erwartetes Ergebnis / Soll-Zustand:** Deine Komponenten greifen einheitlich und sauber über einen eigenen Hook auf den globalen Zustand zu.

### Erweiterungsaufgabe 2: Context in mehrere Bereiche aufteilen

**Ziel:** Du strukturierst globalen Zustand feiner und vermeidest unnötige Kopplung.  
**Arbeitsauftrag:** Teile deinen bisherigen Context in mindestens zwei Kontexte auf, zum Beispiel:
- `ThemeContext`
- `UserContext`
- optional `NotificationContext`

Passe Provider und Komponenten so an, dass jede Komponente nur die Daten bezieht, die sie wirklich braucht.

**Erwartetes Ergebnis / Soll-Zustand:** Dein globaler Zustand ist besser organisiert und in logisch getrennte Bereiche aufgeteilt.

### Erweiterungsaufgabe 3: Globalen Zustand persistent machen

**Ziel:** Du machst deinen globalen Zustand im Alltag nützlicher.  
**Arbeitsauftrag:** Speichere mindestens einen globalen Wert dauerhaft im Browser, zum Beispiel:
- Theme
- Benutzername

Lade den gespeicherten Wert beim Start der Anwendung wieder ein. Teste das Verhalten nach einem Neuladen der Seite.

**Erwartetes Ergebnis / Soll-Zustand:** Mindestens ein globaler Zustand bleibt nach einem Reload erhalten.

## Wichtige Hinweise

- Arbeite Schritt für Schritt und teste nach jeder Aufgabe.
- Halte die Oberfläche bewusst klein, damit du dich auf den Zustand konzentrierst.
- Nutze für globale Daten nur Werte, die wirklich in mehreren Komponenten gebraucht werden.
- Behalte rein lokale UI-Zustände in der jeweiligen Komponente.
- Wenn du unsicher bist, entscheide pragmatisch und prüfe danach im laufenden Code, ob sich die Entscheidung bewährt.
- Verwende klare Namen für Context, Provider, Hook und Update-Funktionen.

## Reflexionsfragen

- Welche Daten in deiner Anwendung waren wirklich global?
- Bei welchen Daten war Context hilfreich, bei welchen eher unnötig?
- Wo hast du vorher Props weitergereicht, die du jetzt nicht mehr brauchst?
- Welche Zustände hast du bewusst lokal gelassen und warum?
- Wie würdest du deine Context-Struktur erweitern, wenn die Anwendung größer wird?

---