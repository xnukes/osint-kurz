# 7.8 Telegram

> **Cíle kapitoly:**
>
> - Porozumět struktuře Telegramu a jeho OSINT potenciálu
> - Umět analyzovat Telegram kanály a skupiny
> - Znát techniky pro sběr dat z Telegramu
> - Znát nástroje pro Telegram OSINT

---

## Teorie

### Telegram jako OSINT zdroj

Telegram je messaging platforma s důrazem na kanály a skupiny. Veřejné kanály jsou přístupné bez přihlášení.

```mermaid
graph TD
    A[Telegram] --> B[Kanály]
    A --> C[Skupiny]
    A --> D[Uživatelé]
    A --> E[Boti]
    
    B --> B1[Veřejné kanály]
    B --> B2[Soukromé kanály]
    B --> B3[Zprávy]
    B --> B4[Sledující]
    
    C --> C1[Veřejné skupiny]
    C --> C2[Soukromé skupiny]
    
    D --> D1[Jméno + username]
    D --> D2[Profilová fotka]
    D --> D3[Bio]
    D --> D4[Telefon (skrytý)]
```

### Veřejné informace na Telegramu

| Informace | Veřejný kanál | Uživatel |
|---|---|---|
| Název | Ano | — |
| Username | Ano | Ano (volitelně) |
| Popis | Ano | Bio (volitelně) |
| Počet členů | Ano | — |
| Zprávy | Ano (text) | — |
| Média | Ano | Profilová fotka |
| Telefon | Ne | Skrytý |
| Status online | — | Volitelně |

### Nástroje pro Telegram OSINT

| Nástroj | Účel |
|---|---|
| **Telegram Web** | Základní prohlížení |
| **tgscan** | Vyhledávání kanálů |
| **Telegram API** | Programový přístup |
| **Telethon** | Python knihovna pro Telegram |
| **Telegram Stats** | Statistiky kanálů |
| **Combot** | Kanálová analytika |

---

## Postup krok za krokem: Telegram analýza

### 1. Vyhledání kanálu

```bash
# Telegram Web
web.telegram.org

# Vyhledávání kanálů
# @username nebo t.me/username

# Google dork
site:t.me "téma"
```

### 2. Analýza kanálu

```bash
# Název, popis, počet členů
# Datum vytvoření (první zpráva)
# Frekvence příspěvků
# Typ obsahu
# Odkazy v popisu
```

### 3. Sběr zpráv

```bash
# Manuálně
# Screenshot nebo kopírování

# Automaticky
# Telegram API + Telethon
# Export chat history
```

### 4. Metadata zpráv

```bash
# Datum a čas (přesný timestamp)
# Forwarded from?
# Edited?
# Views
```

---

## Reálné příklady

### Příklad 1: Sledování kanálu

**Cíl:** Sledovat aktivitu podezřelého kanálu

**Postup:**
1. Najít kanál (t.me/nazev)
2. Analyzovat popis a obsah
3. Sledovat frekvenci příspěvků
4. Identifikovat správce (podle formátu zpráv)
5. Analyzovat odkazy a média

### Příklad 2: Analýza skupiny

**Cíl:** Zjistit členství cíle

**Postup:**
1. Pokud je cíl ve veřejné skupině
2. Zkontrolovat seznam členů (pokud není skrytý)
3. Analyzovat příspěvky cíle
4. Zkontrolovat profilovou fotku

---

## Tipy a časté chyby

> [!TIP]
> Telegram API umožňuje sběr dat z veřejných kanálů. Telethon je nejlepší Python knihovna pro tento účel.

> [!WARNING]
> **Častá chyba:** Telegram kanály mohou být falešné. Stejný název, ale jiný odkaz (@official vs @officiaI).

> [!WARNING]
> **Častá chyba:** Forwarded zprávy odhalují původní kanál. I když je kanál smazán, forwarded zprávy zůstávají.

---

## Praktické cvičení

**Úkol 1:** Analyzujte Telegram kanál:
1. Najděte veřejný Telegram kanál na libovolné téma
2. Zjistěte: název, popis, počet členů
3. Analyzujte 10 posledních příspěvků
4. Jaká je frekvence příspěvků?

**Úkol 2:** Sběr dat:
1. Pomocí Telethonu (Python) získejte zprávy z veřejného kanálu
2. Zjistěte: datum první zprávy, průměrný počet zpráv/den
3. Exportujte metadata

**Pomůcky:** Telegram Web, Telethon (Python), t.me
**Očekávaný výstup:** Analýza kanálu + data z Telethonu

---

## Shrnutí

- Telegram kanály jsou veřejně čitelné bez přihlášení
- Kanály prozrazují témata, frekvenci a dosah
- Telegram API a Telethon umožňují automatizovaný sběr
- Forwarded zprávy odhalují původní zdroj
- Falešné kanály jsou běžné — ověřovat oficiální zdroj

---

## Kontrolní otázky

1. Jaké informace jsou na Telegram kanálu veřejné?
2. Jak zjistíte datum vytvoření Telegram kanálu?
3. K čemu slouží Telethon?
4. Proč jsou forwarded zprávy důležité pro OSINT?
5. Jak ověříte, že Telegram kanál je oficiální?

---

## Zdroje a odkazy

- [Telegram Web](https://web.telegram.org)
- [Telethon](https://docs.telethon.dev)
- [Telegram API](https://core.telegram.org/api)
- [tgscan](https://tgscan.dev)
