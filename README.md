# 🛡️ NTLM Cracking

## 📌 Formål
Dette prosjektet dokumenterer en laboratorieøvelse hvor jeg har opprettet en lokal Windows-konto, henter NTLM-hash fra minnet ved hjelp av **Mimikatz**, og demonstrerer cracking av hashen med **John the Ripper**.  
Hensikten er å forstå hvordan NTLM-hash-utvinning og cracking fungerer, og hvilke sikkerhetstiltak som bør være på plass. Alt utført i et lukket testmiljø med uttrykkelig tillatelse.

---

## 🔍 Innhold
Repoen dekker:

- **Scope:** Lokalt Windows-lab (administrativ tilgang nødvendig)  
- **Metodikk:** Opprette testbruker → hente NTLM-hash fra minnet → cracke hash med John the Ripper  
- **Etikk & lovverk:** Tydelig advarsel om at teknikkene kun skal brukes i kontrollerte miljøer med tillatelse

---

## 🛠️ Verktøy brukt
- **Mimikatz** – utvinning av credentials/NTLM-hash fra minne  
- **John the Ripper** – cracking av NTLM-hash  
- **wordlist:** `rockyou.txt`  

---

## 📊 Viktigste funn / observasjoner
- NTLM-hash kan hentes fra minnet hvis kontoens credentials finnes i RAM (f.eks. ved aktiv innlogging eller tjenester).  
- Effektiviteten av cracking avhenger sterkt av passordets kompleksitet og tilgjengelige wordlists / regler.  
- **Sikkerhetsimplikasjoner:** Lagring av plaintekst-passord, svak passordpolicy eller manglende beskyttelse mot lokal eskalering øker risiko.  
- **Mottiltak:** Sterk passordpolicy, LSA-protection / Credential Guard, redusere administrative innlogginger, og oppdatere/overvåke endepunkt-sikkerhet.

---

## 📑 Repo-struktur
```bash
ntlm-cracking-lab/
│── README.md
│── LICENSE
│── images/
│   ├── 01-opprett-bruker.png
│   ├── 02-lage-passord.png
│   ├── 03-logge-inn.png
│   ├── 04-lastet-ned-mimikatz.png
│   ├── 05-mimikatz-kommandoer.png
│   ├── 06-mimikatz-ntlm-hash.png
│   └── 07-john-crack.png
│── .gitignore
