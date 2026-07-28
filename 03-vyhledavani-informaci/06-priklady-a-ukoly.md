# 3.5 Příklady a úkoly

> **Cíle kapitoly:**
>
> - Procvičit si vyhledávací techniky na praktických úlohách
> - Kombinovat operátory a nástroje z předchozích kapitol
> - Získat jistotu v používání pokročilého vyhledávání

---

## Úloha 1: Vyhledání osoby

**Zadání:** Najděte maximální množství informací o fiktivní osobě "Petr Svoboda" z České republiky. Není to reálná osoba — jde o procvičení technik.

**Postup:**

1. Začněte základním vyhledáváním: `"Petr Svoboda"`
2. Zúžte na ČR: `"Petr Svoboda" site:cz`
3. Hledejte na sociálních sítích: `site:linkedin.com "Petr Svoboda"`
4. Hledejte dokumenty: `filetype:pdf "Petr Svoboda"`

**Otázky:**
- Kolik unikátních výsledků jste našli?
- Jaké typy zdrojů převažují (sociální sítě, dokumenty, weby)?
- Dají se některé výsledky propojit?

---

## Úloha 2: Firemní průzkum

**Zadání:** Najděte informace o firmě "Seznam.cz, a.s."

**Techniky:**
1. `site:cz "Seznam.cz" filetype:pdf` — dokumenty
2. `site:or.justice.cz "Seznam.cz"` — obchodní rejstřík
3. `site:linkedin.com "Seznam.cz"` — zaměstnanci
4. `"Seznam.cz" "výroční zpráva"` — finanční data

**Výstup:**
- IČO, sídlo, jednatelé
- Výroční zprávy (tržby, zisk)
- Počet zaměstnanců na LinkedIn
- Veřejné zakázky

---

## Úloha 3: Dork výzva

**Zadání:** Sestavte Google dork dotazy pro:

1. Nalezení souborů `.env` na českých webech
2. Nalezení phpMyAdmin přihlašovacích stránek
3. Nalezení otevřených adresářů (Directory Listing)
4. Nalezení log souborů
5. Nalezení konfiguračních souborů (config.php, config.json)

**Výstup:** Funkční dork dotazy + screenshoty výsledků.

---

## Úloha 4: Archivní výzkum

**Zadání:** Pomocí Wayback Machine a archive.today:

1. Najděte verzi webu idnes.cz z 1. ledna 2010
2. Porovnejte tehdejší titulní stranu s dnešní
3. Najděte článek na téma "OSINT" na Wayback Machine (první snapshot)
4. Archivujte aktuální zpravodajský článek (save page now)

---

## Úloha 5: Mezinárodní vyhledávání

**Zadání:** Použijte alternativní vyhledávače:

1. Najděte na Yandex ruské zdroje o OSINT
2. Najděte na Baidu čínské zdroje (stačí zkusit)
3. Porovnejte výsledky DuckDuckGo vs Google pro stejný dotaz
4. Vyhledejte na Shodan zařízení v Německu s otevřeným portem 3389 (RDP)

---

## Řešení

### Úloha 1 — Indikativní výsledky

```bash
# Základní vyhledávání
"Petr Svoboda" → cca 10 000 výsledků (mnoho různých osob)

# Zúžení
"Petr Svoboda" "IT" "Prague" → mnohem méně

# LinkedIn
site:linkedin.com "Petr Svoboda" → desítky profilů
```

### Úloha 2 — Firemní data

```bash
# Obchodní rejstřík
site:or.justice.cz "Seznam.cz"
# IČO: 26168685

# Veřejné zakázky
site:vestnikverejnychzakazek.cz "Seznam.cz"
```

### Úloha 3 — Dork dotazy

```bash
# .env soubory
filetype:env "DB_PASSWORD" OR "DB_USERNAME" site:cz

# phpMyAdmin
intitle:"phpMyAdmin" "Welcome to phpMyAdmin" site:cz

# Directory Listing
intitle:"index of" "parent directory" site:cz

# Log soubory
filetype:log "error" "warning" site:cz

# Config soubory
filetype:php "config" "database" "password" site:cz
```

---

## Tipy a časté chyby

> [!TIP]
> U každé úlohy si zaznamenávejte postup a použité dotazy. To vám pomůže při opakování a sdílení s kolegy.

> [!WARNING]
> **Častá chyba:** Vzdání se po prvním neúspěšném dotazu. Zkoušejte různé varianty a operátory.

> [!TIP]
> U dlouhých seznamů výsledků použijte Google operátory pro filtrování podle data (Nástroje → Časové období).

---

## Shrnutí

- Procvičování je klíčem k ovládnutí vyhledávacích technik
- Každá úloha vyžaduje kombinaci různých operátorů a nástrojů
- Dokumentace postupu pomáhá při opakování
- Různé vyhledávače dávají různé výsledky — používejte je všechny
- Systematický přístup vede k lepším výsledkům

---

## Zdroje a odkazy

- [Google Dorking Cheat Sheet](https://github.com/ayoubfathi/OSINT-Toolkit)
- [Exploit DB - Google Hacking Database](https://www.exploit-db.com/google-hacking-database)
- [OSINT Framework](https://osintframework.com)
- [Wayback Machine](https://web.archive.org)
