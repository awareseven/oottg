# Katalog Bus

_Die BUS-Kommunikation kann ein potenzielles Ziel für Angriffe in OT-Umgebungen sein. BUS-Kommunikation bezieht sich auf die Übertragung von Daten zwischen Geräten oder Komponenten über einen gemeinsamen Kommunikationspfad. Übliche Beispiele für BUS-Kommunikationsprotokolle in OT-Systemen sind Modbus, Profibus, CAN (Controller Area Network). Es ist erwähnenswert, dass Ethernet zwar typischerweise mit lokalen Netzwerken (LANs) in Verbindung gebracht wird und nicht als BUS im engeren Sinne betrachtet wird, aber in OT-Umgebungen für die Kommunikation zwischen Geräten weit verbreitet ist. Ethernet-basierte Protokolle wie EtherNet/IP, PROFINET und Modbus TCP werden häufig in der Industrieautomatisierung eingesetzt und sollten auch im OT-Pentesting nicht vergessen werden._

| Test-Modul | Modulbeschreibung | Test-Durchführung|  Externer Angriff möglich? | Aggressivität | Externe Quellen |
|------------|-------------------|-------------------|---------------------------|---------------|-----------------|
|**B.1** - Eavesdropping| Wenn die BUS-Kommunikation nicht ausreichend gesichert oder verschlüsselt ist, kann ein Angreifer mit Zugang zur Netzinfrastruktur die Kommunikation abfangen oder abhören. Dadurch können möglicherweise sensible Informationen wie Steuerbefehle oder Sensormesswerte offengelegt werden, was zu unbefugtem Zugriff oder Datenmanipulation führen kann.|Es werden mögliche Zugänge auf den BUS überprüft. Es wird sichergestellt, dass sensible Informationen nur verschlüsselt übertragen werden|Nein|Passiv|[Paper: Bus Probing Angriff](https://www.researchgate.net/publication/328353143_Probing_Attacks_on_Physical_Layer_Key_Agreement_for_Automotive_Controller_Area_Networks_Extended_Version)|
|**B.2** - Man-in-the-Middle Attacke|Ein Angreifer könnte sich zwischen den über den BUS kommunizierenden Geräten positionieren und die übertragenen Daten abfangen oder verändern. Indem er sich in den Kommunikationspfad einschleust, kann er die Daten manipulieren, bösartige Befehle einschleusen oder die Integrität der Kommunikation verfälschen.|Es wird überprüft, dass die Integrität und Authentizität der Nachrichten sichergestellt wird|Nein|Abwägend|[Automotive MitM](https://www.hackster.io/news/emile-nijssen-s-open-source-can-bridge-makes-automotive-man-in-the-middle-a-cinch-b4dfeb952b04) <br> [Paper: MitM für PCI CAN Bus](https://www.sciencedirect.com/science/article/abs/pii/S0141933120303653)|
|**B.3** - Replay Attacke|Bei einem Replay-Angriff fängt ein Angreifer einen legitimen Kommunikationsaustausch zwischen Geräten über das BUS ab und spielt ihn erneut ab. Dies kann besonders effektiv sein, wenn die Kommunikation nicht über angemessene Authentifizierungs- oder Timestampmechanismen verfügt. Durch die erneute Wiedergabe der aufgezeichneten Nachrichten kann der Angreifer möglicherweise unbefugte Aktionen durchführen oder das Systemverhalten manipulieren.|Es wird überprüft, ob Timestamps oder ähnliche Validierungsmaßnahmen implementiert wurden|Nein|Abwägend|[Paper: Implementation of Replay Attack in Controller Area Network Bus using Universal Verification Methodology](https://www.researchgate.net/publication/350935778_Implementation_of_Replay_Attack_in_Controller_Area_Network_Bus_using_Universal_Verification_Methodology)|
|**B.4** - Denial of Service (Dos) Attacke|Die BUS-Kommunikation kann ein Ziel für DoS-Angriffe sein, bei denen ein Angreifer den BUS mit übermäßigem oder bösartigem Datenverkehr überflutet und so eine Unterbrechung oder Beeinträchtigung der Kommunikation verursacht. Indem er den BUS oder die damit verbundenen Geräte überlastet, kann der Angreifer kritische Abläufe stören, was zu Systemausfällen oder -störungen führt.|Es wird überprüft ob ein DoS Angriff erkannt und gemeldet bzw. abgewehrt wird. Dabei werden Funktionen mit erhöhtem Zeit- und Rechenaufwand besonders in den Fokus genommen.|Nein|Aggressiv|[Paper: Practical Modbus Flooding Attack and Detection](https://www.semanticscholar.org/paper/Practical-Modbus-Flooding-Attack-and-Detection-Bhatia-Kush/59190c574ab49c10069080239119e428fdb17c9f)|
|**B.5** - Bus Device Spoofing|Ein Angreifer kann versuchen, sich als ein legitimes Gerät auf dem BUS auszugeben, indem er dessen Identität fälscht oder klont. Auf diese Weise kann er sich unbefugten Zugriff auf den BUS verschaffen und möglicherweise die Kommunikation zwischen den Geräten manipulieren oder stören.|Es wird überprüft, ob die Authentizität der Kommunikationsparteien sichergestellt wird. |Nein|Abwägend|[Paper: Spoofing attack using bus-off attacks against a specific ECU of the CAN bus](https://www.researchgate.net/publication/323863962_Spoofing_attack_using_bus-off_attacks_against_a_specific_ECU_of_the_CAN_bus)|

## Weitere Quellen

### Tools

- [**CANtact**](https://github.com/linklayer/cantact): CANtact ist ein Hardware-Tool für die Interaktion mit CAN-Netzwerken. Es bietet eine USB-Schnittstelle für den Anschluss an CAN-Busse und ermöglicht die Überwachung, Analyse und Injektion von CAN-Nachrichten. Zusammen mit geeigneten Software-Frameworks wie SocketCAN oder CANalyzat0r ermöglicht CANtact die Interaktion mit CAN-Netzwerken zum Testen, Analysieren oder potenziellen Manipulieren der Kommunikation.

  
- [**Wireshark**](https://www.wireshark.org/): Wireshark ist ein beliebtes Open-Source-Netzwerkprotokoll-Analyseprogramm. Es ermöglicht Ihnen, den Netzwerkverkehr zu erfassen und zu analysieren, einschließlich der über verschiedene BUS-Protokolle übertragenen Daten. Wireshark kann verwendet werden, um die auf dem BUS ausgetauschten Pakete zu untersuchen und so Schwachstellen zu identifizieren, Kommunikationsmuster zu analysieren oder Anomalien zu erkennen.
    

- [**QModBus**](https://github.com/ed-chemnitz/qmodbus): QModBus ist ein spezielles Tool zum Testen und Simulieren der Modbus-Kommunikation. Es ermöglicht das Scannen und Auslesen von Modbus-Geräten, das Lesen von Registern, das Schreiben von Werten und die Überwachung der Modbus-Kommunikation auf dem BUS.

- [**Scapy**](https://scapy.net/): Scapy ist ein leistungsfähiges Python-basiertes Werkzeug zur Paketmanipulation. Es bietet ein flexibles und interaktives Framework zum Erstellen und Senden von Netzwerkpaketen. Mit Scapy können benutzerdefinierte Pakete erstellt werden, einschließlich missgebildeter oder unerwarteter Pakete, die in die BUS-Kommunikation eingespeist werden können, um Fuzzing- oder Injektionsangriffe durchzuführen.

### Webseiten
- [CAN BUS Hacking](https://mk4-wiki.denkdose.de/artikel/can-bus/hacking/start)

- [CAN BUS Hacking im Bereich Automotive](https://medium.com/@yogeshojha/car-hacking-101-practical-guide-to-exploiting-can-bus-using-instrument-cluster-simulator-part-i-cd88d3eb4a53)

### Paper
- [A Survey on CAN Bus Protocol: Attacks,
Challenges, and Potential Solutions](https://files.core.ac.uk/pdf/23/287585022.pdf)

- [Secure communication in microcomputer bus systems for embedded devices](https://www.sciencedirect.com/science/article/abs/pii/S1383762108000611)
  
- [Detection and Blocking of Replay, False Command, and False Access Injection Commands in SCADA Systems with Modbus Protocol](https://www.researchgate.net/publication/354886985_Detection_and_Blocking_of_Replay_False_Command_and_False_Access_Injection_Commands_in_SCADA_Systems_with_Modbus_Protocol)

- [CAN Bus Security](https://canislabs.com/downloads/2020-02-14-White-Paper-CAN-Security.pdf)