# 14.6 Kompletní řešení krok za krokem

> **Cíle kapitoly:**
>
> - Ukázka celého vyšetřovacího procesu
> - Od zadání po závěrečnou zprávu
> - Demonstrace všech technik

---

## Kompletní případ

**Zadání:** Prověřte firmu "Seznam.cz, a.s." — zjistěte:
1. Základní informace (IČO, sídlo, vedení)
2. Doménovou infrastrukturu
3. Veřejné zakázky
4. Technologický stack

---

### Fáze 1: Základní informace

```bash
# OR: IČO 26168685, sídlo: Radlická 3294/10, Praha 5
# Jednatelé: Pavel Zima, ...
```

### Fáze 2: Doménová analýza

```bash
# WHOIS: seznam.cz, registrováno 1997
# DNS: 77.75.75.75, AS24971
# Subdomény: www, email, firmy, ...
```

### Fáze 3: Technologie

```bash
# Port 80/443: Apache
# Vlastní AS, vlastní IP rozsah
# SPF + DMARC (p=reject)
```

### Fáze 4: Zpráva

```bash
# Executive summary
# Nálezy
# Analýza
# Závěr
```

---

## Shrnutí

- Systematický postup je klíčový
- Každá fáze přidává nové informace
- Kombinace technik dává celkový obraz
- Závěrečná zpráva shrnuje vše
