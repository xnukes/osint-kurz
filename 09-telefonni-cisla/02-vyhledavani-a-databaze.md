# 9.1 Vyhledávání a databáze

> **Cíle kapitoly:**
>
> - Umět vyhledávat informace podle telefonního čísla
> - Znát databáze a nástroje pro reverse phone lookup
> - Umět interpretovat výsledky
> - Znát limity vyhledávání telefonních čísel

---

## Teorie

### Telefonní číslo jako identifikátor

Telefonní číslo je často silnější identifikátor než e-mail — je jedinečné a méně často měněné.

```mermaid
graph TD
    A[Telefonní číslo] --> B[Operátor]
    A --> C[Geolokace]
    A --> D[Osoba]
    A --> E[Propojené služby]
    
    B --> B1[Mobilní/Pevná linka]
    B --> B2[Operátor]
    B --> B3[Předvolba]
    
    C --> C1[Země]
    C --> C2[Region]
    
    D --> D1[Jméno (omezeně)]
    D --> D2[Adresa (omezeně)]
    
    E --> E1[WhatsApp]
    E --> E2[Telegram]
    E --> E3[Signal]
    E --> E4[Sociální sítě]
```

### Struktura telefonního čísla

```bash
# +420 601 123 456
# + = mezinárodní prefix
# 420 = předvolba ČR
# 601123456 = národní číslo

# Předvolby ČR:
# +420 601-609 = T-Mobile
# +420 720-739 = O2
# +420 770-779 = Vodafone
```

### Nástroje pro reverse phone lookup

| Nástroj | URL | Popis |
|---|---|---|
| **Numverify** | numverify.com | API + web |
| **PhoneInfoga** | github.com/sundowndev/phoneinfoga | OSINT nástroj |
| **Truecaller** | truecaller.com | Veřejná databáze (omezená) |
| **Whitepages** | whitepages.com | USA |
| **Sync.me** | sync.me | Caller ID |
| **České databáze** | — | Omezený přístup |

---

## Postup krok za krokem: Analýza telefonního čísla

### 1. Základní informace

```bash
# Předvolba → země
# Délka čísla → formát
# Prefix → operátor
```

### 2. Numverify

```bash
# Web nebo API
curl -H "apikey: KEY" \
  "https://api.numverify.com/validate?number=+420601123456"

# Výsledek:
{
  "valid": true,
  "country": "Czech Republic",
  "location": "Prague",
  "carrier": "T-Mobile",
  "line_type": "mobile"
}
```

### 3. PhoneInfoga

```bash
# Instalace
pip install phoneinfoga

# Základní vyhledání
phoneinfoga -n +420601123456

# Pokročilé vyhledání
phoneinfoga -n +420601123456 -s all
```

### 4. Truecaller / Sync.me

```bash
# Truecaller (web, omezený bez přihlášení)
# Vyhledávání podle čísla
# Zobrazí jméno (pokud je v databázi)
```

---

## Reálné příklady

### Příklad 1: Identifikace operátora

```bash
$ curl "https://api.numverify.com/validate?number=+420721123456"
"carrier": "O2"
"line_type": "mobile"

# +420 721 = O2
```

### Příklad 2: Reverse lookup

```bash
$ phoneinfoga -n +420601123456 -s all
# Operátor: T-Mobile
# Lokace: ČR
# Truecaller: Jan Novák (pokud je v DB)
# WhatsApp: Ano (účet existuje)
# Telegram: Ano (účet existuje)
```

---

## Tipy a časté chyby

> [!TIP]
> PhoneInfoga je nejlepší open-source nástroj pro reverse phone lookup v OSINT.

> [!WARNING]
> **Častá chyba:** Truecaller a podobné služby mají databáze plné chyb. Ne vždy je jméno správné.

> [!WARNING]
> **Častá chyba:** Telefonní číslo může být VoIP nebo virtuální — nelze geolokovat.

---

## Praktické cvičení

**Úkol 1:** Analyzujte telefonní číslo:
1. Použijte Numverify na +420601123456
2. Zjistěte: operátor, typ linky, země
3. Použijte PhoneInfoga na stejné číslo

**Úkol 2:** Porovnání:
1. Zkuste reverse lookup na své číslo
2. Které služby vrátily informace?
3. Jak přesné jsou?

**Pomůcky:** PhoneInfoga, Numverify, Truecaller
**Očekávaný výstup:** Analýza telefonního čísla + porovnání nástrojů

---

## Shrnutí

- Telefonní číslo je silný identifikátor
- Předvolba určuje zemi, prefix operátora
- Numverify poskytuje základní info (operátor, typ)
- PhoneInfoga je komplexní OSINT nástroj
- Truecaller může mít jméno, ale není vždy přesný

---

## Kontrolní otázky

1. Jak zjistíte operátora z telefonního čísla?
2. K čemu slouží PhoneInfoga?
3. Jaký je limit Truecalleru?
4. Proč není reverse phone lookup vždy přesný?
5. Jaké informace lze získat z telefonního čísla?

---

## Zdroje a odkazy

- [PhoneInfoga](https://github.com/sundowndev/phoneinfoga)
- [Numverify](https://numverify.com)
- [Truecaller](https://www.truecaller.com)
- [Sync.me](https://sync.me)
