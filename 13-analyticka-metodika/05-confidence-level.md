# 13.4 Confidence level

> **Cíle kapitoly:**
>
> - Porozumět konceptu confidence level
> - Umět stanovit úroveň spolehlivosti
> - Znát systémy hodnocení

---

## Teorie

### Co je confidence level

Confidence level vyjadřuje míru jistoty analytika v závěr.

```mermaid
graph LR
    A[Nejistota] --> B[Možné]
    B --> C[Pravděpodobné]
    C --> D[Téměř jisté]
    D --> E[Jisté]
```

### Stupně confidence

| Stupeň | Popis | Pravděpodobnost |
|---|---|---|
| **Téměř jisté** | Více zdrojů, konzistentní | >90% |
| **Pravděpodobné** | Silné důkazy | 60-90% |
| **Možné** | Některé důkazy | 30-60% |
| **Nepravděpodobné** | Slabé důkazy | 10-30% |
| **Téměř vyloučené** | Protichůdné důkazy | <10% |

### Kdy snížit confidence

| Faktor | Dopad |
|---|---|
| Jeden zdroj | Snížit |
| Zdroje se shodují jen částečně | Snížit |
| Zdroj má motivaci lhát | Snížit |
| Informace je stará | Snížit |
| Chybí kontext | Snížit |

---

## Postup krok za krokem: Stanovení confidence

### 1. Zhodnoťte důkazy

```bash
# Kolik nezávislých zdrojů?
# Jaká je kvalita zdrojů?
# Jsou konzistentní?
```

### 2. Zvažte alternativy

```bash
# Existuje jiné vysvětlení?
# Co by muselo být pravda, aby alternativní hypotéza platila?
```

### 3. Stanovte úroveň

```bash
# Téměř jisté / Pravděpodobné / Možné / Nepravděpodobné
# Zdokumentujte, proč jste zvolili tuto úroveň
```

---

## Praktické cvičení

**Úkol:** Stanovte confidence level:
1. Vyberte si informaci z předchozích cvičení
2. Zhodnoťte důkazy
3. Stanovte confidence level
4. Zdůvodněte

---

## Shrnutí

- Confidence level vyjadřuje míru jistoty
- Vždy uvádět confidence level v závěrech
- Snižovat při nejistotě nebo jednom zdroji
- Zdokumentovat důvody pro zvolenou úroveň

---

## Kontrolní otázky

1. Co je confidence level?
2. Jaké jsou stupně confidence?
3. Kdy snižujete confidence?
4. Proč uvádět confidence level v závěrech?
5. Jak zdokumentujete důvody?
