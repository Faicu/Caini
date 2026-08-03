# Cum public „Ghid dresaj canin” pe Google Play

Aplicația e gata ca **PWA** (Progressive Web App) — un site care se comportă ca o aplicație
nativă: funcționează offline, are icon propriu, se instalează pe telefon. Acesta este cel
mai simplu drum spre Play Store fără să scrii cod Android/Kotlin.

Ai nevoie de 3 lucruri: **(1)** aplicația găzduită pe un domeniu HTTPS, **(2)** un pachet
Android (.aab) generat automat, **(3)** un cont de dezvoltator Google Play.

---

## Pasul 1 — Găzduirea e deja gata ✅

Aplicația e deja live prin **GitHub Pages**, la adresa:

**https://chitubgd-lang.github.io/Caini/**

Nu mai trebuie să faci nimic la acest pas — de fiecare dată când se face `git push` pe
branch-ul `main`, site-ul se actualizează automat în 1-2 minute.

---

## Pasul 2 — Generează pachetul Android (.aab) cu PWABuilder

1. Mergi pe **https://www.pwabuilder.com**
2. Introdu adresa **https://chitubgd-lang.github.io/Caini/** și apasă „Start”
3. PWABuilder analizează automat `manifest.json` — ar trebui să apară scor verde/bun
   (icoanele, numele și culorile sunt deja configurate corect în acest proiect)
4. Alege platforma **Android**, apoi generează pachetul **.aab** (Android App Bundle)
5. Descarcă arhiva — conține fișierul `.aab` plus un fișier `assetlinks.json`

### Important — verificarea de proprietate a domeniului
Pentru ca aplicația din Play Store să se deschidă fără bara de browser (ca o aplicație
reală), trebuie să urci fișierul `assetlinks.json` primit de la PWABuilder la adresa:
**https://chitubgd-lang.github.io/Caini/.well-known/assetlinks.json**

Pentru asta, creezi în repo folderul `.well-known/` cu fișierul `assetlinks.json` înăuntru
și dai push — GitHub Pages îl publică automat la adresa de mai sus. (Trimite-mi conținutul
fișierului descărcat de la PWABuilder și ți-l urc eu direct în repo.)

---

## Pasul 3 — Cont de dezvoltator Google Play

1. Mergi pe **https://play.google.com/console** și creează cont (taxă unică de 25 USD)
2. Verificarea identității poate dura de la câteva ore până la 2-3 zile
3. Creează o aplicație nouă → încarcă fișierul `.aab` din Pasul 2

## Pasul 4 — Fișa aplicației (obligatorii pentru publicare)

- **Icon** de 512×512 — ai deja `icons/icon-512.png` în acest proiect
- **Screenshot-uri** — minim 2, făcute din telefon după ce instalezi aplicația
  (deschide **https://chitubgd-lang.github.io/Caini/** în Chrome pe Android → meniu →
  „Instalează aplicația”)
- **Descriere scurtă și lungă** — poți folosi textul din secțiunea de mai jos
- **Politică de confidențialitate** — obligatorie chiar și pentru o app simplă. Deoarece
  aplicația nu colectează date (progresul se salvează doar local, pe telefon), poți genera
  una gratuit pe **https://app-privacy-policy-generator.firebaseapp.com** (poți găzdui
  și tu rezultatul tot prin GitHub Pages, în același repo — trimite-mi textul și ți-l adaug).
- **Chestionar de clasificare a conținutului** — completezi în consolă; pentru o aplicație
  educațională fără conținut sensibil, rezultatul e „Everyone”.
- **Categorie sugerată:** Educație sau Lifestyle.

### Text sugerat pentru fișa din Store
**Titlu:** Ghid dresaj canin
**Descriere scurtă:** Ghid complet de dresaj canin: comenzi de bază, comportament și pui.
**Descriere lungă:**
> Ghid dresaj canin este un ghid practic și complet de dresaj pentru câini, gândit pentru
> stăpâni la orice nivel de experiență. Găsești pas-cu-pas comenzile de bază (stai,
> culcat, rămâi, vino, la picior), soluții pentru probleme frecvente de comportament
> (lătrat, tras de lesă, anxietate de separare) și un ghid dedicat dresajului pentru
> pui în primele luni esențiale. Fiecare lecție are pași clari, greșeli de evitat și
> recomandări pentru când e nevoie de un specialist. Include un tracker de progres
> care funcționează offline, direct pe telefonul tău.

---

## Pasul 5 — Trimite spre revizuire

După completarea fișei, apasă „Trimite spre revizuire” în Play Console. Revizuirea
Google durează de obicei **1-3 zile**. După aprobare, aplicația e live pe Play Store.

---

## Ce pot face eu pentru tine în acest proces

Pot să:
- adaug orice fișier necesar în repo (ex. `assetlinks.json`, pagina de politică de
  confidențialitate) și să fac push, ca să apară automat pe GitHub Pages
- ajustez `manifest.json` sau iconițele dacă PWABuilder cere modificări

Nu pot să:
- creez sau plătesc contul de Google Play Console în locul tău (necesită cardul și
  identitatea ta)
- rulez eu PWABuilder — e un serviciu web care cere interacțiune directă din browserul tău
- trimit aplicația spre revizuire — se face din contul tău de Play Console

---

## Actualizarea conținutului pe viitor

Tot conținutul ghidului (comenzi, probleme de comportament, dresaj pui) este în fișierul
`index.html`, în interiorul `<script>`, în obiectul `DATA`. Poți edita textele direct
acolo (sau îmi ceri mie), redistribui fișierele către hosting — iar aplicația se
actualizează automat pe telefoanele utilizatorilor (nu e nevoie de o versiune nouă în
Play Store pentru simple modificări de text, doar pentru schimbări de icon/nume/
funcționalitate majoră).
