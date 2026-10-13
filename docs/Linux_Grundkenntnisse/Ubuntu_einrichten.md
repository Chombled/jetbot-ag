# Linux-Einführung

Der JetBot läuft unter Linux (Ubuntu). Für die AG braucht deshalb jede Person einen Laptop mit Linux, am besten **Ubuntu**.

Es gibt zwei Möglichkeiten:

| Variante | Für wen? |
|---|---|
| **Dual-Boot** (Ubuntu neben Windows) | empfohlen, beste Leistung |
| **Virtuelle Maschine** (z. B. VirtualBox) | wer nichts an der Festplatte ändern will und einen ausreichend starken Laptop hat |

## Dual-Boot einrichten

Schritt-für-Schritt-Anleitung (Ubuntu neben Windows):
👉 [Einrichten eines Dual-Boot-Systems mit Ubuntu und Windows (gcore.com)](https://gcore.com/de/learning/dual-boot-ubuntu-windows-setup)

**Bevor ihr loslegt, unbedingt beachten:**

- **Backup machen!** Beim Partitionieren kann im schlimmsten Fall etwas verloren gehen.
- **BitLocker / Geräteverschlüsselung:** Bei vielen neueren Windows-Laptops ist die Festplatte verschlüsselt. Notiert euch **vorher** den BitLocker-Wiederherstellungsschlüssel (zu finden unter https://account.microsoft.com/devices/recoverykey). Ohne ihn kommt ihr nach Änderungen im BIOS/UEFI unter Umständen nicht mehr in Windows.
- **Neuere Ubuntu-Versionen** bieten im Installer meist direkt die Option „Ubuntu neben Windows installieren“ an. Das ist einfacher als die manuelle Partitionierung („Etwas anderes“) aus der Anleitung.
- Für Ubuntu mindestens **25 GB**, besser **50 GB** freien Speicher einplanen.

## Alternative: Virtuelle Maschine

- Software: [VirtualBox](https://www.virtualbox.org/) + [Ubuntu Desktop ISO](https://ubuntu.com/download/desktop)
- Mindestens **4 GB RAM**, **2 CPU-Kerne** und **25 GB Speicher** für die VM
- Netzwerkadapter der VM auf **„Netzwerkbrücke“ (Bridged)** stellen, damit die VM im selben Netz (Hotspot) ist wie der JetBot

## Bei Problemen

Meldet euch frühzeitig, **nicht erst am AG-Termin**, damit wir die Sitzung nicht mit Installationen verbringen.
