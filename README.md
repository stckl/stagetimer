# Stagetimer - Event Tech Edition

Ein hochmoderner, Webbasiertes Stagetimer-System, das stark an das Design von `timer.ted.com` angelehnt ist. Entwickelt für Senior Frontend Entwickler und Event-Techniker.

Dieses Projekt bietet eine Standalone-Lösung mit **Vue 3** und **PeerJS**, die sowohl lokal als auch über das Internet (via WebRTC) synchronisiert werden kann.

## 🚀 Features

- **Drei + Eins Modi**:
  - **Clock**: Aktuelle Uhrzeit (HH:MM:SS).
  - **Countdown**: Präziser Countdown mit TED-typischem Ampelsystem (Grün/Gelb/Rot).
  - **Stopwatch**: Hochzählende Stoppuhr.
  - **Black**: Ein "Blackout"-Modus für Pausen (nur Hintergrund).
- **Intelligente Steuerung**:
  - **Smart Time Input**: Eingabe von Minuten (z.B. `90`) oder `H:MM` (z.B. `1:30`) mit automatischer Formatierung.
  - **On-the-fly Korrektur**: Schnelle Anpassung während der Show (+5m, +1m, +10s und Gegenstücke).
  - **Remote Sync**: Kopplung beliebig vieler Geräte via WebRTC (PeerJS). Ein gemeinsamer Session-Code für alle Teilnehmer.
- **Design & UX**:
  - **Massive Typografie**: Perfekt zentrierte, fette serifenlose Schrift (Arial Black, Inter oder Google Fonts).
  - **Dynamisches Styling**: Hintergrundfarbe, Textfarbe und Schriftgröße (in vh) live anpassbar.
  - **Übergangseffekte**: Dezente Einzelziffer-Animationen (Fade, Zoom, Slide Up/Down, 3D Flip).
  - **Progress Bar**: Mitlaufender Balken am unteren Rand in Ampelfarbe.
- **100% Offline-fähig**: Alle Abhängigkeiten können lokal gespeichert werden.

## 🛠 Architektur

Die App besteht aus zwei Ansichten in einer einzigen Datei:
1. **Controller**: Das Steuerpult für den Operator (Tablet, Laptop).
2. **Display**: Die reine Ausspielung für das Bühnen-Display oder den Vorschaumonitor.

Die Synchronisation erfolgt primär über **WebRTC (PeerJS)** für verschiedene Geräte. Wenn beide Ansichten im selben Browser laufen, erfolgt ein automatischer Fallback auf **LocalStorage**.

## 📦 Installation & Setup

1. Klone das Repository:
   ```bash
   git clone git@github.com:stckl/stagetimer.git
   cd stagetimer
   ```

2. **Offline-Betrieb**:
   Für den Betrieb ohne Internetverbindung lade die folgenden Bibliotheken herunter und speichere sie im Projektordner:
   - [vue.global.js](https://unpkg.com/vue@3/dist/vue.global.js)
   - [peerjs.min.js](https://unpkg.com/peerjs@1.5.2/dist/peerjs.min.js)

3. Öffne die `index.html` in einem modernen Webbrowser.

## 🔗 Remote Sync

1. Öffne die App auf Gerät A (z.B. Haupt-Laptop).
2. Kopiere den angezeigten **Kopplungscode**.
3. Öffne die App auf Gerät B (z.B. Tablet).
4. Gib den Code im Bereich **Remote Sync** ein und klicke auf **Koppeln**.
5. Wähle auf einem Gerät "Controller" und auf dem anderen "Display".

## ⚖️ Lizenz

Dieses Projekt ist unter **The Unlicense** lizenziert. Das bedeutet, die Software ist gemeinfrei (Public Domain) und kann von jedem für jeden Zweck frei verwendet, verändert und verbreitet werden.

Weitere Informationen unter [unlicense.org](https://unlicense.org).
