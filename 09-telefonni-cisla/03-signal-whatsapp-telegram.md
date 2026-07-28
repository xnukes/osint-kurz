# 9.2 Signal, WhatsApp, Telegram

> **Cíle kapitoly:**
>
> - Umět ověřit existenci účtu na messengerech
> - Znát techniky pro vyhledávání napříč messengery
> - Umět analyzovat metadata z messengerů

---

## Teorie

### Messengery a OSINT

Messengery (WhatsApp, Signal, Telegram) propojují telefonní čísla s uživatelskými profily.

```mermaid
graph TD
    A[Telefonní číslo] --> B[WhatsApp]
    A --> C[Signal]
    A --> D[Telegram]
    
    B --> B1[Profilová fotka]
    B --> B2["About" text]
    B --> B3[Status (online/offline)]
    
    C --> C1[Profilová fotka]
    C --> C2[Username (volitelně)]
    
    D --> D1[Username]
    D --> D2[Bio]
    D --> D3[Profilová fotka]
    D --> D4[Last seen]
```

### Co lze zjistit

| Messenger | Informace | Dostupnost |
|---|---|---|
| **WhatsApp** | Existence účtu | Ano (API) |
| | Profilová fotka | Ano (s kontaktem) |
| | About text | Ano |
| **Signal** | Existence účtu | Omezeně |
| | Username | Pokud nastaven |
| **Telegram** | Existence účtu | Ano |
| | Username | Ano (volitelně) |
| | Bio | Ano |
| | Profilová fotka | Ano |
| | Last seen | Volitelné |

### Nástroje

| Nástroj | Messengery |
|---|---|
| **PhoneInfoga** | WhatsApp, Telegram |
| **WhatsApp API** | WhatsApp (neoficiální) |
| **Telegram API** | Telegram |
| **Signal CLI** | Signal (omezeně) |
| **WAG scraper** | WhatsApp |

---

## Postup krok za krokem: Kontrola messengerů

### 1. WhatsApp

```bash
# PhoneInfoga
phoneinfoga -n +420601123456 -s whatsapp

# WhatsApp API (neoficiální)
# Přidání čísla do kontaktů → kontrola profilovky
```

### 2. Telegram

```bash
# PhoneInfoga
phoneinfoga -n +420601123456 -s telegram

# Telegram API
# https://t.me/USERNAME
# Kontrola existence účtu

# Telethon
from telethon import TelegramClient
client = TelegramClient('session', api_id, api_hash)
await client.get_entity('+420601123456')
```

### 3. Signal

```bash
# Signal — omezená možnost
# Registrace k Signal vyžaduje SMS kód
# Těžko automatizovatelné
```

---

## Reálné příklady

### Příklad 1: WhatsApp existence

```bash
$ phoneinfoga -n +420601123456 -s whatsapp
[WhatsApp] +420601123456: Exists
[WhatsApp] Profile picture: Yes (URL)
```

### Příklad 2: Telegram účet

```bash
$ phoneinfoga -n +420601123456 -s telegram
[Telegram] +420601123456: Exists
[Telegram] Username: @jan_novak
[Telegram] Bio: IT Security Specialist
```

---

## Tipy a časté chyby

> [!TIP]
> PhoneInfoga dokáže zkontrolovat existenci účtu na WhatsApp a Telegram během sekund.

> [!WARNING]
> **Častá chyba:** WhatsApp profilová fotka je viditelná jen kontaktům. Bez uložení do kontaktů fotku neuvidíte.

> [!WARNING]
> **Častá chyba:** Signal je nejbezpečnější messenger — bez přímého kontaktu nelze zjistit existenci účtu.

---

## Praktické cvičení

**Úkol 1:** Zkontrolujte messengery:
1. Použijte PhoneInfoga na testovací číslo
2. Existuje účet na WhatsApp? Telegramu? Signalu?
3. Jaké informace jsou dostupné?

**Úkol 2:** Telegram profil:
1. Pokud číslo má Telegram, zkuste najít username
2. Zkontrolujte bio a profilovou fotku

**Pomůcky:** PhoneInfoga, Telegram API
**Očekávaný výstup:** Analýza messenger účtů k číslu

---

## Shrnutí

- WhatsApp a Telegram umožňují ověřit existenci účtu
- PhoneInfoga automatizuje kontrolu napříč messengery
- WhatsApp profilovka jen pro kontakty
- Signal je nejbezpečnější — nejhůře analyzovatelný
- Telegram bio a username odhalují informace o osobě

---

## Kontrolní otázky

1. Jak zjistíte, zda číslo používá WhatsApp?
2. Co lze zjistit z Telegram účtu?
3. Proč je Signal obtížné analyzovat?
4. K čemu slouží PhoneInfoga?
5. Proč není WhatsApp profilovka vždy vidět?

---

## Zdroje a odkazy

- [PhoneInfoga](https://github.com/sundowndev/phoneinfoga)
- [Telegram API](https://core.telegram.org)
- [WhatsApp Web](https://web.whatsapp.com)
