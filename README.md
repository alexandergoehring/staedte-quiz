# staedte-quiz
von Claude Opus 4.6 generiertes Browserspiel

Promt an Claude Opus 4.6:
> Erstelle ein Browserspiel.
Es soll ein Quiz werden. 
Es sollen zehn deutsche große Städte erraten werden anhand von Bildern von Sehenswürdigkeiten der Städte.

Hinweise:
- die Grundlogik und Design war bereits beim FirstShot korrekt
- durch die KI wurden Spieledetails eigenständig ohne expolizite Vorgabe ausmodelliert:
  - Städte Auswahl
  - Sehenswürdigkeiten Auswahl
  - Quiz A/B/C/D Städtevorschläge
  - Fortschrittsbalken
  - Rundenzähler
  - Punktezähler
  - finale ergebnisabhängige textuelle und grafische Auswertung
- benötigte Zeit: ca. 30min
  - Initialer Prompt + 4 Iterationen
    - aufgrund von Bilder Download Problem 2te Runde mit Promt:
    - > die Bilder passen nicht. nicht alle Bilder laden fehlerfrei
    - die KI hat auf selbst erstellte SVG Grafiken umgestellt ('Statt externer Fotos enthält es jetzt eingebettete SVG-Illustrationen für jede Sehenswürdigkeit')
  - da SVG Grafiken nicht ansprechend waren weitere Runde mit Prompt:
    - > Anstatt der eingebetteten SVG Grafiken bitte reale Fotos verwenden, herunterladen und lokal bereitstellen. Also mit richtigen Fotos arbeiten.
    - KI erstellte Phyton Skript bilder_herunterladen.py ('Das Skript lädt echte Fotos von Wikimedia Commons herunter')
    - es gab noch Bilder Download Fehler bei Ausführung von 'python3 bilder_herunterladen.py'
    - daraufhin wurde einfach der Konsolen Error Output an die KI zur automatisierten Problemlösung zurück gegeben
      - 'Das Skript ist aktualisiert mit drei Verbesserungen: Bessere Dateinamen für Dresden und Nürnberg (die alten existierten nicht auf Wikimedia Commons), Pause zwischen Downloads (1,5 Sekunden), um das Rate-Limiting zu vermeiden, Automatische Wiederholung bei 429-Fehlern mit ansteigender Wartezeit'
    - noch eine Runde aufgrund Bilder Download Fehler bei Ausführung von 'python3 bilder_herunterladen.py'
      - 'Das Skript ist jetzt komplett umgebaut. Statt feste Dateinamen zu raten, nutzt es die Wikimedia Commons Such-API — es sucht dynamisch nach Bildern zu Begriffen wie "Frauenkirche Dresden" oder "Kaiserburg Nürnberg" und lädt den besten Treffer herunter.'  


Fazit:
- keine einzige Zeile Code programmiert
- nur die Claude KI instruiert

das Spiel ist live unter: https://alexandergoehring.github.io/staedte-quiz/quiz.html

