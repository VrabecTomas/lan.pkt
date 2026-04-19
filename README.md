# Konfigurace LAN sítě v Cisco Packet Tracer

Tento úkol demonstruje nastavení lokální počítačové sítě (LAN) s využitím služeb DNS, HTTP a DHCP. Konfigurace byla provedena v programu Cisco Packet Tracer.

## Hlavní součásti sítě
* **Switch (S1):** Centrální prvek sítě, konfigurovaný přes konzolový kabel.
* **SRV1:** Plní roli DNS serveru a DHCP serveru.
* **SRV2:** Plní roli webového (HTTP) serveru.
* **Koncová zařízení:** PC1 (statická IP), PC2 (dynamická IP přes DHCP) a Laptop (správa).

## Provedená konfigurace

### Hlavní přehled
* SRV1 (DNS & DHCP): * Nastavení DNS záznamu pro doménu vrabec.cz směřující na webový server.

Konfigurace DHCP poolu pro automatické přidělování IP adres v síti.

SRV2 (HTTP): Nastavení webového serveru a úprava index.html.

PC1: Ruční nastavení IP a ověření funkčnosti pomocí ping a webového prohlížeče.

PC2: Ověření funkčnosti DHCP (automatické získání adresy).

Obsah odevzdání:

lan.pkt – soubor s projektem Packet Tracer.

screenshots/ – složka s důkazy funkčnosti (Terminal, DNS, Web, Ping, DHCP).


```bash
Switch>enable
Switch#configure terminal
Switch(config)#hostname S1
Switch (S1): Konfigurace hostname přes konzolový kabel z Laptopu.
