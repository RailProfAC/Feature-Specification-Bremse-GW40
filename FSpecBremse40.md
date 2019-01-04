# Feature Specification Bremse 40 #

Bremse Güterwagen 4.0

Version draft

Prepared by Raphael Pfaff

FH Aachen

<date created>

Revision History
<table>
<tr>
<th>Name</th>
<th>Date</th>
<th>Reason for Changes</th>
<th>Version</th>
</tr>
<tr>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
</table>

## 1 Introduction ##

Dieses Dokument beschreibt die Umsetzung des Bremssystems für den Güterwagen 4.0 im Rahmen des Projekts "Neue Elektronik- und Kommunikationssysteme für den intelligenten, vernetzten Güterwage (FKZ 16ES0850K)".

### 1.1 Purpose ###

Das vorliegende Dokument beschreibt die Anforderungen an die Komponenten des Bremssystem für

- Labormuster und
- Demonstrator.

Es wird im folgenden von einem für den SS-Verkehr geeigneten Güterwagen ausgegangen.

### 1.2 Document Conventions ###

### 1.3 Glossary ###

### 1.4 Intended Audience and Reading Suggestions ###

### 1.5 Product Scope ###

### 1.6 References ###

## 2 Overall Description ##

### 2.1 Product Perspective ###

### 2.2 Product Functions ###

Die Bremse des Güterwagen 4.0 bietet folgende Funktionen:

- TSI-konformes Steuerventil
    - Bremsarten G und P
    - Automatische Lastabbremsung
- Fernbetätigte Endabsperrhähne
- Anzeige des Zustands der pneumatischen Kupplung (drucklos/druckbeaufschlagt)
- Fernbetätigung folgender Funktionen
    - Schnelllösen
    - Bremse aus
    - Bremsstellung
- Feststellbremse fernbetätigt
- ep-Bremsen
- Messung C-Druck


### 2.3 User Classes and Characteristics ###

Anwender des beschriebenen Bremssystems sind:

- Rangierende
- WagenmeisterInnen
- Bremsprobenberechtigte
- Triebfahrzeug- und Lokrangierführende

### 2.4 Operating Environment ###

### 2.5 Design and Implementation Constraints ###

Aus Zulassungsgründen wird ein UIC/TSI-kompatibles Steuerventil eingesetzt.

### 2.6 User Documentation ###

### 2.7 Assumptions and Dependencies ###

## 3 External Interface Requirements ##

### 3.1 User Interfaces ###

### 3.2 Hardware Interfaces ###

| --- | --- | --- |
| Komponente | Schnittstelle | Kommentar |
| TSI-konformes Steuerventil  | Verschraubung gemäß gewähltem Steuerventil | |
| | Schnelllösen, Bremsstellung offen | |
| Relaisventil | | |
| --- | --- | --- |

1. Das Relaisventil ist für automatische Lastabbremsung mit Wiegeventil vorgesehen. 
    
### Endabsperrhähne ###

1. Die Endabsperrhähne verfügen über einen freien Querschnitt von 1,25".
1. Die Endabsperrhähne sind bistabil, d.h. verbleiben ohne Betätigung in ihrem letzten Zustand.
1. Die Betätigungszeit für den Übergang Öffnen-Schließen beträgt maximal 10 s.
1. Das Funktionsprinzip der Hähne ist geeignet, die Anforderungen der DIN EN 14601 erfüllen zu können. Für die Demonstratoren und Labormuster muss diese Norm nicht erfüllt werden.
1. Eine fahrzeugseitige Verschraubung nach G1 1/4i (DIN EN ISO 228-1) ist zu bevorzugen. Für den Demonstrator kann die Kompatibilität durch einen Adapter hergestellt werden.
1. Kupplungsseitig ist eine Verschraubung mit Whitworth-Gewinde mit stumpfen Gewinden für G1 1⁄4i—Leitungen zu bevorzugen. Für den Demonstrator kann die Kompatibilität durch einen Adapter hergestellt werden.

### Außenanzeige ###

1. Mindestens eine Anzeige je Fahrzeugende zum Einbau am Pufferträger ist vorzusehen.
1. Die Anzeige stellt den Zustand der Bremskupplung (drucklos/druckbeaufschlagt) dar.
1. Die Anzeige muss Überdrücke > 0,5 bar in den Bremskupplungen anzeigen, bspw. durch die Farbe "Rot" im Schauglas.
1. Bei Unterschreiten des Drucks wird bspw. die Farbe "Grün" angezeigt.
1. Die Anzeige muss im stromlosen Zustand verfügbar sein.

### Fernbetätigung der SV-Funktionen ###

1. Es müssen folgende Funktionen fernbetätigt werden können:
    - Schnelllösen
    - Bremse aus
    - Bremsstellung

#### Schnelllösen ####

1. Ein Löseimpuls löst die Schnelllösefunktion des Steuerventils aus.
1. Der Löseimpuls kann elektromechanisch oder pneumatisch auf das Steuerventil übertragen werden.

#### Bremse aus ####

1. Die Funktion ist bistabil umzusetzen.
1. Es werden folgende Verbindungen geöffnet bzw. geschlossen:
    - HLL - SV (Entlüftung zum SV)
    - SV - R (Entlüftung zum SV)
    - SV - Cv (Entlüftung zum Relaisventil)
1. Die Betätigung muss in weniger als 10 Sekunden durchgeführt werden.

#### Bremsstellung ####

1. Die Bremsstellung wird elektrisch bistabil durch Verstellen des SV umgestellt.
1. Eine Rückmeldung ist vorzusehen.

### Feststellbremse ###

