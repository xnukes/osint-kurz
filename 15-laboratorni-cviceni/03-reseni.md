# 15.3 Řešení

> **Cíle kapitoly:**
>
> - Poskytnout řešení vybraných úkolů
> - Ukázat správný postup
> - Demonstrovat očekávané výstupy

---

## Řešení vybraných úkolů

### Úkol 1.1: PDF na doméně mvcr.cz

```bash
Google: site:mvcr.cz filetype:pdf
# Výsledek: desítky PDF dokumentů
# Lze filtrovat: site:mvcr.cz filetype:pdf "zpráva"
```

### Úkol 2.1: WHOIS 3 domény

```bash
whois seznam.cz
whois google.com
whois github.com

# Srovnání:
# seznam.cz: vlastní AS, český registrátor
# google.com: vlastní AS, USA
# github.com: vlastní AS, USA, Microsoft
```

### Úkol 4.1: EXIF z telefonu

```bash
exiftool photo.jpg
# GPS, datum, model telefonu
# Pokud fotka z social media: EXIF smazán
```

### Úkol 5.1: Sherlock

```bash
sherlock username
# Seznam platforem, kde username existuje
# Často: Twitter, GitHub, Instagram, Reddit
```

### Úkol 6.1: Hlavičky e-mailu

```bash
# Zobrazit hlavičky v Gmailu
# Analyzovat Received řetězec
# Zkontrolovat SPF, DKIM, DMARC
```

---

## Obecná řešení

| Oblast | Klíčový nástroj | Očekávaný výstup |
|---|---|---|
| Vyhledávání | Google operátory | Seznam výsledků |
| Domény | whois, dig, crt.sh | Profil domény |
| IP | nmap, shodan | Mapa služeb |
| Metadata | exiftool | EXIF data |
| Sociální sítě | Sherlock | Multi-platformní profil |
| E-maily | HIBP, Epieos | Analýza účtu |
| Telefony | PhoneInfoga | Operátor, služby |
| Geolokace | SunCalc, Google Earth | Místo, čas |
| Dark web | Tor Browser, Ahmia | Onion služby |
| Úniky | HIBP, DeHashed | Seznam úniků |
| Metodika | Mermaid, Gephi | Časová osa, graf |
