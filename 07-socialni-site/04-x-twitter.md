# 7.3 X (Twitter)

> **Cíle kapitoly:**
>
> - Umět analyzovat X/Twitter profily a tweety
> - Znát pokročilé vyhledávání na X
> - Umět mapovat sítě sledujících a interakcí
> - Znát nástroje pro Twitter OSINT

---

## Teorie

### X/Twitter jako OSINT zdroj

X je primárně textová síť vhodná pro sledování diskuzí, trendů a síťových vztahů.

```mermaid
graph TD
    A[X profil] --> B[Tweety]
    A --> C[Sledující]
    A --> D[Sledovaní]
    A --> E[Líbí se mi]
    A --> F[Seznamy]
    A --> G[Média]
    
    B --> B1[Text]
    B --> B2[Datum]
    B --> B3[Retweety]
    B --> B4[Odpovědi]
    B --> B5[Lokace (volitelně)]
    
    C --> S1[Síť followerů]
    D --> S2[Síť sledovaných]
    E --> Z1[Zájmy]
```

### X vyhledávací operátory

| Operátor | Příklad | Popis |
|---|---|---|
| **from:** | from:username | Tweety od uživatele |
| **to:** | to:username | Odpovědi uživateli |
| **@** | @username | Zmínky uživatele |
| **#** | #hashtag | Hashtag |
| **since:** | since:2024-01-01 | Od data |
| **until:** | until:2024-12-31 | Do data |
| **filter:media** | filter:media | S médii |
| **filter:images** | filter:images | S obrázky |
| **filter:links** | filter:links | S odkazy |
| **lang:** | lang:cs | České tweety |
| **min_faves:** | min_faves:100 | Minimálně 100 lajků |
| **min_retweets:** | min_retweets:50 | Minimálně 50 retweetů |
| **-filter:retweets** | -filter:retweets | Bez retweetů |

### Nástroje pro Twitter OSINT

| Nástroj | Účel |
|---|---|
| **Twitter Advanced Search** | Pokročilé vyhledávání |
| **Nitter** | Anonymní prohlížení Twitteru |
| **TweetDeck** | Sledování více sloupců |
| **TweeterID** | Získání User ID |
| **Social Bearing** | Analýza tweetů |
| **Twitonomy** | Detailní analýza profilů |
| **ExportData** | Export dat |

---

## Postup krok za krokem: Analýza profilu

### 1. Základní informace

```bash
# Profil
x.com/username

# Bio, lokace, web, datum registrace
# Počet tweetů, sledujících, sledovaných
```

### 2. Pokročilé vyhledávání

```bash
# Všechny tweety uživatele
from:username

# S obrázky
from:username filter:images

# V časovém rozmezí
from:username since:2024-01-01 until:2024-06-01

# Tweety obsahující konkrétní slovo
from:username "klíčové slovo"

# Odpovědi uživateli
to:username
```

### 3. Analýza sítě

```bash
# Nástroj: Social Bearing nebo Twitonomy
# Kdo jsou nejčastější interakce?
# Jaká je struktura followerů?
# Kdo retweetuje nejčastěji?
```

### 4. Metadata tweetu

```bash
# Každý tweet má unikátní ID
# Lze získat přes API
# Obsahuje: datum, čas (přesný), source (klient)
```

---

## Reálné příklady

### Příklad 1: Sledování diskuze

**Cíl:** Sledovat vývoj diskuze na konkrétní téma

```bash
# Sledování hashtagu v čase
#hashtag since:2024-01-01 until:2024-12-31

# Kdo jsou hlavní účastníci?
# Jak se vyvíjel sentiment?
# Které tweety měly největší dosah?
```

### Příklad 2: Identifikace botů

**Cíl:** Identifikovat podezřelé účty

**Indikátory:**
- Vysoký poměr sledování × sledující
- Žádné originální tweety, jen retweety
- Náhodně generovaná uživatelská jména
- Profilová fotka z generátoru obličejů

---

## Tipy a časté chyby

> [!TIP]
> Nitter (nitter.net) umožňuje prohlížet Twitter bez přihlášení a bez sledování. Používejte ho pro anonymní výzkum.

> [!WARNING]
> **Častá chyba:** X API je placené a omezené. Pro větší analýzu používejte scraping (s opatrností).

> [!WARNING]
> **Častá chyba:** Retweety nejsou souhlas. Někteří retweetují, aby kritizovali. Analyzujte kontext.

---

## Praktické cvičení

**Úkol 1:** Analyzujte profil:
1. Vyberte x profil veřejné osoby
2. Pomocí pokročilého vyhledávání zjistěte:
   - Kdy byl účet založen?
   - Jaká témata nejčastěji tweetuje?
   - S kým nejčastěji interaguje?

**Úkol 2:** Sledování hashtagu:
1. Vyberte hashtag (např. #kyberbezpecnost)
2. Sledujte vývoj za poslední měsíc
3. Kdo jsou hlavní přispěvatelé?

**Pomůcky:** Twitter Advanced Search, Nitter, Social Bearing
**Očekávaný výstup:** Analýza profilu + sledování hashtagu

---

## Shrnutí

- X je cenný pro sledování diskuzí a síťových vztahů
- Pokročilé vyhledávání umožňuje přesné dotazy
- Twitter API je omezené a placené
- Nitter umožňuje anonymní přístup
- Analýza sítě odhaluje vztahy a vliv

---

## Kontrolní otázky

1. Jak najdete všechny tweety konkrétního uživatele?
2. Jaký operátor použijete pro tweety s obrázky?
3. K čemu slouží Nitter?
4. Jaké jsou indikátory bot účtu?
5. Proč je kontext důležitý při analýze retweetů?

---

## Zdroje a odkazy

- [X Advanced Search](https://x.com/search-advanced)
- [Nitter](https://nitter.net)
- [Social Bearing](https://socialbearing.com)
- [Twitonomy](https://twitonomy.com)
- [TweeterID](https://tweeterid.com)
