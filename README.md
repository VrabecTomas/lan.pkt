# Projekt: Konfigurace LAN sítě v Cisco Packet Tracer

Tento repozitář obsahuje konfiguraci lokální sítě (LAN) zaměřenou na služby DNS, HTTP a DHCP. Součástí je i dokumentace nastavení a ověření funkčnosti.

## Obsah odevzdání
* `lan.pkt` – Zdrojový soubor projektu pro Cisco Packet Tracer.
* `README.md` – Popis sítě, technické výpočty a dokumentace.
* `/screenshots` – Složka se snímky obrazovky potvrzujícími funkčnost.

---

## 1. Popis sítě
V rámci projektu byla vytvořena hvězdicová topologie s následujícími prvky:
* **Switch (S1):** Centrální propojovací prvek, pojmenován skrze konzolové připojení z Laptopu.
* **SRV1 (DNS & DHCP):** Server zajišťující překlad doménových jmen a automatické přidělování IP adres.
* **SRV2 (HTTP):** Webový server hostující stránku `vrabec.cz`.
* **PC1:** Koncová stanice se staticky nastavenou adresou pro testování dostupnosti.
* **PC2:** Koncová stanice využívající protokol DHCP pro získání síťové konfigurace.

---

## 2. Výpočet proměnné X (Síťové parametry)
Pro tento projekt byla zvolena hodnota **X = 179**.

**Technické parametry sítě:**
* **Adresa sítě:** `192.168.179.0`
* **Maska podsítě:** `255.255.255.0` (Prefix `/24`)
* **Výchozí brána (Default Gateway):** `192.168.179.1`
* **Broadcast adresa:** `192.168.179.255`

**Logický výpočet:**
Maska `/24` (binárně 24 jedniček) určuje, že první tři oktety (`192.168.179`) patří síti. Poslední oktet je vyhrazen pro hosty.
* Počet využitelných adres: $2^{(32 - 24)} - 2 = 254$.
* Rozsah adres pro hosty: `192.168.179.1` až `192.168.179.254`.

---

## 3. Snímky obrazovky (Důkazy funkčnosti)

V repozitáři (složka `screenshots`) jsou doloženy tyto kroky:

1.  **Terminal (S1):** Konfigurace `hostname S1` přes konzoli Laptopu.
2.  **DNS Config:** Nastavení záznamu typu A pro doménu `vrabec.cz` na SRV1.
3.  **Web Browser:** Úspěšné načtení obsahu webu `http://vrabec.cz` na PC1.
4.  **Ping Test:** Ověření konektivity a překladu jména příkazem `ping vrabec.cz`.
5.  **DHCP Success:** Potvrzení o úspěšném automatickém přidělení IP adresy na PC2.

---

## 4. Konfigurace služeb v kostce
| Služba | Parametry |
| :--- | :--- |
| **DNS** | `vrabec.cz` -> `192.168.179.11` |
| **DHCP Pool** | `192.168.179.100` - `192.168.179.150` |
| **HTTP** | Úprava `index.html` na SRV2 |
