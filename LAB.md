# LAB — NTLM Cracking

## Forutsetninger
- Windows testmaskin med admin-tilgang.
- Kali/eller tilsvarende for cracking (John).
- Mimikatz lastet ned (bruk kun i lab).
- Wordlist (f.eks. `/usr/share/wordlists/rockyou.txt`).

---

## Steg 1 — Opprett testbruker
<img width="445" height="380" alt="1  Lage bruker" src="https://github.com/user-attachments/assets/d29832da-a9db-4c4d-98a2-4c54a48429c6" />

*Opprettelse av brukerobjekt i AD / lokal users.*

<img width="446" height="378" alt="2  Lage passord" src="https://github.com/user-attachments/assets/74f6ee78-c312-4dc7-a268-1c84ffb87d59" />

*Angi passord og innstillinger (f.eks. 'Password never expires').*

<img width="1024" height="761" alt="3  Logge inn T50087" src="https://github.com/user-attachments/assets/dc10f2a8-03c0-40fc-957e-bea39b303243" />

*Bekrefter innlogging.*

---

## Steg 2 — Last ned og kjør Mimikatz
<img width="887" height="718" alt="4  Lastet ned Mimikatz" src="https://github.com/user-attachments/assets/97808b83-c49c-4bc0-90d1-55e0b437c5f6" />

*Pakker ut og kjører `mimikatz.exe` som administrator.*

<img width="672" height="183" alt="5  Mimikatz kommandoer" src="https://github.com/user-attachments/assets/b3a0815c-e788-4d7f-9913-ea07fab7af45" />

*Kjører privilege::debug og sekurlsa::logonpasswords for å få rettigheter og leser LSASS-prosessen for å hente innloggingsinformasjon*

<img width="665" height="716" alt="6  Mimikatz NTLM Hash" src="https://github.com/user-attachments/assets/5f682d99-2a6d-4dc1-a4e9-fbf2ae353d26" />

*NTLM Hashen i klartekst*

<img width="884" height="374" alt="7  John crack" src="https://github.com/user-attachments/assets/2262f4ae-07ad-4a7c-8ff7-866757dcfdb4" />

*Oppretter en ny tekstfil med brukernavn og passord som sjekkes opp mot rockyou.txt for å finne passordet.*
