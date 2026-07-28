# 11.4 Vyhledávání informací

> **Cíle kapitoly:**
>
> - Umět vyhledávat na dark webu
> - Znát vyhledávače pro onion služby
> - Znát techniky pro monitoring dark webu

---

## Teorie

### Dark web vyhledávače

| Vyhledávač | URL | Popis |
|---|---|---|
| **Ahmia** | ahmia.fi | Nejznámější, indexuje .onion |
| **Torch** | torche — jeden z nejstarších | |
| **Not Evil** | notevil | Alternativa |
| **Phobos** | phobos | Další onion vyhledávač |
| **Candle** | candle | Novější vyhledávač |

### Ahmia pokročilé vyhledávání

```bash
# Základní dotaz
téma

# Víceslovný dotaz
"přesná fráze"

# Vyloučení
téma -vyloučit

# Site
site:.onion téma
```

### Monitoring dark webu

| Nástroj | Popis |
|---|---|
| **Ahmia API** | Programový přístup |
| **OnionScan** | Skenování onion služeb |
| **DarkFeed** | RSS feedy z dark webu |
| **IntelX** | Multi-zdrojové vyhledávání |

---

## Postup krok za krokem: Vyhledávání

### 1. Ahmia

```bash
# Otevřít ahmia.fi
# Vyhledat téma
# Prohlédnout výsledky (.onion)
```

### 2. Ověření

```bash
# Každý .onion odkaz ověřit:
# - Existuje?
# - Je aktivní?
# - Je bezpečný? (žádné automatické stahování)
```

### 3. Dokumentace

```bash
# Zaznamenat:
# - .onion adresu
# - Popis služby
# - Stav (aktivní/neaktivní)
# - Obsah (legitimní/nelegální)
```

---

## Tipy a časté chyby

> [!TIP]
> Ahmia indexuje jen zlomek onion služeb. Většina dark webu není indexována.

> [!WARNING]
> **Častá chyba:** Ahmia může zobrazovat nelegální obsah. Buďte připraveni a nejednejte nelegálně.

> [!WARNING]
> **Častá chyba:** Domněnka, že vše na dark webu je skryté. Mnoho onion služeb je sledováno policií.

---

## Praktické cvičení

**Úkol:** Vyhledávejte na dark webu:
1. Otevřete Ahmia
2. Vyhledejte téma kybernetická bezpečnost
3. Vyhledejte téma whistleblowing
4. Zaznamenejte výsledky

**Pomůcky:** Tor Browser, Ahmia
**Očekávaný výstup:** Seznam onion služeb k tématům

---

## Shrnutí

- Ahmia je hlavní vyhledávač dark webu
- Většina onion služeb není indexována
- Každý odkaz ověřovat
- Dark web je sledován
- Dokumentovat nálezy

---

## Kontrolní otázky

1. Jaký vyhledávač použijete pro dark web?
2. Proč Ahmia neindexuje vše?
3. Jak ověříte onion adresu?
4. Proč je dark web sledován?
5. Jak dokumentujete nálezy z dark webu?

---

## Zdroje a odkazy

- [Ahmia](https://ahmia.fi)
- [OnionScan](https://onionscan.org)
- [DarkFeed](https://darkfeed.io)
