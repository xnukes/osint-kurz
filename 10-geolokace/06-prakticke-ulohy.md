# 10.5 Praktické úlohy

> **Cíle kapitoly:**
>
> - Procvičit geolokaci na praktických úlohách
> - Kombinovat všechny techniky z kapitoly 10
> - Získat jistotu v geolokaci

---

## Úloha 1: Geolokace fotografie

**Zadání:** Určete místo pořízení fotografie. (Použijte libovolnou fotku z internetu nebo z vlastního archivu bez GPS.)

**Postup:**
1. Reverzní vyhledání na Google Images a Yandex
2. Vizuální analýza (jazyky, značky, architektura)
3. Street View pro ověření
4. Satelitní snímky pro potvrzení

## Úloha 2: Geolokace podle stínu

**Zadání:** Fotografie ukazuje objekt s výrazným stínem. Určete přibližný čas a zeměpisnou šířku.

**Postup:**
1. Změřte poměr výška/délka stínu
2. SunCalc → výška slunce
3. Odhad času a šířky

## Úloha 3: Analýza lokality

**Zadání:** Máte adresu. Proveďte analýzu lokality pomocí map, satelitů a Street View.

**Postup:**
1. Street View — fyzické zabezpečení, přístup
2. Satelitní snímky — okolí, infrastruktura
3. Overpass Turbo — služby v okolí
4. Historické snímky — změny v čase

## Úloha 4: GeoGuessr výzva

**Zadání:** Použijte GeoGuessr (geoguessr.com) a určete místo náhodné fotografie.

**Postup:**
1. Bez pohybu — pouze fotografie
2. Určit: země, region, město (pokud možné)
3. Jaké indikátory jste použili?

---

## Řešení

### Úloha 1 — Indikátory

```bash
# Reverzní vyhledání:
# Google: 3 podobné fotky
# Yandex: 7 podobných (ukázalo jiné místo)

# Vizuální:
# České nápisy → ČR
# Tramvaj → Praha nebo Brno
# Budova Národního muzea → Praha

# Ověření Street View → Václavské náměstí
```

### Úloha 2 — Stín

```bash
# Poměr 1:1.5
# SunCalc pro 50° s.š.:
# 10:00 v létě nebo 14:00 v zimě
# Kombinace s oblečením → léto → 10:00
```

---

## Tipy a časté chyby

> [!TIP]
> GeoGuessr je skvělý nástroj pro procvičení geolokačních dovedností.

> [!WARNING]
> **Častá chyba:** Příliš rychlý závěr. Vždy ověřovat více indikátory.

---

## Shrnutí

- Geolokace kombinuje reverzní vyhledávání, vizuální analýzu, stíny a mapy
- Praxe je klíčová pro zlepšení
- GeoGuessr je zábavný způsob procvičování
- Vždy používat více indikátorů

---

## Zdroje a odkazy

- [GeoGuessr](https://www.geoguessr.com)
- [Google Earth](https://earth.google.com)
- [SunCalc](https://www.suncalc.org)
