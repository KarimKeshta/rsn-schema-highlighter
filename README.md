![Vorschau des Highlightings](screenshot.png)
# Relational Schema Notation (RSN) Highlighter

Ein VS Code Addon für Studenten, um **DBCoach**-Aufgaben und relationale Schemata einfacher zu bearbeiten.

Dieses Plugin bietet Syntax-Highlighting für die relationale Notation, wie sie in der Vorlesung verwendet wird. Es hilft dir, Primärschlüssel, Fremdschlüssel und Beziehungen sofort visuell zu erkennen.

## ✨ Features

* **Syntax Highlighting:** Färbt deine Schemata automatisch ein.
* **Intelligente Erkennung:**
    * 🟨 **Tabellen** werden Gold/Gelb hervorgehoben.
    * 🩷 **Primärschlüssel** (`_ID_` oder `{ID}`) leuchten in Pink.
    * 💠 **Fremdschlüssel** (`(ID) ->`) werden Hellblau/Cyan markiert.
    * 🟠 **Werte & Indikatoren** (wie `X` oder Zahlen) sind Orange.
* **Candidate Keys:** Erkennt auch `{Kandidatenschlüssel}` innerhalb der Notation.
* **Automatische Einrückung:** Hilft beim sauberen Formatieren der Aufgaben.

## 🚀 Installation

### Über den VS Code Marketplace
1. Öffne VS Code.
2. Drücke `Strg+P` (oder `Cmd+P` auf Mac).
3. Tippe: `ext install [DeinPublisherName].rsn-highlighter`
*(Hinweis: Dieser Schritt gilt erst, wenn du es veröffentlicht hast)*

### Manuelle Installation (.vsix)
Wenn du die Datei von einem Kommilitonen erhalten hast:
1. Gehe in VS Code zum Bereich **Erweiterungen** (`Strg+Shift+X`).
2. Klicke oben rechts auf die drei Punkte `...`.
3. Wähle **"Install from VSIX..."**.
4. Wähle die Datei `rsn-highlighter-0.0.1.vsix` aus.

## 🎨 Farbschema

Damit du dich in den Aufgaben schnell zurechtfindest:

| Element | Farbe | Bedeutung |
| :--- | :--- | :--- |
| **Tabellenname** | 🟢 Grün / 🟡 Gold | Der Name der Relation (z.B. `Gerichte`) |
| **Primärschlüssel** | 🩷 **Pink** | Eindeutige Identifikation (`_ID_` oder `{ID}`) |
| **Fremdschlüssel** | 💠 *Cyan* | Verweis auf eine andere Tabelle |
| **Attribute** | ⚪ Weiß | Normale Datenfelder |
| **Constraints** | 🟣 Lila | `NOT NULL`, `UNIQUE`, Pfeile `->` |

## 📝 Beispiel Code

Erstelle eine Datei mit der Endung `.rsn` und füge deinen DBCoach-Code ein:

```rsn
Gerichte ( _GerichtID_ , Name, Preis )
{GerichtID} -> X
Name NOT NULL

Fotos ( _FotoID_, GerichtID, Dateipfad )
{FotoID} -> X
(GerichtID) -> Gerichte(GerichtID)