# Nutzung Pvlib
Nutzung von pvLib zur Simulation deutscher PV-Anlagen.

# Motivation
Verfügbare Programme zur Simulation von PV-Anlagen sind oft nicht frei zu nutzen. Beispiele dafür sind:
- PVsyst (Schweizer Programm), Lizenz für 600 CHF pro Jahr (https://www.pvsyst.com/shop-prices/)
- PV\*SOL (deutsches Programm), Lizenz einmalig 850 Euro plus Wartungsgebühr von 160€/Jahr (https://valentin-software.com/produkte/pvsol/)  

Diese kommerziellen Programme pflegen umfangreiche Datenbanken mit Datensätzen für Wechselrichter und Solarmodule.

Andere sind von spezifischen Herstellern (z.B. SolarEdge) und damit auf Komponenten jener festgelegt. 

Frei verfügbare Tools (z.B. Solar-Planit, www.solar-planit.de) sind oftmals  auf die beim jeweiligen Unternehmen lieferbaren Komponenten und bezüglich der universellen Verwendbarkeit eingeschränkt.

Eines der wenigen, frei verfügbaren Simulationstools mit großem Funktionsumfang und wissenschaftlich fundiertem Hintergrund ist pvLib. Ursprünglich als Toolbox für Matlab entstanden, bietet sich jetzt auch die Nutzung mit Python an: https://pvpmc.sandia.gov/applications/pv_lib-toolbox/

# Probleme
pvLib ist ein Projekt aus dem Dunstkreis des US-DoE (Department of Energy der Vereinigten Staaten von Amerika). Die im Programm mitgelieferten Daten für Wechselrichter und Solarmodule stammen aus SAM (System Advisor Model), einem Projekt des US-amerikanischen National Renewable Energy Laboratory) (https://sam.nrel.gov/). Daher sind die im Programm verfügbaren Modelle für Wechselrichter und Solarmodule stark auf den amerikanischen Markt ausgelegt.

Regelmäßig sind die über SAM verfügbaren Daten neuer als diejenigen, welche in pvLib mitgelieferten werden (mehr/aktuellere Module und Wechselrichter). 

Als alternative Datenquelle für pvLib steht mit pvfree eine Online-Datenbank zur Verfügung (https://pvfree.azurewebsites.net), die dort verfügbaren Daten sind jedoch mit wenigen Ausnahmen identisch mit denjenigen aus SAM.

Es fehlt also an einfach nutzbaren Daten für pvLib im deutschen/europäischen Kontext.
