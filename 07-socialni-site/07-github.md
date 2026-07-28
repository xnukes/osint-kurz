# 7.6 GitHub

> **Cíle kapitoly:**
>
> - Umět analyzovat GitHub profily a repozitáře
> - Znát techniky pro hledání citlivých dat na GitHub
> - Umět analyzovat commity a přispěvatele
> - Znát nástroje pro GitHub OSINT

---

## Teorie

### GitHub jako OSINT zdroj

GitHub je platforma pro vývoj software, která obsahuje množství dat o vývojářích, projektech a firmách.

```mermaid
graph TD
    A[GitHub profil] --> B[Repozitáře]
    A --> C[Příspěvky]
    A --> D[Organizace]
    A --> E[Sledující]
    
    B --> B1[Kód]
    B --> B2[Commity]
    B --> B3[Issues]
    B --> B4[Wiki]
    B --> B5[Soubory]
    
    C --> C1[Aktivita]
    C --> C2[Jazyk]
    C --> C3[Čas]
    
    D --> O1[Firemní organizace]
    D --> O2[Kolegové]
```

### Co lze na GitHub najít

| Data | Dostupnost | OSINT hodnota |
|---|---|---|
| Uživatelské jméno | Ano | Identita |
| Jméno | Volitelné | Identita |
| Bio/Company | Volitelné | Zaměstnání |
| E-mail | Volitelné | Kontakt |
| Lokace | Volitelné | Poloha |
| Repozitáře | Ano | Projekty |
| Commity | Ano | Aktivita |
| Sledující | Ano | Síť |
| Organizace | Ano | Zaměstnavatel |
| SSH klíče | Volitelné | Bezpečnost |
| GPG klíče | Volitelné | Identita |

### Nástroje pro GitHub OSINT

| Nástroj | Účel |
|---|---|
| **GitHub Search** | Vyhledávání v kódu, repozitářích |
| **GitDorker** | Hledání citlivých dat |
| **truffleHog** | Hledání tajemství v commitech |
| **gitrob** | Analýza bezpečnosti repozitářů |
| **github-dorks** | Automatizované dorkování |

---

## Postup krok za krokem: GitHub analýza

### 1. Profil

```bash
# Základní informace
github.com/username

# Jméno, bio, lokace, web
# Organizace
# Počet repozitářů
# Příspěvkový graf (contribution graph)
```

### 2. Repozitáře

```bash
# Veřejné repozitáře
# Forknuto z?
# Jazyk, hvězdičky, forky
# Issues a pull requests
# Kdo přispívá?
```

### 3. Commity

```bash
# Historie commitů
# E-mail v commitech
# Časová osa aktivity
# Spolupracovníci
```

### 4. Hledání citlivých dat

```bash
# GitHub search
"password" OR "secret" OR "api_key" language:python
"aws_access_key" language:yaml
"-----BEGIN RSA PRIVATE KEY-----"
"DB_PASSWORD" language:env
```

---

## Reálné příklady

### Příklad 1: Identifikace vývojáře

**Cíl:** Zjistit, na jakých projektech vývojář pracuje

**Postup:**
1. Zkontrolovat profi — bio, lokace, company
2. Prohlédnout repozitáře — témata, jazyky
3. Contribution graph — jak aktivní?
4. Commity — s kým spolupracuje?

### Příklad 2: Firemní projekty

**Cíl:** Zjistit, na čem firma pracuje

**Postup:**
1. Najít firemní organizaci na GitHub
2. Prohlédnout repozitáře
3. Zkontrolovat issues — co plánují?
4. Commity — kdo je aktivní?

---

## Tipy a časté chyby

> [!TIP]
> E-mail v commitech často uniká, i když není v profilu. Zkontrolujte `git log` nebo `commit` historii.

> [!WARNING]
> **Častá chyba:** Citlivá data (API klíče, hesla) v repozitářích. I po smazání zůstávají v historii commitů.

> [!WARNING]
> **Častá chyba:** Forky repozitářů mohou obsahovat citlivá data z upstreamu. Fork je kopie včetně historie.

---

## Praktické cvičení

**Úkol 1:** Analyzujte GitHub profil:
1. Najděte GitHub profil vývojáře (např. svůj nebo známý projekt)
2. Zjistěte: bio, lokace, company
3. Prohlédněte repozitáře a commity
4. Contribution graph — jaká je aktivita?

**Úkol 2:** Hledání citlivých dat:
1. Vyzkoušejte GitHub search na "password" site:github.com
2. Hledejte API klíče ve formátu "sk-" (Stripe) nebo "AIza" (Google)
3. Co jste našli?

**Úkol 3:** GitDorker:
1. Nainstalujte GitDorker
2. Spusťte na testovací doméně (s povolením)
3. Analyzujte výsledky

**Pomůcky:** GitHub, GitDorker, truffleHog
**Očekávaný výstup:** Profilová analýza + nálezy citlivých dat

---

## Shrnutí

- GitHub odhaluje projekty, aktivitu a síť vývojářů
- Commity často obsahují e-maily autorů
- Veřejné repozitáře často obsahují citlivá data
- Smazaná data zůstávají v historii commitů
- Organizace prozrazují firemní strukturu

---

## Kontrolní otázky

1. Jaké informace jsou na GitHub profilu veřejné?
2. Kde v GitHubu uniká e-mail i přes skrytí v profilu?
3. Jak hledáte citlivá data na GitHub?
4. Proč fork repozitáře může být bezpečnostní riziko?
5. Co je contribution graph a k čemu slouží?

---

## Zdroje a odkazy

- [GitHub Search](https://github.com/search)
- [GitDorker](https://github.com/obheda12/GitDorker)
- [truffleHog](https://github.com/trufflesecurity/trufflehog)
- [gitrob](https://github.com/michenriksen/gitrob)
- [GitGuardian](https://www.gitguardian.com)
