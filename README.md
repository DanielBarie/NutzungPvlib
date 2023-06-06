# Nutzung Pvlib
Ideen zur Nutzung von pvLib zwecks Simulation deutscher PV-Anlagen.

# Motivation
PV-Anagen sind komplexe Systeme mit vielen einzelnen Komponenten. Das Verhalten der Komponenten muss einzeln und im Zusammenspiel betrachtet werden. Dazu sind umfangreichen Daten zu Solarmodulen und Wechselrichtern sowie Wetterdaten notwendig. Aufrund der Komplexität erfolgt vor dem Aufbau einer PV-Anlage regelmäßig eine Simulation, welche datenbasierte Modelle für die Komponenten erfordert.  

Verfügbare Programme zur Simulation von PV-Anlagen sind oft nicht frei zu nutzen. Beispiele dafür sind:
- PVsyst (Schweizer Programm), Lizenz für 600 CHF pro Jahr (https://www.pvsyst.com/shop-prices/)
- PV\*SOL (deutsches Programm), Lizenz einmalig 850 Euro plus Wartungsgebühr von 160€/Jahr (https://valentin-software.com/produkte/pvsol/)  

Diese kommerziellen Programme pflegen umfangreiche Datenbanken mit Datensätzen für Wechselrichter und Solarmodule. Aus den Datensätzen werden für die Simulation erforderliche Parameter der Modelle gespeist.

Andere sind von spezifischen Herstellern (z.B. SolarEdge) und damit auf Komponenten jener festgelegt. 

Frei verfügbare Tools (z.B. Solar-Planit, www.solar-planit.de) sind oftmals  auf die beim jeweiligen Unternehmen lieferbaren Komponenten und bezüglich der universellen Verwendbarkeit eingeschränkt.

Eines der wenigen, frei verfügbaren Simulationstools mit großem Funktionsumfang und wissenschaftlich fundiertem Hintergrund ist pvLib. Ursprünglich als Toolbox für Matlab entstanden, bietet sich jetzt auch die Nutzung mit Python an: https://pvpmc.sandia.gov/applications/pv_lib-toolbox/

# Probleme
pvLib ist ein Projekt aus dem Dunstkreis des US-DoE (Department of Energy der Vereinigten Staaten von Amerika). Die im Programm mitgelieferten Daten für die Wechselrichtern und Solarmodulen zu Grunde liegenden Modelle stammen aus SAM (System Advisor Model), einem Projekt des US-amerikanischen National Renewable Energy Laboratory) (https://sam.nrel.gov/). Daher sind die im Programm verfügbaren Typen (und damit Modelltaten) von Wechselrichtern und Solarmodulen stark auf den amerikanischen Markt ausgelegt.

Regelmäßig sind die über SAM verfügbaren Daten neuer als diejenigen, welche in pvLib mitgelieferten werden (mehr/aktuellere Module und Wechselrichter). 

Als alternative Datenquelle für pvLib steht mit pvfree eine Online-Datenbank zur Verfügung (https://pvfree.azurewebsites.net), die dort verfügbaren Daten sind jedoch mit wenigen Ausnahmen identisch mit denjenigen aus SAM.

Es fehlt also an einfach nutzbaren Daten für pvLib im deutschen/europäischen Kontext.

# Modelle pvLib
Die Simulation komplexer Syteme arbeitet mit Modellen der einzelnen Systemkomponenten; diese wiederum werden im Zusammenspiel betrachtet. Regelmäßig besteht eine PV-Anlage aus einer Vielzahl an einzelnen Solarmodulen und dem Wechselrichter (ggfs. auch mehreren Wechserichtern). Dazwischen verläuft eine Gleichstrom-verkabelung. Nach dem Wechselrichter erfolgt i.d.R. der wechselstrommäßige Anschluss an das Energieverteilnetz. 

Als Minimum kann in der Simulation die Betrachtung der Solarmodule und des Wechselrichters erfolgen. Weitere Modelle können beispielsweise Verluste der Verkabelung oder Fehlanpassungen zwischen den Komponenten und / oder dem Energienetz nachbilden. 


# Ressourcen:
- Arizona State University: https://www.pveducation.org/pvcdrom/welcome-to-pvcdrom 