1. Die Feststellbremse kann unabhängig von der pneumatischen Energie im Wagen angelegt und gelöst werden.
1. Das Anlegen und Lösen erfolgt bistabil durch eletrischen Impuls.
1. Eine Rückmeldefunktion für den gelösten Zustand ist vorzusehen.
1. Die Bremskraft am Bremszylinder beträgt 7500 kN (für 2%-Gefälle, 90 t, Klotzbremse).
1. Alternative Lösungen, wie Federspeicher oder FT Park Lock können vorgeschlagen werden.

### ep-Bremsen ###

1. Ein ep-Brems-Ventil wird mit der HLL verbunden.
1. Das Ventil wird zum Bremsen bestromt.
1. Das Ventil entlüftet die HLL im Wagen in (3,5...5) s von Regelbetriebsdruck auf 3,5 bar.

### Messung C-Druck ###

### 3.3 Software Interfaces ###

### 3.4 Communication Interfaces ###

## 4 System Features ##

### TSI-konformes Steuerventil ###

1. Es wird ein TSI-konformes Steuerventil für die pneumatische Bremse eingesetzt.
1. Das Steuerventil verfügt über die Bremsstellungen G und P.
1. Das Steuerventil verfügt über automatisches Schnelllösen.
1. Das Relaisventil ist vorzugsweise nicht integriert.

### Relaisventil ###

1. Das Relaisventil ist für automatische Lastabbremsung mit Wiegeventil vorgesehen. 
    
### Endabsperrhähne ###

1. Die Endabsperrhähne verfügen über einen freien Querschnitt von 1,25".
1. Die Endabsperrhähne sind bistabil, d.h. verbleiben ohne Betätigung in ihrem letzten Zustand.
1. Die Betätigungszeit für den Übergang Öffnen-Schließen beträgt maximal 10 s.
1. Das Funktionsprinzip der Hähne ist geeignet, die Anforderungen der DIN EN 14601 erfüllen zu können. Für die Demonstratoren und Labormuster muss diese Norm nicht erfüllt werden.
1. Eine fahrzeugseitige Verschraubung nach G1 1/4i (DIN EN ISO 228-1) ist zu bevorzugen. Für den Demonstrator kann die Kompatibilität durch einen Adapter hergestellt werden.
1. Kupplungsseitig ist eine Verschraubung mit Whitworth-Gewinde mit stumpfen Gewinden für G1 1⁄4i—Leitungen zu bevorzugen. Für den Demonstrator kann die Kompatibilität durch einen Adapter hergestellt werden.

### Außenanzeige ###

1. Mindestens eine Anzeige je Fahrzeugende zum Einbau am Pufferträger ist vorzusehen.
1. Die Anzeige stellt den Zustand der Bremskupplung (drucklos/druckbeaufschlagt) dar.
1. Die Anzeige muss Überdrücke > 0,5 bar in den Bremskupplungen anzeigen, bspw. durch die Farbe "Rot" im Schauglas.
1. Bei Unterschreiten des Drucks wird bspw. die Farbe "Grün" angezeigt.
1. Die Anzeige muss im stromlosen Zustand verfügbar sein.

### Fernbetätigung der SV-Funktionen ###

1. Es müssen folgende Funktionen fernbetätigt werden können:
    - Schnelllösen
    - Bremse aus
    - Bremsstellung

#### Schnelllösen ####

1. Ein Löseimpuls löst die Schnelllösefunktion des Steuerventils aus.
1. Der Löseimpuls kann elektromechanisch oder pneumatisch auf das Steuerventil übertragen werden.

#### Bremse aus ####

1. Die Funktion ist bistabil umzusetzen.
1. Es werden folgende Verbindungen geöffnet bzw. geschlossen:
    - HLL - SV (Entlüftung zum SV)
    - SV - R (Entlüftung zum SV)
    - SV - Cv (Entlüftung zum Relaisventil)
1. Die Betätigung muss in weniger als 10 Sekunden durchgeführt werden.

#### Bremsstellung ####

1. Die Bremsstellung wird elektrisch bistabil durch Verstellen des SV umgestellt.
1. Eine Rückmeldung ist vorzusehen.

### Feststellbremse ###

1. Die Feststellbremse kann unabhängig von der pneumatischen Energie im Wagen angelegt und gelöst werden.
1. Das Anlegen und Lösen erfolgt bistabil durch eletrischen Impuls.
1. Eine Rückmeldefunktion für den gelösten Zustand ist vorzusehen.
1. Die Bremskraft am Bremszylinder beträgt 7500 kN (für 2%-Gefälle, 90 t, Klotzbremse).
1. Alternative Lösungen, wie Federspeicher oder FT Park Lock können vorgeschlagen werden.

### ep-Bremsen ###

1. Ein ep-Brems-Ventil wird mit der HLL verbunden.
1. Das Ventil wird zum Bremsen bestromt.
1. Das Ventil entlüftet die HLL im Wagen in (3,5...5) s von Regelbetriebsdruck auf 3,5 bar.

### Messung C-Druck ###

1. Der Bremszylinderdruck (D-Cruck) wird gemessen.
1. Der Sensor arbeitet als Stromsensor (4-20 mA).
1. Der Messbereich ist (0...5) bar.
1. Die Messunsicherheit und Auflösing ist so gewählt, dass die erste und letzte Bremsstufe (0,45 bar Cv) sicher erkannt werden. Eine Messunsicherheit von 0,05 bar erfüllt diese Anforderung.

# 5. Nonfunctional Requirements #

### 5.1 Performance Requirements ###

### 5.2 Safety Requirements ###

1. Alle elektrischen Komponenten arbeiten mit 24 V.

### 5.3 Security Requirements ###

### 5.4 Software Quality Attributes ###

### 5.5 Business Rules ###

# 6 Other Requirements #

<!--appendix-->
