# Energieadaptive Produktionsumgebung – Beispielmodelle

Dieses GitHub-Repository stellt Beispielmodelle für eine **energieadaptive Produktionsumgebung** bereit. Die Modelle dienen als **Prototyp zur Demonstration der Informationsstruktur sowie des konzeptionellen Constraint-Aufbaus**.

---

# Modellübersicht

## 1. AML-Basismodell
**Datei:** `EnergieadaptiveProduktion_BaseClassLib_AML_1.0.0.aml`

Als Grundlage aller AML-Modelle wurde eine Basismodell-Datei erstellt. Diese enthält allgemeine und wiederverwendbare Definitionen wie:

- RoleClasses  
- InterfaceClasses  
- AttributeTypes  

Die Basismodell-Datei dient als zentrale Referenz und wird von allen weiteren AML-Modellen eingebunden.

---

## 2. AML-Produktionssystemmodell
**Datei:** `Produktionssystem.aml`

Dieses Modell enthält Informationen über das Produktionssystem, beispielsweise:

- MaschinenNennleistung  
- Fertigungszeit  

Diese Informationen werden genutzt, um den **Gesamtenergieverbrauch eines Fertigungsprozesses** zu berechnen.

Darüber hinaus enthält das Modell Informationen über die **Anzahl qualifizierter Mitarbeiter**, die an einer bestimmten Maschine oder einem Fertigungsprozess arbeiten.

---

## 3. AML-Energieerzeugungskomponentenmodell
**Datei:** `Energieerzeugungskomponente.aml`

Dieses Modell enthält Informationen zur Energieerzeugung, beispielsweise:

- Nennleistung pro PV-Modul  
- Anzahl installierter PV-Module  

Diese Informationen werden verwendet, um die **gesamte Energieerzeugung einer PV-Anlage** zu berechnen.

---

## 4. AML-Personalmodell
**Datei:** `Personal.aml`

Dieses Modell beschreibt Personalinformationen wie:

- Personalqualifikation (zeigt, an welchen Maschinen Mitarbeiter arbeiten dürfen)  
- Grundgehalt pro Stunde  
- Wochenendzuschlag in Prozent  

Diese Informationen werden genutzt, um die **Wochenendzuschlagskosten für eingesetzte Arbeitskräfte** zu berechnen.

---

## 5. AML-Energiepreismodell
**Datei:** `Energiepreis.aml`

Dieses Modell enthält Informationen über den **Energiepreis innerhalb eines bestimmten Zeitintervalls**.

---

## 6. OCL-Constraintmodell
**Datei:** `EnergieadaptiveProduktion_Constraints.ocl`

Diese Datei beschreibt die **Berechnungslogik und die Struktur der Constraints** auf Basis der Attribute aus den AML-Informationsmodellen.

### Constraint 1 – EnergieVerfügbarkeit

Dieser Constraint prüft, ob ein Fertigungsprozess nur dann geplant wird, wenn die durch die PV-Anlage erzeugte Energie größer ist als der Energieverbrauch des jeweiligen Fertigungsprozesses.

### Constraint 2 – KostenVergleich

Dieser Constraint prüft, ob ein Fertigungsprozess am Wochenende geplant werden soll. Dies ist nur dann sinnvoll, wenn die **Wochenendzuschlagskosten der Arbeitskräfte geringer sind als der Energiepreis**, der durch die Verschiebung des Prozesses eingespart werden kann.

---

# Modellbeschränkungen

Die bereitgestellten Modelle dienen ausschließlich als **Prototyp zur Demonstration der Modellstruktur und der Constraint-Logik**. Daher gelten folgende Einschränkungen:

## 1. Vereinfachte Modellstruktur

Die Modelle enthalten **nur eine minimale Menge an Attributen**, die zur Demonstration der Szenarien erforderlich sind. Weitere Attribute können in zukünftigen Arbeiten ergänzt werden, um realistischere Szenarien abzubilden.

## 2. Semantische Referenzierung

Eine **vollständige semantische Referenzierung zwischen Klassen aus unterschiedlichen AutomationML-Informationsmodellen** ist derzeit noch nicht implementiert. Diese stellt eine mögliche Erweiterung zukünftiger Arbeiten dar.

## 3. OCL-Constraints

Die bereitgestellte OCL-Datei dient ausschließlich der **konzeptionellen Darstellung von Berechnungen und Constraints**. Die Constraints werden derzeit **nicht direkt auf AutomationML SystemUnitClasses angewendet**.

## 4. Zukünftige Erweiterungen

Eine Softwarekomponente zur **direkten Anwendung von OCL-Constraints auf AML-Modelle** befindet sich derzeit in Entwicklung und wird in zukünftigen Arbeiten integriert.
