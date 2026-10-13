# Linux-Einführung und Grundbefehle

Der JetBot läuft unter **Linux (Ubuntu)**. Vieles erledigt ihr bequem über JupyterLab im Browser, aber spätestens bei der Einrichtung, bei Fehlersuche oder beim Kopieren von Dateien braucht ihr das **Terminal**. Diese Seite gibt euch die wichtigsten Grundlagen.

> 📖 **Ausführliche Befehlsübersicht (deutsch):** [ubuntuusers.de – Shell/Befehlsübersicht](https://wiki.ubuntuusers.de/Shell/Befehls%C3%BCbersicht/)
> Dort ist zu jedem Befehl eine eigene Wiki-Seite mit Beispielen verlinkt.

---

## 1. Was ist das Terminal?

Das Terminal (auch *Shell* oder *Konsole*) ist eine textbasierte Oberfläche: Ihr tippt einen Befehl ein, drückt Enter, und der Computer führt ihn aus.

**Terminal öffnen:** `Strg` + `Alt` + `T`

Die Zeile vor eurem Cursor nennt sich **Prompt** und sieht etwa so aus:

```
marc@laptop:~/Projekte$
```

| Teil | Bedeutung |
|---|---|
| `marc` | angemeldeter Benutzer |
| `laptop` | Name des Rechners |
| `~/Projekte` | Ordner, in dem ihr euch gerade befindet |
| `$` | normaler Benutzer (`#` wäre root/Administrator) |

---

## 2. Das Dateisystem

Unter Linux gibt es keine Laufwerksbuchstaben wie `C:\`. Alles hängt in **einem einzigen Baum**, der bei `/` (dem *Root*) beginnt.

| Pfad | Inhalt |
|---|---|
| `/` | Wurzel des gesamten Dateisystems |
| `/home/<benutzer>` | euer persönlicher Ordner, Kurzform: `~` |
| `/etc` | Konfigurationsdateien |
| `/usr` | installierte Programme |
| `/tmp` | temporäre Dateien |

### Absolute und relative Pfade

Das ist der häufigste Stolperstein am Anfang:

- **Absolut:** beginnt mit `/` oder `~` und gilt immer, egal wo ihr gerade seid
  `cd ~/Projekte/jetbot-ag/docs`
- **Relativ:** gilt **ab dem Ordner, in dem ihr gerade seid**
  `cd docs` funktioniert nur, wenn es im aktuellen Ordner einen Ordner `docs` gibt

| Kürzel | Bedeutung |
|---|---|
| `.` | aktueller Ordner |
| `..` | übergeordneter Ordner (eine Ebene hoch) |
| `~` | euer Home-Ordner |

> 💡 **Tipp:** Wenn ein Befehl meldet *„Datei oder Verzeichnis nicht gefunden“*, prüft zuerst mit `pwd`, wo ihr gerade seid.

---

## 3. Grundbefehle

### Orientieren und bewegen

| Befehl | Bedeutung | Beispiel |
|---|---|---|
| `pwd` | Wo bin ich gerade? (*print working directory*) | `pwd` |
| `ls` | Inhalt des Ordners anzeigen (*list*) | `ls` |
| `ls -la` | auch versteckte Dateien, mit Details | `ls -la` |
| `cd` | Ordner wechseln (*change directory*) | `cd Projekte` |
| `cd ..` | eine Ebene nach oben | `cd ..` |
| `cd ~` oder `cd` | zurück in den Home-Ordner | `cd` |

### Dateien und Ordner

| Befehl | Bedeutung | Beispiel |
|---|---|---|
| `mkdir` | Ordner anlegen (*make directory*) | `mkdir test` |
| `touch` | leere Datei anlegen | `touch notizen.txt` |
| `cp` | kopieren (*copy*) | `cp a.txt b.txt` |
| `cp -r` | Ordner mit Inhalt kopieren | `cp -r ordner1 ordner2` |
| `mv` | verschieben oder umbenennen (*move*) | `mv alt.txt neu.txt` |
| `rm` | Datei löschen (*remove*) | `rm datei.txt` |
| `rm -r` | Ordner mit Inhalt löschen | `rm -r ordner` |

> ⚠️ **Achtung:** `rm` löscht **endgültig**, es gibt keinen Papierkorb. Vor allem mit `rm -r` vorsichtig sein!

### Dateien ansehen und bearbeiten

| Befehl | Bedeutung | Beispiel |
|---|---|---|
| `cat` | Inhalt einer Datei ausgeben | `cat notizen.txt` |
| `less` | lange Dateien seitenweise lesen (Beenden mit `q`) | `less log.txt` |
| `head` / `tail` | erste bzw. letzte Zeilen anzeigen | `tail -n 20 log.txt` |
| `nano` | einfacher Texteditor im Terminal | `nano notizen.txt` |

**nano-Kurzbefehle:** `Strg` + `O` speichern, `Enter` bestätigen, `Strg` + `X` beenden

### Software und Rechte

| Befehl | Bedeutung | Beispiel |
|---|---|---|
| `sudo` | Befehl mit Administratorrechten ausführen | `sudo apt update` |
| `sudo apt update` | Paketlisten aktualisieren | |
| `sudo apt upgrade` | installierte Programme aktualisieren | |
| `sudo apt install` | Programm installieren | `sudo apt install htop` |
| `chmod +x` | Datei ausführbar machen | `chmod +x skript.sh` |

### Netzwerk (wichtig für den JetBot!)

| Befehl | Bedeutung | Beispiel |
|---|---|---|
| `hostname -I` | eigene IP-Adresse anzeigen | `hostname -I` |
| `ip a` | alle Netzwerkschnittstellen mit Details | `ip a` |
| `ping` | ist ein Gerät erreichbar? (Abbrechen mit `Strg` + `C`) | `ping 192.168.43.17` |
| `ssh` | per Terminal auf einem anderen Rechner anmelden | `ssh <benutzer>@<jetbot-ip>` |
| `scp` | Dateien zwischen Rechnern kopieren | `scp datei.txt <benutzer>@<jetbot-ip>:~/` |

Die IP-Adresse des JetBots steht auf seinem kleinen **OLED-Display**.

### System überwachen

| Befehl | Bedeutung |
|---|---|
| `top` / `htop` | laufende Prozesse und CPU-Auslastung (Beenden mit `q`) |
| `free -h` | Arbeitsspeicher-Auslastung |
| `df -h` | freier Speicherplatz |
| `tegrastats` | **nur auf dem JetBot:** Auslastung von CPU, GPU, RAM und Temperatur |

### Hilfe bekommen

| Befehl | Bedeutung |
|---|---|
| `man <befehl>` | Handbuch zu einem Befehl (Beenden mit `q`) |
| `<befehl> --help` | Kurzhilfe zu einem Befehl |

---

## 4. Tastenkürzel, die euch viel Zeit sparen

| Taste | Funktion |
|---|---|
| `Tab` | **Autovervollständigung** für Befehle, Datei- und Ordnernamen. Einfach anfangen zu tippen und `Tab` drücken! |
| `Tab` `Tab` | alle Möglichkeiten anzeigen |
| `↑` / `↓` | vorherige Befehle durchblättern |
| `Strg` + `C` | laufenden Befehl abbrechen |
| `Strg` + `L` | Bildschirm leeren (wie `clear`) |
| `Strg` + `Shift` + `C` / `V` | im Terminal kopieren / einfügen |

> 💡 Mit `Tab` vermeidet ihr auch die meisten Tippfehler in Pfaden.

---

## 5. Probiert's aus

Kleine Aufwärmübungen, ohne feste Lösung. Experimentiert einfach:

1. Findet heraus, in welchem Ordner ihr nach dem Öffnen des Terminals seid.
2. Legt in eurem Home-Ordner einen Ordner `jetbot-test` an, wechselt hinein und erstellt dort eine Datei mit `nano`. Schreibt etwas hinein und lasst es euch mit `cat` anzeigen.
3. Benennt die Datei um, kopiert sie, und löscht am Ende den ganzen Ordner wieder.
4. Wie lautet die IP-Adresse eures Laptops? Könnt ihr den JetBot anpingen?
5. Meldet euch per `ssh` auf dem JetBot an und schaut euch mit `tegrastats` an, was er gerade macht.
6. **Bonus:** Was macht der Befehl `sl`? (Tipp: vorher mit `sudo apt install sl` installieren)

---

## Weiterführende Links

- [ubuntuusers.de – Shell/Befehlsübersicht](https://wiki.ubuntuusers.de/Shell/Befehls%C3%BCbersicht/): deutsche Übersicht aller wichtigen Befehle
- [ubuntuusers.de – Shell](https://wiki.ubuntuusers.de/Shell/): Grundlagen zur Shell
- [Ubuntu Tutorial: The Linux command line for beginners](https://ubuntu.com/tutorials/command-line-for-beginners) (englisch): interaktives Einsteiger-Tutorial
