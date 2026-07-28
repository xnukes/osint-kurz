# 7.5 LinkedIn

> **Cíle kapitoly:**
>
> - Umět analyzovat LinkedIn profily
> - Znát techniky pro firemní OSINT na LinkedIn
> - Umět mapovat organizační struktury
> - Znát limity LinkedIn OSINT

---

## Teorie

### LinkedIn jako OSINT zdroj

LinkedIn je profesní síť s detailními informacemi o pracovních zkušenostech, vzdělání a kariérním postupu.

```mermaid
graph TD
    A[LinkedIn profil] --> B[Pracovní historie]
    A --> C[Vzdělání]
    A --> D[Dovednosti]
    A --> E[Doporučení]
    A --> F[Síť kontaktů]
    A --> G[Zájmové stránky]
    
    B --> Firma 1
    B --> Firma 2
    B --> Pozice
    B --> Období
    B --> Popis práce
    
    C --> Škola
    C --> Obor
    C --> Rok
```

### Veřejné vs soukromé informace

| Informace | Veřejná | Omezení |
|---|---|---|
| Jméno | Ano | — |
| Profilová fotka | Ano | — |
| Současná pozice | Ano | — |
| Současná firma | Ano | — |
| Pracovní historie | Ano | Může být omezena |
| Vzdělání | Ano | Může být omezeno |
| Dovednosti | Ano | — |
| Doporučení | Ano | — |
| Kontakty | Ne, jen společný | Pouze 3. stupeň |
| E-mail/Telefon | Ne | Skryto |

### Nástroje pro LinkedIn OSINT

| Nástroj | Účel |
|---|---|
| **LinkedIn Search** | Základní vyhledávání |
| **Sales Navigator** | Pokročilé vyhledávání (placené) |
| **LinkedIn API** | Programový přístup |
| **Scraping** (opatrně) | Automatizovaný sběr |
| **TheHarvester** | OSINT nástroj s LinkedIn modulem |

---

## Postup krok za krokem: Analýza profilu

### 1. Vyhledání profilu

```bash
# LinkedIn vyhledávání
linkedin.com/search/results/people/?keywords=Jméno+Firma

# Google dork
site:linkedin.com/in "Jméno Příjmení" "Firma"
```

### 2. Analýza profilu

```bash
# Profilová fotka
# Současná a minulá zaměstnání
# Vzdělání
# Dovednosti s potvrzením
# Doporučení (kdo doporučil?)
```

### 3. Firemní stránka

```bash
# LinkedIn company page
# Počet zaměstnanců
# Podobné firmy
# Lidé, kteří pracují ve firmě
```

### 4. Síťová analýza

```bash
# Společné kontakty
# Lidé se stejnou firmou/školou
# Groups
```

---

## Reálné příklady

### Příklad 1: Ověření zaměstnání

**Cíl:** Ověřit, zda osoba skutečně pracuje v uvedené firmě

**Postup:**
1. Zkontrolovat LinkedIn profil
2. Ověřit datum nástupu
3. Zkontrolovat doporučení od kolegů
4. Ověřit u kolegů z téže firmy

### Příklad 2: Due diligence

**Cíl:** Prověřit firmu a její vedení

**Postup:**
1. Firemní LinkedIn stránka — velikost, zaměření
2. Profily vedení — kariérní historie, vzdělání
3. Společné kontakty s jinými firmami
4. Doporučení a hodnocení

---

## Tipy a časté chyby

> [!TIP]
> LinkedIn Sales Navigator umožňuje pokročilé filtry (lokalita, firma, pozice, škola). Pro seriózní OSINT se vyplatí.

> [!WARNING]
> **Častá chyba:** Scrapování LinkedIn je proti jejich podmínkám. Může vést k blokaci účtu.

> [!WARNING]
> **Častá chyba:** LinkedIn profily mohou být neaktuální. Vždy ověřovat aktuálnost informací.

---

## Praktické cvičení

**Úkol 1:** Analyzujte profil:
1. Najděte LinkedIn profil manažera české firmy
2. Zjistěte: pracovní historie, vzdělání, dovednosti
3. Zkontrolujte doporučení
4. Ověřte pracovní historii firmu po firmě

**Úkol 2:** Firemní analýza:
1. Najděte LinkedIn stránku firmy
2. Zjistěte: počet zaměstnanců, podobné firmy
3. Najděte 3 zaměstnance a zkontrolujte jejich profily

**Pomůcky:** LinkedIn, Google
**Očekávaný výstup:** Profilová + firemní analýza

---

## Shrnutí

- LinkedIn je nejlepší zdroj pro profesní OSINT
- Pracovní historie a vzdělání jsou obvykle veřejné
- Firemní stránky odhalují velikost a strukturu
- Sales Navigator poskytuje pokročilé vyhledávání
- Scrapování je proti podmínkám

---

## Kontrolní otázky

1. Jaké informace jsou na LinkedIn veřejné?
2. Jak ověříte, že osoba pracuje v uvedené firmě?
3. K čemu slouží Sales Navigator?
4. Proč není scrapování LinkedIn doporučeno?
5. Jak můžete mapovat organizační strukturu?

---

## Zdroje a odkazy

- [LinkedIn](https://www.linkedin.com)
- [Sales Navigator](https://business.linkedin.com/sales-solutions)
- [TheHarvester](https://github.com/laramies/theHarvester)
