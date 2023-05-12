# Modellierung

Bevor ein Penetrationstest gestartet wird, ist eine korrekte Modellierung notwendig. Diese gibt den Rahmen vor, an den sich die Tester halten und entspricht den Wünschen der Kunden. Die Modellierung eines OT-Penetrationstests umfasst die Identifizierung der Informationsbasis, die Aggressivität des Tests, die Zugangsmöglichkeiten und die Testkanäle, die verwendet werden sollen.


<img src="../img/modellierung.png" style="display: block; margin-left: auto; margin-right: auto;">


## 1. Informationsbasis

Die Informationsbasis bezieht sich auf alle verfügbaren Informationen über das zu testende System, einschließlich seiner Architektur, Betriebssysteme, Netzwerkstruktur, Anwendungen, Benutzer und Daten. Eine gründliche Informationsbasis ermöglicht es dem Penetrationstester, gezielte Angriffe auf Schwachstellen durchzuführen. Bei einem Black-Box-Penetrationstest gibt es nahezu keine Informationen und bei einem White-Box-Test sind umfangreiche Informationen zur Verfügung gestellt. Ein Grey-Box Test liegt dazwischen.


## 2. Aggressivität

Die Aggressivität des Tests bezieht sich auf den Grad der Intensität, mit der der Pentester vorgehen soll. Ein hoher Grad der Aggressivität kann schnellere und umfassendere Ergebnisse liefern, aber auch das Risiko von Schäden und Ausfällen erhöhen. Eine geringere Aggressivität kann das Risiko von Schäden verringern, aber auch die Entdeckung von Schwachstellen verlangsamen.

Die Aggressivitätsstufen beim Pentesting variieren von Passiv, Vorsichtig, Abwägend bis hin zu Aggressiv. Bei der passiven Stufe geht der Penetrationstester sehr vorsichtig vor und hinterlässt so wenig Spuren wie möglich, während bei der vorsichtigen Stufe etwas mehr Druck ausgeübt wird, jedoch weiterhin vorsichtig, sodass Schäden vermieden werden. Bei der abwägenden Stufe wird ein höheres Maß an Risiko eingegangen, um Schwachstellen zu identifizieren. In seltenen Fällen kann es zu unvorhergesehenen Auswirkungen auf das zu testende System führen. Bei der aggressiven Stufe wird ein hohes Maß an Risiko eingegangen und teilweise schädliche Angriffe durchgeführt, um maximale Ergebnisse zu erzielen. Die Wahl der Aggressivitätsstufe hängt von verschiedenen Faktoren ab, wie der Art des zu testenden Systems, der Sensibilität der Daten und der Toleranz des Kunden gegenüber möglichen Auswirkungen auf das System.

## 3. Zugang

Die Zugangsmöglichkeiten beziehen sich auf die Art und Weise, wie der Pentester Zugang zum System erhält. Dabei wird zwischen einem Innen- und einem Außentäter unterschieden, der entweder von außerhalb (Internet-Angreifermodell) oder innerhalb des Unternehmens oder des Netzwerks agiert. Bei einem Penetrationstest von innen müssen üblicherweise keine Zugangskontrollen überwunden werden, um Zugang zu den Geräten zu erhalten. Bei einem Penetrationstest von außen müssen üblicherweise Zugangskontrollen, wie Firewalls oder Gebäudeschließeinrichtungen überwunden werden.

## 4. Testkanäle

Die Testkanäle beziehen sich auf die Art und Weise, wie der Penetrationstester Angriffe durchführt. Die Testkanäle können Netzwerk-, Bus-, Firmware- und physische Tests umfassen. Netzwerktests überprüfen Netzwerkprotokolle und -kommunikation, Bus-Tests evaluieren die Kommunikation zwischen Komponenten, Firmware-Tests suchen nach Schwachstellen in Firmware, und physische Tests decken Schwachstellen durch physischen Zugang auf.