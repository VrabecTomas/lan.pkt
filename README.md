# Konfigurace LAN sítě v Cisco Packet Tracer

Tento projekt demonstruje nastavení lokální počítačové sítě (LAN) s využitím služeb DNS, HTTP a DHCP. Konfigurace byla provedena v programu Cisco Packet Tracer.

## Hlavní součásti sítě
* **Switch (S1):** Centrální prvek sítě, konfigurovaný přes konzolový kabel.
* **SRV1:** Plní roli DNS serveru a DHCP serveru.
* **SRV2:** Plní roli webového (HTTP) serveru.
* **Koncová zařízení:** PC1 (statická IP), PC2 (dynamická IP přes DHCP) a Laptop (správa).

## Provedená konfigurace

### 1. Správa Switche (Terminal)
Pomocí Laptopu připojeného přes konzolový kabel (RS232 -> Console) byl nastaven název switche:
```bash
Switch>enable
Switch#configure terminal
Switch(config)#hostname S1
