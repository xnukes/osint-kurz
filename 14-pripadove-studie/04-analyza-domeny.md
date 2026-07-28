# 14.3 Analýza domény

> **Cíle kapitoly:**
>
> - Umět provést komplexní analýzu domény
> - Aplikovat techniky z kapitol 4-5
> - Sestavit profil domény

---

## Zadání

**Cíl:** Proveďte kompletní analýzu domény example.com.

---

## Postup krok za krokem

### 1. WHOIS

```bash
whois example.com
# Vlastník, datum registrace, registrátor
```

### 2. DNS

```bash
dig example.com A, MX, TXT, NS
# IP, mail servery, SPF, nameservery
```

### 3. ASN a IP

```bash
whois 93.184.216.34
# ASN, IP rozsah, organizace
```

### 4. CT logy

```bash
crt.sh/?q=example.com
# Subdomény, certifikáty
```

### 5. Reverse IP

```bash
# yougetsignal.com
# Další domény na stejné IP
```

---

## Shrnutí

- WHOIS dává vlastníka
- DNS odhaluje infrastrukturu
- CT logy ukazují subdomény
- Reverse IP najde příbuzné domény
