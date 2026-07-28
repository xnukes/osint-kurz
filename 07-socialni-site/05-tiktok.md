# 7.4 TikTok

> **Cíle kapitoly:**
>
> - Umět analyzovat TikTok profily a obsah
> - Znát specifika TikToku pro OSINT
> - Umět extrahovat metadata z TikTok videí
> - Znát nástroje pro TikTok OSINT

---

## Teorie

### TikTok jako OSINT zdroj

TikTok je video platforma s rychle rostoucím významem pro OSINT, zejména díky své popularitě u mladší generace.

```mermaid
graph TD
    A[TikTok profil] --> B[Videa]
    A --> C[Bio]
    A --> D[Sledující/sledovaní]
    A --> E[Líbí se mi]
    
    B --> B1[Video obsah]
    B --> B2[Popis]
    B --> B3[Hashtagy]
    B --> B4[Zvuk]
    B --> B5[Lokace (volitelně)]
    B --> B6[Duety/Stitch]
    
    D --> S1[Síť]
    E --> Z1[Zájmy]
```

### Veřejné informace na TikTok

| Informace | Dostupnost |
|---|---|
| Uživatelské jméno | Ano |
| Bio | Ano |
| Počet videí | Ano |
| Počet sledujících | Ano |
| Sledovaní | Ne (pouze počet) |
| Seznam videí | Ano (veřejný profil) |
| Líbí se mi | Volitelné |
| Komentáře | Ano |
| Lokace | Volitelné |

### Nástroje pro TikTok OSINT

| Nástroj | Účel |
|---|---|
| **TikTok Web** | Základní prohlížení |
| **TikStats** | Analýza profilu |
| **TokCount** | Statistiky |
| **TikTok API (neoficiální)** | Programový přístup |
| **Urlebird** | Online viewer |

---

## Postup krok za krokem: Analýza TikTok

### 1. Profilová analýza

```bash
# Webové rozhraní
tiktok.com/@username

# Bio, odkaz v bio, počet videí
# Počet sledujících, sledovaných
# Popis videa v profilu
```

### 2. Analýza videí

```bash
# Stažení videa pro metadata
# TikTok videa mají metadata: datum nahrání, zvuk, hashtagy

# Geolokace (pokud přidána)
# Pozadí videa — vizuální analýza
```

### 3. Zvuková analýza

```bash
# TikTok používá populární zvuky
# Lze dohledat další videa se stejným zvukem
# Odhaluje komunity a trendy
```

---

## Reálné příklady

### Příklad 1: Geolokace z videa

**Cíl:** Určit místo nahrání TikTok videa

**Postup:**
1. Vizuální analýza pozadí (budovy, příroda)
2. Pokud je přidána lokace → přímo
3. Analýza počasí/denní doby
4. Identifikace unikátních prvků (billboardy, loga)

### Příklad 2: Analýza sítě

**Cíl:** Identifikovat komunity cíle

**Postup:**
1. Sledovat, které účaty cíl sleduje
2. Analyzovat hashtagy v popiscích
3. Zkontrolovat duety a stitche
4. Identifikovat vzorce v obsahu

---

## Tipy a časté chyby

> [!TIP]
> TikTok videa často obsahují vizuální informace o lokaci v pozadí. Věnujte pozornost detailům: billboardy, názvy obchodů, SPZ.

> [!WARNING]
> **Častá chyba:** TikTok API je neoficiální a nestabilní. Spoléhejte hlavně na webové rozhraní.

> [!WARNING]
> **Častá chyba:** TikTok má přísnou ochranu soukromí — profilová fotka a bio jsou veřejné, ale mnoho dat je skryto.

---

## Praktické cvičení

**Úkol 1:** Analyzujte TikTok profil:
1. Najděte veřejný TikTok profil
2. Zjistěte: bio, počet videí, sledující
3. Analyzujte 5 videí: hashtagy, zvuk, obsah

**Úkol 2:** Geolokace videa:
1. Najděte TikTok video s rozpoznatelným místem
2. Identifikujte lokaci podle vizuálních prvků
3. Ověřte na Google Maps

**Pomůcky:** TikTok web, Google Maps
**Očekávaný výstup:** Profilová analýza + geolokace videa

---

## Shrnutí

- TikTok je rostoucí OSINT zdroj pro video obsah
- Profil, bio a sledující jsou veřejné
- Videa obsahují hashtagy, zvuk a někdy lokace
- Vizuální analýza pozadí je klíčová pro geolokaci
- API je omezené a nestabilní

---

## Kontrolní otázky

1. Jaké informace jsou na TikTok veřejné?
2. Jak můžete určit lokaci TikTok videa?
3. K čemu slouží hashtagy na TikTok?
4. Jaký je limit TikTok pro OSINT?
5. Co prozrazuje zvuk v TikTok videu?

---

## Zdroje a odkazy

- [TikTok Web](https://www.tiktok.com)
- [Urlebird](https://urlebird.com)
- [TikStats](https://tikstats.com)
- [TokCount](https://tokcount.com)
