# Eigenen Code ins AG-Repository hochladen

In der AG arbeitet ihr hauptsächlich in den **Jupyter-Notebooks (`.ipynb`)** auf dem JetBot. Damit eure Ergebnisse nicht verloren gehen und alle sehen können, was ihr gebaut habt, ladet ihr sie in **euren Gruppenordner** im AG-Repository hoch.

Dafür braucht ihr **kein Terminal**, alles geht über den Browser.

**AG-Repository:** https://github.com/mapeit04/jetbot-ag

---

## Das Prinzip in einem Satz

Ihr erstellt eine **eigene Kopie** des Repositorys (*Fork*), ladet dort eure Notebooks hoch und schickt dann eine **Anfrage** (*Pull Request*), damit sie ins AG-Repository übernommen werden.

```
AG-Repository  ──Fork──▶  Kopie eurer Gruppe  ──Upload──▶  eure Notebooks
      ▲                                                        │
      └─────────────── Pull Request (Marc prüft & übernimmt) ◀─┘
```

---

## Einmalig: Einrichtung (pro Gruppe)

### 1. GitHub-Account

Jede Person braucht einen kostenlosen Account auf [github.com](https://github.com).

### 2. Fork erstellen (nur **eine** Person pro Gruppe)

1. Öffnet das [AG-Repository](https://github.com/mapeit04/jetbot-ag).
2. Klickt oben rechts auf **„Fork“** und dann auf **„Create fork“**.
3. Ihr landet in eurer Kopie: `github.com/<euer-name>/jetbot-ag`

### 3. Gruppenmitglieder hinzufügen

Damit die ganze Gruppe in den Fork hochladen kann:

1. Im Fork auf **„Settings“** klicken
2. Links **„Collaborators“** → **„Add people“**
3. GitHub-Namen der anderen Gruppenmitglieder eingeben
4. Die anderen bekommen eine Einladung per E-Mail und müssen sie **annehmen**.

### 4. Euren Gruppenordner finden

Eure Gruppe hat einen festen Ordner:

| Termin A | Termin B |
|---|---|
| `gruppen/termin-a/gruppe_a` | `gruppen/termin-b/gruppe_e` |
| `gruppen/termin-a/gruppe_b` | `gruppen/termin-b/gruppe_f` |
| `gruppen/termin-a/gruppe_c` | `gruppen/termin-b/gruppe_g` |
| `gruppen/termin-a/gruppe_d` | `gruppen/termin-b/gruppe_h` |

> ⚠️ **Wichtigste Regel:** Ändert **nur Dateien in eurem eigenen Gruppenordner**. Dann kommen sich die Gruppen nie in die Quere.

---

## Jedes Mal: Notebooks hochladen

### Schritt 1: Notebook vom JetBot herunterladen

1. Öffnet JupyterLab auf dem JetBot (`http://<jetbot-ip>:8888`).
2. **Ausgaben löschen**, damit die Datei klein bleibt: Notebook öffnen → Menü **Edit → Clear All Outputs**, dann speichern (`Strg` + `S`).
   Kamerabilder werden sonst direkt in die Datei eingebettet und machen sie riesig.
3. Im Dateibrowser links **Rechtsklick auf das Notebook → „Download“**.
   Die `.ipynb`-Datei landet im Download-Ordner eures Laptops.

> 💡 Gebt euren Notebooks **eindeutige Namen**, z. B. `collision_avoidance_eigene_strategie.ipynb` statt `Untitled3.ipynb`.

### Schritt 2: In euren Fork hochladen

1. Öffnet **euren Fork** auf GitHub (nicht das AG-Repository!).
2. Navigiert in **euren Gruppenordner**, z. B. `gruppen/termin-a/gruppe_b`.
3. **„Add file“ → „Upload files“**
4. Notebook(s) per Drag & Drop hineinziehen.
5. Unten eine kurze Beschreibung eingeben, z. B. *„Collision Avoidance mit eigener Fahrstrategie“*
6. **„Commit changes“** klicken.

Bestehende Dateien mit gleichem Namen werden dabei überschrieben. Die alte Version bleibt aber in der Git-Historie erhalten.

### Schritt 3: Pull Request stellen

1. Oben in eurem Fork erscheint der Hinweis *„This branch is X commits ahead of mapeit04/jetbot-ag:main“*.
2. Klickt auf **„Contribute“ → „Open pull request“**.
3. Gebt einen aussagekräftigen Titel ein, z. B. **„Gruppe B: Collision Avoidance“**, und beschreibt kurz, was ihr gemacht habt.
4. **„Create pull request“** klicken.

Marc schaut sich euren Pull Request an und übernimmt ihn. Falls etwas nicht passt, bekommt ihr dort einen Kommentar.

---

## Euren Fork aktuell halten

Wenn im AG-Repository neue Anleitungen oder Challenges dazukommen, bekommt euer Fork das **nicht automatisch** mit.

Im Fork oben auf **„Sync fork“ → „Update branch“** klicken. Das am besten **vor** jedem neuen Upload machen.

---

## Was **nicht** ins Repository gehört

| Nicht hochladen | Warum |
|---|---|
| Trainierte Modelle (`best_model.pth` usw.) | viel zu groß. GitHub erlaubt im Browser max. 25 MB pro Datei, ein AlexNet-Modell hat über 200 MB |
| Datensätze (`dataset/`, `dataset.zip`) | zu groß und zu viele Dateien |
| Passwörter, Zugangsdaten, persönliche Daten | das Repository ist für andere sichtbar |

Hochladen solltet ihr **Notebooks, eigene Python-Skripte, kurze Beschreibungen** und gerne ein paar **Fotos oder kurze Videos** eures Roboters in Aktion 🤖

---

## Bonus: Kurze README für eure Gruppe

Legt in eurem Gruppenordner eine `README.md` an (**„Add file“ → „Create new file“**) und erzählt kurz:

- Gruppenname (gerne kreativ, ihr braucht ihn spätestens beim Sumo-Turnier 😉)
- Was habt ihr ausprobiert?
- Was hat funktioniert, was nicht?

---

## Häufige Probleme

| Problem | Lösung |
|---|---|
| Ich sehe den „Settings“-Reiter nicht | Ihr seid im AG-Repository statt in eurem Fork, oder nicht der Besitzer des Forks |
| „Contribute“ zeigt nichts an | Ihr habt noch nichts committet, oder euer Fork ist schon auf dem Stand des AG-Repositorys |
| Upload schlägt fehl / Datei zu groß | Ausgaben im Notebook löschen (Schritt 1) oder große Dateien weglassen |
| Collaborator kann nicht hochladen | Einladung per E-Mail noch nicht angenommen |
