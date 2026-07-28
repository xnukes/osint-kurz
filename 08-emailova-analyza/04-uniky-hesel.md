# 8.3 Úniky hesel

> **Cíle kapitoly:**
>
> - Porozumět databázovým únikům hesel
> - Umět zkontrolovat, zda byl e-mail v úniku
> - Znát nástroje pro vyhledávání v uniklých datech
> - Umět postupovat při nálezu uniklých dat

---

## Teorie

### Co jsou úniky hesel

Únik hesel (credential leak) nastává, když útočník získá databázi uživatelů a hesel z nějaké služby.

```mermaid
graph TD
    A[Únik databáze] --> B[Slabé zabezpečení]
    A --> C[Útok na službu]
    A --> D[Insider hrozba]
    
    B --> E[Uniklá data]
    C --> E
    D --> E
    
    E --> F[E-maily]
    E --> G[Hesla (hash/plaintext)]
    E --> H[IP adresy]
    E --> I[Další osobní data]
```

### Největší úniky

| Rok | Služba | Počet účtů |
|---|---|---|
| 2013 | Adobe | 153 miliónů |
| 2016 | LinkedIn | 700 miliónů |
| 2017 | Equifax | 147 miliónů |
| 2018 | Marriott | 500 miliónů |
| 2019 | Collection #1 | 773 miliónů |
| 2021 | Facebook | 533 miliónů |
| 2023 | Twitter | 235 miliónů |

### Nástroje pro kontrolu úniků

| Nástroj | URL | Popis |
|---|---|---|
| **Have I Been Pwned** | haveibeenpwned.com | Nejznámější, hledání podle e-mailu |
| **Firefox Monitor** | monitor.firefox.com | HIBP integrace |
| **DeHashed** | dehashed.com | Placený, detailnější |
| **IntelX** | intelx.io | Multi-zdrojové vyhledávání |
| **Snusbase** | snusbase.com | Databáze úniků |
| **LeakCheck** | leakcheck.io | Placený |

---

## Postup krok za krokem: Kontrola úniků

### 1. Have I Been Pwned

```bash
# Web
https://haveibeenpwned.com/account/email@example.com

# API
curl https://haveibeenpwned.com/api/v3/breachedaccount/email@example.com
```

### 2. DeHashed

```bash
# Web
https://dehashed.com/search?query=email@example.com

# Výsledky:
# - Které služby unikly
# - Jaká data unikla (hash hesla, IP, ...)
# - Datum úniku
```

### 3. Analýza výsledků

```bash
# Které služby unikly?
# Jaká hesla byla kompromitována?
# Jsou hesla stále používána?
# Je třeba změnit hesla?
```

---

## Reálné příklady

### Příklad 1: Kontrola e-mailu

```bash
$ haveibeenpwned.com/account/jan.novak@gmail.com
# Výsledek:
# LinkedIn (2021) - 700M únik
# Adobe (2013) - 153M únik
# Twitter (2023) - 235M únik
```

**Akce:** Změnit hesla na LinkedIn, Adobe, Twitter a všech službách se stejným heslem.

### Příklad 2: Hledání podle hesla

```bash
# DeHashed hledání podle hash hesla
# (eticky, jen vlastní hesla)
# Zjistit, zda bylo heslo uniknuto
```

---

## Tipy a časté chyby

> [!TIP]
> Pravidelně kontrolujte své e-maily na HIBP. Nastavte notifikace pro nové úniky.

> [!WARNING]
> **Častá chyba:** Používání stejného hesla napříč službami. Jeden únik = kompromitace všech účtů.

> [!WARNING]
> **Častá chyba:** Slepá důvěra nástrojům. Některé "leak check" služby mohou být podvodné — sbírají e-maily a hesla.

---

## Praktické cvičení

**Úkol 1:** Kontrola úniků:
1. Zkontrolujte svůj e-mail na haveibeenpwned.com
2. Zkontrolujte na dehashed.com (pokud máte účet)
3. Které služby unikly?
4. Kdy k únikům došlo?

**Úkol 2:** Bezpečnostní audit:
1. Pro každý uniklý účet změňte heslo
2. Aktivujte 2FA
3. Zkontrolujte, zda nepoužíváte stejné heslo jinde

**Pomůcky:** haveibeenpwned.com, dehashed.com
**Očekávaný výstup:** Seznam uniklých účtů + bezpečnostní opatření

---

## Shrnutí

- Úniky hesel jsou běžné — stovky miliónů účtů unikly
- HIBP je standardní nástroj pro kontrolu
- DeHashed poskytuje detailnější informace
- Uniklé heslo změnit VŠUDE, kde bylo použito
- Pravidelně kontrolovat a používat unikátní hesla

---

## Kontrolní otázky

1. Jak zkontrolujete, zda váš e-mail unikl?
2. Proč je nebezpečné používat stejné heslo?
3. Jaké jsou největší úniky v historii?
4. Jaká data kromě hesla mohou uniknout?
5. Jaký je postup po zjištění úniku?

---

## Zdroje a odkazy

- [Have I Been Pwned](https://haveibeenpwned.com)
- [DeHashed](https://dehashed.com)
- [Firefox Monitor](https://monitor.firefox.com)
- [IntelX](https://intelx.io)
