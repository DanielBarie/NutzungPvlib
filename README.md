# Nutzung Pvlib
Ideen zur Nutzung von pvLib zwecks Simulation deutscher PV-Anlagen. In diesem Dokument werden zahlreiche Begriffe "einfach so" benutzt, ohne auf das für das Verständnis ggfs. erforderliche Studium der Grundlagen einzugehen. Hierzu empfiehlt sich beispielsweise die Lektüre der im Abschnitt Ressourcen aufgeführten Dokumente.

# Motivation
Eine PV-Anlage soll Strahlungsenergie der Sonne in elektrische Energie umwandeln. Solche Anlagen sind komplexe Systeme und bestehen aus vielen einzelnen Komponenten. Das Verhalten der Komponenten muss einzeln und im Zusammenspiel betrachtet werden. Aufrund der Komplexität erfolgt vor dem Aufbau einer PV-Anlage regelmäßig eine Simulation, welche datenbasierte Modelle für die Komponenten erfordert. Dazu sind umfangreiche Daten zu Solarmodulen und Wechselrichtern sowie Wetterdaten notwendig

Zum einen können für die Simulation kommerzielle, nicht frei zu nutzende Programme verwendet werden. Diese pflegen umfangreiche Datenbanken mit Datensätzen für Wechselrichter und Solarmodule und haben verschiedene Berechnungsmodelle integriert. Aus den Datensätzen der Datenbanken werden für die Simulation erforderliche Parameter der Modelle gespeist. Beispiele für derartige Programme sind:
- PVsyst (Schweizer Programm), Lizenz für 600 CHF pro Jahr (https://www.pvsyst.com/shop-prices/)
- PV\*SOL (deutsches Programm), Lizenz einmalig 850 Euro plus Wartungsgebühr von 160€/Jahr (https://valentin-software.com/produkte/pvsol/)  

Andere Simulationsprogramme sind von spezifischen Herstellern (z.B. SolarEdge) und damit auf Komponenten jener festgelegt. 

Frei verfügbare Tools (z.B. Solar-Planit, www.solar-planit.de) sind oftmals auf die beim jeweiligen Unternehmen lieferbaren Komponenten und bezüglich der universellen Verwendbarkeit eingeschränkt.

Eines der wenigen, frei verfügbaren Simulationstools mit großem Funktionsumfang und wissenschaftlich fundiertem Hintergrund ist pvLib. Ursprünglich als Toolbox für Matlab entstanden, bietet sich jetzt auch die Nutzung mit Python an: https://pvpmc.sandia.gov/applications/pv_lib-toolbox/

# Probleme
pvLib ist ein Projekt aus dem Dunstkreis des US-DoE (Department of Energy der Vereinigten Staaten von Amerika). Die im Programm mitgelieferten Daten für die Wechselrichtern und Solarmodulen zu Grunde liegenden Modelle stammen aus SAM (System Advisor Model), einem Projekt des US-amerikanischen National Renewable Energy Laboratory) (https://sam.nrel.gov/). Daher sind die im Programm verfügbaren Typen (und damit Modelltaten) von Wechselrichtern und Solarmodulen stark auf den amerikanischen Markt ausgelegt.

Regelmäßig sind die über SAM verfügbaren Daten neuer als diejenigen, welche in pvLib mitgelieferten werden (mehr/aktuellere Module und Wechselrichter). 

Als alternative Datenquelle für pvLib steht mit pvfree eine Online-Datenbank zur Verfügung (https://pvfree.azurewebsites.net), die dort verfügbaren Daten sind jedoch mit wenigen Ausnahmen identisch mit denjenigen aus SAM.

Es fehlt also an einfach nutzbaren Daten für pvLib im deutschen/europäischen Kontext.

# Modelle pvLib
Die Simulation komplexer Syteme arbeitet mit Modellen der einzelnen Systemkomponenten; diese wiederum werden im Zusammenspiel betrachtet. Regelmäßig besteht eine PV-Anlage aus einer Vielzahl an einzelnen Solarmodulen und dem Wechselrichter (ggfs. auch mehreren Wechserichtern). Dazwischen verläuft eine Gleichstrom-Verkabelung. Nach dem Wechselrichter erfolgt i.d.R. der wechselstrommäßige Anschluss an das Energieverteilnetz. 

Als Minimum kann in der Simulation die Betrachtung der Solarmodule und des Wechselrichters erfolgen. Weitere Modelle können beispielsweise Verluste der Verkabelung oder Fehlanpassungen zwischen den Komponenten und / oder dem Energienetz nachbilden. 

Die einzelnen Solarmodule wiederum bestehen aus einer Vielzahl von Solarzellen. Daher werden die Solarmodule für die Simulation wiederum in einzelne Zellen zerlegt. Dieser Schritt erfordert ein Modell für die Solarzellen, die im Grunde nichts weiter als Halbleiterdioden sind. 

# Ressourcen:
- Arizona State University; https://www.pveducation.org/pvcdrom/welcome-to-pvcdrom 
- Sandia Labs; Report Nr. 3535, Photovoltaic Array Performance Model; https://energy.sandia.gov/wp-content/gallery/uploads/SAND-2004_PV-Performance-Array-Model.pdf
- NREL; Comparison of Photovoltaic Models in the System Advisor Model; https://www.nrel.gov/docs/fy13osti/58057.pdf
- AssessingSolar.org; https://assessingsolar.org/intro.html
