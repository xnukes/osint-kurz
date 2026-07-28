# 4.6 Praktické příklady

> **Cíle kapitoly:**
>
> - Aplikovat techniky analýzy domén na reálné příklady
> - Kombinovat WHOIS, DNS, ASN, reverzní DNS a CT
> - Umět sestavit komplexní profil domény

---

## Případová studie 1: Kompletní analýza domény

**Cíl:** Proveďte kompletní OSINT analýzu cílové domény (např. seznam.cz)

### Krok 1: WHOIS

```bash
$ whois seznam.cz
# Domain: seznam.cz
# Registrant: Seznam.cz, a.s.
# Registration: 1997-09-01
# Expiration: 2027-09-01
# Registrar: CZ.NIC
# NSSET: SEZNAM
```

### Krok 2: DNS záznamy

```bash
# A záznam
$ dig seznam.cz +short
77.75.75.75
77.75.77.77

# MX záznam
$ dig seznam.cz MX +short
10 mail.seznam.cz.

# TXT záznam
$ dig seznam.cz TXT +short
"v=spf1 include:spf.seznam.cz ~all"

# NS záznam
$ dig seznam.cz NS +short
ns.seznam.cz.
ns2.seznam.cz.
```

### Krok 3: ASN analýza

```bash
$ whois 77.75.75.75 | grep -i origin
origin: AS24971

$ whois -h whois.radb.net !gAS24971
# Seznam.cz, a.s.
# IP rozsahy: 77.75.75.0/24, 77.75.76.0/24, ...
```

### Krok 4: Reverzní DNS

```bash
$ dig -x 77.75.75.75 +short
mail.seznam.cz
```

### Krok 5: Certificate Transparency

```bash
$ curl -s "https://crt.sh/?q=seznam.cz&output=json" | \
  jq -r '.[].name_value' | sort -u | head -20
```

### Krok 6: Reverse IP lookup

```bash
# Pomocí yougetsignal.com nebo securitytrails.com
# seznam.cz, seznam.net, spoluzaci.cz, ...
```

### Kompletní profil

| Atribut | Hodnota |
|---|---|
| **Doména** | seznam.cz |
| **Vlastník** | Seznam.cz, a.s. |
| **Registrováno** | 1997 |
| **IP adresy** | 77.75.75.75, 77.75.77.77 |
| **ASN** | AS24971 |
| **IP rozsah** | 77.75.75.0/24 a další |
| **Mail server** | mail.seznam.cz |
| **Nameservery** | ns.seznam.cz, ns2.seznam.cz |
| **SPF** | v=spf1 include:spf.seznam.cz ~all |
| **Subdomény** | www, mail, email, video, firmy, ... |
| **Reverse PTR** | mail.seznam.cz |

---

## Případová studie 2: Porovnání doménových technologií

### Doména s CDN (Cloudflare)

```bash
$ dig cloudflare.com +short
104.16.124.96
104.16.123.96

# PTR — typicky cloudflare IP
# WHOIS může ukazovat Cloudflare
# ASN: AS13335

$ dig cloudflare.com NS +short
ns3.cloudflare.com.
ns4.cloudflare.com.
ns5.cloudflare.com.
ns6.cloudflare.com.
ns7.cloudflare.com.
```

### Doména s vlastní infrastrukturou

```bash
$ dig seznam.cz +short
77.75.75.75
77.75.77.77

# PTR — vlastní jméno
# WHOIS — vlastní kontakt
# ASN — vlastní AS
# IP rozsah — vlastní
```

### Doména na sdíleném hostingu

```bash
$ dig example-hosting.cz +short
81.2.3.4  # Sdílená IP s mnoha doménami

# Reverse IP — desítky až stovky domén
# PTR — hosting provider, ne doména
# ASN — hosting provider
```

---

## Cvičení

**Úkol:** Proveďte kompletní analýzu 3 domén:

1. **Doména s CDN** (např. github.com)
2. **Česká doména** (např. novinky.cz)
3. **Malý web** (např. lokální firma nebo blog)

Pro každou doménu zjistěte:
1. WHOIS — vlastník, datum registrace, registrátor
2. DNS — A, MX, TXT, NS, SOA
3. ASN — číslo, organizace, IP rozsahy
4. Reverzní DNS — PTR záznam
5. CT — subdomény z certifikátů
6. Reverse IP — další domény na stejné IP

**Výstup:** Tabulka srovnání + kompletní profil každé domény

---

## Shrnutí

- Kompletní analýza domény kombinuje 5+ technik
- Každá technika odhaluje jinou vrstvu informací
- WHOIS dává vlastnická data, DNS infrastrukturu
- ASN odhaluje IP rozsahy organizace
- CT logy ukazují subdomény a časovou osu
- Reverse IP najde související domény

---

## Kontrolní otázky

1. Jaké kroky zahrnuje kompletní analýza domény?
2. Co vše lze zjistit kombinací těchto technik?
3. Jaký je rozdíl mezi doménou s CDN a vlastní infrastrukturou?
4. Proč je reverse IP lookup užitečný?
5. Co je nejdůležitější zjištění při analýze domény?

---

## Zdroje a odkazy

- [crt.sh](https://crt.sh)
- [MXToolbox](https://mxtoolbox.com)
- [DomainTools](https://domaintools.com)
- [SecurityTrails](https://securitytrails.com)
- [DNSDumpster](https://dnsdumpster.com)
