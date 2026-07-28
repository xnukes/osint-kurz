# 14.5 Analýza infrastruktury

> **Cíle kapitoly:**
>
> - Umět zmapovat infrastrukturu cíle
> - Aplikovat techniky z kapitoly 5
> - Sestavit mapu infrastruktury

---

## Zadání

**Cíl:** Zmapujte infrastrukturu cílové domény.

---

## Postup krok za krokem

### 1. DNS

```bash
# A, AAAA, MX, TXT, NS, CNAME
# Subdomény z CT logů
```

### 2. Port scanning

```bash
nmap -sV --top-ports 100 cíl
# Otevřené porty a služby
```

### 3. Shodan

```bash
# hostname:cíl
# Další zařízení organizace
```

### 4. CDN

```bash
# Cloudflare?
# Origin IP?
```

### 5. Vizualizace

```bash
# Mermaid diagram
# Mapa infrastruktury
```

---

## Shrnutí

- DNS dává základní přehled
- Port scanning odhaluje služby
- Shodan najde další zařízení
- Vizualizace pomáhá pochopit strukturu
