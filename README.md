# 🏰 Stadiu Dosar ONRC

Aplicație desktop pentru monitorizarea automată a stadiului dosarelor de pe portalul oficial al Registrului Comerțului (myportal.onrc.ro).

---

## 📋 Descriere

**Stadiu Dosar ONRC** este o aplicație Windows care verifică periodic stadiul unor dosare de pe `myportal.onrc.ro` (secțiunea „Stadiu dosar") și te anunță printr-o notificare pe ecran atunci când apare o schimbare.

### Ce monitorizează:
- **Etapa dosarului** — cerere depusă, în procesare, în soluționare, soluție pronunțată
- **Termenul de soluționare** — detectează automat când Registrul Comerțului mută termenul în ziua următoare (situație frecventă din cauza aglomerației)
- **Soluția pronunțată** — admis, respins, amânat etc.
- **Termenul de eliberare** — pentru dosarele finalizate

### Funcționalități:
- ✅ **Verificare periodică** — la interval configurabil (implicit 120 minute)
- ✅ **Notificări tray** — afișează ce anume s-a schimbat (valoarea veche → cea nouă)
- ✅ **Istoric complet** — toate schimbările înregistrate, cu detalii vechi tăiate / noi evidențiate
- ✅ **Actualizare automată** — verifică și descarcă versiunea nouă direct din aplicație
- ✅ **Multiple dosare** — monitorizează simultan mai multe dosare pentru diverși clienți
- ✅ **Date criptate** — parola ONRC este stocată criptat, exclusiv pe calculatorul tău
- ✅ **Rulează în system tray** — poți închide fereastra, aplicația rămâne activă lângă ceas

---

## ⬇️ Descărcare

| Fișier | Descriere | Dimensiune |
|--------|-----------|------------|
| **[StadiuDosarONRC.exe](https://github.com/DrawbridgeOfficial/StadiuDosarONRC-Releases/releases/download/v1.0.0/StadiuDosarONRC.exe)** | Versiune portabilă — dublu-click și rulează | ~62 MB |

> **Notă:** Aplicația este portabilă — nu necesită instalare. Descarcă fișierul `.exe`, rulează-l și gata.

---

## 🖥️ Cerințe de sistem

- **Sistem de operare:** Windows 10 / Windows 11 (64-bit)
- **Browser:** Google Chrome trebuie să fie instalat (aplicația folosește Selenium pentru a controla automat browserul)
- **Cont:** Ai nevoie de un cont activ pe [myportal.onrc.ro](https://myportal.onrc.ro)

---

## 🚀 Cum se utilizează

### Prima utilizare:
1. Descarcă și rulează `StadiuDosarONRC.exe`
2. Click pe **Setări** → introdu utilizatorul și parola de la contul ONRC → **Salvează**
   (Parola se salvează criptat, doar pe calculatorul tău)
3. Click pe **+ Adaugă dosar** pentru fiecare dosar pe care vrei să-l monitorizezi
   (Client, Număr dosar, An, opțional Județ)
4. Click pe **Verifică acum** pentru un prim test
5. Lasă aplicația deschisă — verificarea automată rulează la intervalul setat

### Utilizare curentă:
- Aplicația verifică automat la intervalul setat
- Când detectează o schimbare → afișează o notificare pe ecran cu detaliile
- Double-click pe un dosar → vezi stadiul curent + istoricul schimbărilor
- Butonul **Verifică acum** → forțează o verificare imediată

---

## 🔒 Notă de confidențialitate

**Stadiu Dosar ONRC** respectă confidențialitatea datelor tale:

### Ce date stochează aplicația:
- **Credențiale ONRC** (utilizator + parolă) — stocate **criptat** local pe calculatorul tău, în fișierul `data/credentials.enc`. Nu sunt trimise niciodată către terți.
- **Date de monitorizare** (dosare, stadii, istoric) — stocate local în baza de date SQLite (`data/monitorizare.db`).

### Ce NU face aplicația:
- ❌ NU trimite date către niciun server extern, în afară de `myportal.onrc.ro` / `sso.onrc.ro` (portalul oficial ONRC)
- ❌ NU colectează date de utilizare (telemetrie)
- ❌ NU plasează cookie-uri
- ❌ NU trimite informații către dezvoltator sau terți
- ❌ NU accesează alte site-uri sau aplicații

### Ce date trimite:
- **Doar** cereri către portalul oficial `myportal.onrc.ro` pentru autentificare și interogarea dosarelor
- **Doar** cereri către `api.github.com` pentru verificarea actualizărilor (opțional, doar numărul versiunii)

### Drepturile tale:
- Toate datele rămân exclusiv pe calculatorul tău
- Poți șterge oricând fișierul `.exe` și folderul `data/` pentru eliminarea completă a datelor
- Aplicația nu necesită cont creat sau înregistrare

---

## 📜 Acord de licență de utilizare

### SOFTWARE GRATUIT — Termeni și condiții

Prin descărcarea și utilizarea acestei aplicații, confirmați că ați citit, înțeles și acceptați termenii de mai jos.

**1. Licență de utilizare**
Aceasta este o licență de utilizare gratuită (freeware). Vi se acordă dreptul neexclusiv, netransferabil și revocabil de a utiliza Aplicația pe un număr nelimitat de dispozitive, în scop personal sau comercial.

**2. Restricții**
Nu aveți voie să:
- Decompilați, dezasamblați sau efectuați reverse engineering asupra Aplicației
- Vindeți, închiriați sau sublicențiați Aplicația către terți
- Eliminați sau modificați notificările de copyright
- Distribuiți Aplicația într-o formă modificată sau derivată
- Utilizați Aplicația în scopuri ilegale sau neautorizate

**3. Limitarea răspunderii**
Aplicația este furnizată „CA ATARE", FĂRĂ GARANȚII de orice fel. Dezvoltatorul nu este răspunzător pentru daune directe, indirecte, incidentale sau consecvente, pierderi de date, sau nerespectarea obligațiilor față de autorități.

Utilizatorul este responsabil să verifice corectitudinea informațiilor extrase din portalul ONRC.

**4. Date cu caracter personal**
Aplicația stochează date de autentificare criptat, exclusiv pe dispozitivul dumneavoastră. Acestea NU sunt transmise către dezvoltator sau terți.

**5. Lege aplicabilă**
Acest acord este guvernat de legile României.

---

## ❓ Întrebări frecvente

**Nu reușesc să mă autentific. Ce fac?**
Verifică utilizatorul și parola în Setări. Dacă portalul ONRC a schimbat structura paginii, poate fi nevoie de o actualizare — aplicația verifică automat dacă există versiuni noi.

**Aplicația nu detectează schimbările.**
Asigură-te că dosarul există în portal și că datele introduse (număr, an, județ) sunt corecte. Încearcă un click pe „Verifică acum".

**Cumdezinstalez aplicația?**
Șterge fișierul `StadiuDosarONRC.exe` și, opțional, folderul `data/` din directorul unde se află aplicația.

---

## 📞 Suport

Pentru întrebări sau probleme, deschide un [issue](https://github.com/DrawbridgeOfficial/StadiuDosarONRC-Releases/issues) pe acest repository.

---

© 2026 Drawbridge — Toate drepturile rezervate
