GRIM OPPORTUNITY HUB
MASTER VERIFIED OPPORTUNITY FEED

Versione operativa definitiva


==================================================
1. SCOPO
==================================================

Aggiorna ogni giorno GRIM Opportunity Hub.

Repository:
grimdcc74-netizen/grim-opportunity-data

Branch:
main

Feed pubblico:
data/current.json

Il sistema deve cercare, verificare, confrontare e organizzare:

1. WORK
Opportunità professionali VFX / CGI / AI / Visual Development.

2. ART
Open call, residenze, grant, commissioni, mostre, festival,
collaborazioni e opportunità artistiche.

L'obiettivo non è soltanto trovare annunci.

Per ogni opportunità devo poter capire rapidamente:

- quanto è compatibile con il mio profilo;
- quanto sono già pronti i miei materiali;
- se posso candidarmi;
- dove devo candidarmi;
- qual è il link esatto dell'application;
- entro quando;
- quanti giorni mancano;
- cosa devo preparare;
- cosa mi manca;
- eventuali requisiti bloccanti;
- costi;
- compensi;
- grant;
- contatti ufficiali;
- prossima azione concreta.


==================================================
2. FONTI
==================================================

Usa prioritariamente fonti PRIMARY:

- sito ufficiale dell'azienda;
- career page ufficiale;
- ATS ufficiale;
- sito ufficiale del museo;
- fondazione;
- università;
- istituzione pubblica;
- associazione;
- festival;
- residenza;
- programma europeo;
- portale ufficiale della call;
- portale ufficiale di application.

Job board, database, motori di ricerca, social professionali,
aggregatori e portali autorevoli possono essere utilizzati per:

DISCOVERY
oppure

CORROBORATION

ma non devono sostituire una fonte primaria disponibile.


==================================================
3. LIVELLI DI VERIFICA
==================================================

verification:

PRIMARY
Fonte ufficiale controllata direttamente.

CORROBORATED
Informazione confermata da fonti affidabili ma non completamente
verificata sulla fonte primaria.

TO_VERIFY
Informazione incompleta o non sufficientemente verificata.

Una voce con verification: TO_VERIFY o liveStatus: TO_VERIFY non deve essere
presentata come opportunità verificata LIVE. applicationStatus è indipendente:
una call ufficialmente aperta può essere LIVE con applicationStatus: TO_VERIFY.


==================================================
4. REGOLE ANTI-FALSO-POSITIVO
==================================================

Una pagina esistente non significa automaticamente che
l'opportunità sia ancora aperta.

Per classificare una opportunità come LIVE deve essere verificata
almeno una delle seguenti condizioni:

- application form attivo;
- pulsante Apply attivo;
- ATS accetta ancora candidature;
- deadline futura verificata;
- pagina ufficiale dichiara esplicitamente che la call è aperta;
- email ufficiale indicata per l'invio delle candidature.

Se la call è verificata come aperta sulla fonte ufficiale ma il modulo non è
verificabile: liveStatus può restare LIVE, applicationStatus deve essere
TO_VERIFY e applicationUrl deve essere null. Un login accessibile non prova
che il modulo dietro autenticazione sia accessibile o accetti candidature.
Un canale EMAIL ufficiale verificato può avere applicationStatus: OPEN e
applicationUrl: null: l'assenza di un modulo web non è un'anomalia.

Se il form è chiuso:
CLOSED.

Se la deadline è scaduta:
CLOSED.

Se la pagina esiste ma non è possibile stabilire se accetta ancora
candidature:
TO_VERIFY.


==================================================
5. DATABASE E IDENTIFICATORI
==================================================

Prima di ogni aggiornamento:

- leggi sempre data/current.json;
- confronta i risultati con il giorno precedente;
- non creare duplicati;
- conserva sempre gli ID esistenti;
- conserva firstSeen;
- aggiorna lastVerifiedAt;
- aggiorna generatedAt;
- mantieni la versione più recente verificata.

In testa al JSON mantieni:

schemaVersion

Usa:

schemaVersion: "2.0"

Gli ID devono essere permanenti.

Non usare numerazioni progressive come ID.

Per l'ordinamento visuale usa:

displayOrder

displayOrder può cambiare.
id non deve cambiare.


==================================================
6. WORK - AZIENDE PRIORITARIE
==================================================

Controlla prioritariamente:

1. EDI Effetti Digitali Italiani
2. 22DOGS
3. BAND VFX
4. Proxima Milano
5. altre post-produzioni e VFX house rilevanti di Milano e Lombardia

Controlla anche opportunità:

- italiane;
- europee;
- internazionali;
- remote;

quando hanno forte compatibilità con il profilo.


==================================================
7. EDI - AREE PRIORITARIE
==================================================

Per EDI controlla sempre:

- Art Department
- 2D / Matte Painting
- Concept Art
- Character Design
- Storyboard Artist
- Visual Development
- AI / Generative / RnD
- CG quando pertinente
- Art Supervision
- Visual Development Supervision
- VFX / CG Supervision quando pertinente

Non modificare mai il titolo ufficiale.

Esempio:

title:
"2D - Candidatura Spontanea"

può avere:

category:
"2D / Matte Painting"

ma il title ufficiale resta invariato.


==================================================
8. PROFILO PROFESSIONALE DI RIFERIMENTO
==================================================

Profilo Senior VFX / CG Artist.

Priorità:

- Digital Matte Painting
- Concept Art
- Character Design
- Storyboard
- Art Direction
- Visual Development
- CGI
- Generative AI
- AI-assisted workflows
- Art Development
- Visual Development Supervision
- Art Supervision
- VFX / CG Supervision
- Advertising Post-production

Compositing può essere considerato come competenza secondaria o
adiacente, ma non deve sostituire Matte Painting, Concept e
Visual Development come priorità.


==================================================
9. DE-PRIORITIZZAZIONE WORK
==================================================

De-prioritizza:

- HR;
- amministrazione;
- IT generico;
- producer-only;
- ruoli junior non pertinenti;
- posizioni esclusivamente gestionali;
- ruoli fortemente tecnici lontani dal profilo;
- ruoli senza componente visiva significativa.

Non escludere automaticamente una posizione per un requisito mancante.

Se esiste forte compatibilità generale:
mantieni l'opportunità e segnala il gap.


==================================================
10. DATI WORK
==================================================

Ogni WORK deve contenere quando disponibili:

id
displayOrder
area
title
org

country
city
location
remotePolicy

employmentType
category

publishedAt
publishedDateSource

firstSeen
lastVerifiedAt
sourceCheckedAt
lastChangedAt

liveStatus
applicationStatus
changeType
changeSummary

tag
isNew

sourceType
sourceUrl
canonicalUrl

applicationUrl
directApplyUrl
applicationMethod
applicationPortal
requiresAccount
applicationSteps

deadline
deadlineTimezone
deadlineEuropeRome
daysRemaining
urgency

eligibility
requiredExperience
requiredLanguages
requiredLanguageLevel
requiredSoftware

materials
materialsFormat
materialsDeadline

applicationFeeAmount
applicationFeeCurrency

compensationAmount
compensationCurrency
compensationType
salaryOrCompensation

contactStatus
contactName
contactRole
contactEmail
contactPhone
questionsOrContactUrl

verification
verificationNotes


==================================================
11. SOURCE TYPE
==================================================

sourceType può essere:

EMPLOYER
ATS
INSTITUTION
OFFICIAL_CALL
OFFICIAL_EVENT
SECONDARY


==================================================
12. CHANGE TRACKING
==================================================

changeType può essere:

NEW
UPDATED
UNCHANGED
CLOSED
REOPENED

Per ogni cambiamento significativo genera:

changeSummary

Esempi:

"Deadline prorogata dal 20 al 27 settembre."

"Application form non più disponibile."

"Nuovi requisiti software aggiunti."

"Vacancy riaperta."

CHANGED nel report corrisponde a cambiamenti sostanziali (UPDATED): deadline,
stato, apertura/chiusura, application URL, requisiti, materiali richiesti,
fee, funding/compenso, località, employment type o informazioni operative.
Non classificare CHANGED per soli lastVerifiedAt, sourceCheckedAt,
generatedAt, displayOrder o altri metadati tecnici.
L’arricchimento iniziale delle 14 schede può restare CHANGED nel report del
17 settembre 2026; dalle esecuzioni successive applicare questa distinzione.


==================================================
13. isNew
==================================================

isNew deve essere true soltanto nel primo report nel quale
la nuova vacancy viene rilevata.

Dal report giornaliero successivo:

isNew: false

Non lasciare una opportunità NEW per più giorni.

SPONTANEA:
isNew: false

TALENT_POOL:
isNew: false


==================================================
14. ART - AMBITI DA MONITORARE
==================================================

Cerca opportunità relative a:

- contemporary art
- musei
- fondazioni
- istituzioni pubbliche
- università
- residencies
- grants
- commissions
- photography
- street art
- graffiti
- writing
- public art
- printmaking
- engraving
- media art
- CGI art
- AI art
- moving image
- installation
- Hip Hop culture
- urban culture
- community-based practice
- manifestazioni
- raduni
- convention
- mostre
- art talent
- call per artisti
- open call
- festival
- eventi artistici
- aziende che cercano artisti
- associazioni artistiche
- recruiting Art
- residenze artistiche italiane
- residenze artistiche internazionali
- commissioni pubbliche
- site-specific
- arte e scienza
- programmi interdisciplinari
- programmi europei
- opportunità di produzione


==================================================
15. PRIORITÀ ART
==================================================

Preferisci:

- musei;
- fondazioni;
- università;
- istituzioni pubbliche;
- Creative Europe;
- programmi europei;
- festival consolidati;
- residenze riconosciute;
- programmi finanziati;
- call gratuite;
- low-fee;
- grant;
- artist fee;
- production budget;
- viaggio coperto;
- studio coperto;
- alloggio coperto;
- commissioni con budget reale.

De-prioritizza:

- vanity gallery;
- pay-to-exhibit poco trasparenti;
- fee elevate senza adeguato ritorno;
- call incompatibili per età;
- call incompatibili con artisti established;
- opportunità prive di fonte verificabile.


==================================================
16. DATI ART
==================================================

Ogni ART deve contenere quando disponibili:

id
displayOrder
area
title
org

country
city
location

publishedAt
publishedDateSource
firstSeen
lastVerifiedAt
sourceCheckedAt
lastChangedAt

deadline
deadlineTimezone
deadlineEuropeRome
daysRemaining
urgency

materialsDeadline

liveStatus
applicationStatus

changeType
changeSummary

tag
isNew

summary

eligibility
requiredLanguages
requiredLanguageLevel

materials
materialsFormat

applicationMethod
applicationPortal
requiresAccount
applicationSteps

sourceType
sourceUrl
canonicalUrl
applicationUrl
directApplyUrl

applicationFeeAmount
applicationFeeCurrency

funding

compensationAmount
compensationCurrency
compensationType
salaryOrCompensation

contactStatus
contactName
contactRole
contactEmail
contactPhone
questionsOrContactUrl

verification
verificationNotes


==================================================
17. APPLICATION URL
==================================================

Distinguere sempre:

sourceUrl
pagina ufficiale che descrive l'opportunità.

applicationUrl
pagina esatta nella quale viene realmente presentata
la candidatura.

canonicalUrl
URL ufficiale stabile dell'opportunità.

directApplyUrl
per compatibilità con il sistema attuale replica applicationUrl
quando disponibile.

Non usare come applicationUrl una homepage generica se esiste
un link più diretto.


==================================================
18. TEST APPLICATION URL
==================================================

Prima di salvare applicationUrl verifica:

- non restituisce 404;
- corrisponde alla stessa opportunità;
- non è semplicemente la homepage;
- il form è ancora accessibile;
- se serve login, indicalo;
- se il form è chiuso, non classificare LIVE.

Non considerare valido un applicationUrl che punta soltanto al dominio base
di un servizio. Esempi non validi: https://forms.gle/ e
https://docs.google.com/forms/. Il link deve identificare uno specifico modulo.
Se incompleto, rotto o restituisce errore, non salvarlo come applicationUrl;
cercare il link completo sulla fonte ufficiale. Se non disponibile o se il
modulo non è verificabile, usare applicationUrl: null e
applicationStatus: TO_VERIFY, segnalando il problema nel report.
Non tentare login né aggirare blocchi o permessi.

Non effettuare materialmente una candidatura.


==================================================
19. APPLICATION METHOD
==================================================

applicationMethod può essere:

FORM
EMAIL
PORTAL
OTHER

Se tramite email:
salva contactEmail.

Se tramite piattaforma:
salva applicationPortal.

Se richiede registrazione:
requiresAccount: true.

Se non è possibile verificarlo:
requiresAccount: null.


==================================================
20. APPLICATION STEPS
==================================================

Durante le esecuzioni automatiche non effettuare login e non inserire
credenziali. Se l’application richiede autenticazione: requiresAccount: true.
Descrivere il login come passaggio che dovrà eseguire l’utente.

Quando possibile genera applicationSteps, intesi esclusivamente come
istruzioni per l’utente, non azioni da eseguire automaticamente.

Esempio:

1. Aprire applicationUrl.
2. Creare account.
3. Compilare il profilo.
4. Caricare CV.
5. Caricare portfolio/reel.
6. Allegare lettera.
7. Verificare i documenti.
8. Inviare candidatura.


==================================================
21. DEADLINE
==================================================

Conserva sempre:

deadline originale

deadlineTimezone

deadlineEuropeRome

daysRemaining

urgency

Classifica:

URGENT
<= 3 giorni.

SOON
<= 7 giorni.

NORMAL
> 7 giorni.

Se il fuso non è verificato:
non inventare la conversione.


==================================================
22. MATERIALI
==================================================

Registra con precisione quando richiesti:

- CV
- Artist CV
- Portfolio
- Showreel
- Reel
- Bio
- Artist Statement
- Motivation Letter
- Cover Letter
- Project Proposal
- Budget
- Timeline
- Recommendation Letter
- References
- fotografie
- video
- documentazione amministrativa
- link
- altri allegati.

Per ogni materiale registra quando disponibile:

- formato;
- dimensione massima;
- numero pagine;
- numero immagini;
- durata video;
- lingua;
- template ufficiale.


==================================================
23. COMPENSI E COSTI
==================================================

Normalizza quando possibile:

applicationFeeAmount
applicationFeeCurrency

compensationAmount
compensationCurrency

compensationType:

SALARY
ARTIST_FEE
GRANT
PRODUCTION_BUDGET
TRAVEL_SUPPORT
ACCOMMODATION
MIXED
NONE
UNKNOWN

Mantieni anche una descrizione sintetica:

salaryOrCompensation
oppure
funding


==================================================
24. CONTATTI
==================================================

Cerca esclusivamente contatti professionali resi pubblici
dall'organizzazione.

Salva:

contactName
contactRole
contactEmail
contactPhone
questionsOrContactUrl

contactStatus:

AVAILABLE
NOT_PUBLISHED
NOT_REQUIRED

Non inventare email.

Non dedurre email dal dominio.

Non cercare numeri personali non pubblici.


==================================================
25. COMPATIBILITY SCORING
==================================================

Per ogni opportunità genera separatamente:

fitScore
materialsFitScore
priorityScore
applicationReadiness
applicationEffort


==================================================
26. FIT SCORE
==================================================

fitScore misura la compatibilità con esperienza e competenze.

5/5
compatibilità molto alta.

4/5
compatibilità alta.

3/5
compatibilità media.

2/5
compatibilità bassa.

1/5
compatibilità molto bassa.

Mantieni:

fitReason
matchedSkills
gaps
dealBreakers


==================================================
27. DEAL BREAKERS
==================================================

dealBreakers deve contenere eventuali requisiti potenzialmente
escludenti.

Esempi:

- limite under 35;
- cittadinanza obbligatoria;
- residenza obbligatoria;
- software specialistico obbligatorio;
- lingua certificata;
- titolo accademico indispensabile;
- esperienza specifica non posseduta.

Un dealBreaker deve derivare da una condizione dichiarata,
non da una supposizione.


==================================================
28. MATERIALS FIT SCORE
==================================================

materialsFitScore misura quanto i materiali realmente disponibili
sono già adatti.

5/5
praticamente pronta.

4/5
quasi pronta.

3/5
parzialmente pronta.

2/5
diversi materiali da preparare.

1/5
materiali largamente insufficienti.

Se non è stato possibile verificare i materiali:

materialsFitScore: null
materialsFitStatus: NOT_VERIFIED

Non inventare la disponibilità di un materiale.

Mantieni:

matchedMaterials
missingMaterials
materialsToAdapt
recommendedMaterials
materialsFitNotes


==================================================
29. RECOMMENDED MATERIALS
==================================================

recommendedMaterials indica quali materiali sarebbe strategicamente
meglio utilizzare per quella candidatura.

Esempio:

- CV VFX Senior
- Portfolio Digital Matte Painting
- Concept Art selection
- Character Design selection
- Showreel advertising
- Artist CV
- Bio ENG 250
- Artist Statement


==================================================
30. APPLICATION READINESS
==================================================

La disponibilità dei materiali personali non determina se la call è aperta.
Non usare APPLY NOW = NO soltanto perché i materiali personali sono N/V.
Per MMCA e ogni altra call aperta mostrare APPLICATION OPEN: YES anche con
MATERIAL READINESS: NOT_VERIFIED; verificare separatamente APPLICATION ACCESS.
Le valutazioni personali restano nel layer privato, non nel feed pubblico.

applicationReadiness:

READY
Tutto il necessario è disponibile.

PARTIAL
Servono adattamenti o alcuni materiali.

BLOCKED
Manca un requisito/materiale essenziale.

NOT_VERIFIED
Informazioni insufficienti.


==================================================
31. APPLICATION EFFORT
==================================================

applicationEffort:

LOW
candidatura semplice, pochi materiali.

MEDIUM
richiede adattamento o preparazione moderata.

HIGH
richiede progetto, budget, recommendation, numerosi documenti
o lavoro preparatorio importante.


==================================================
32. PRIORITY SCORE
==================================================

priorityScore misura la priorità operativa.

Considera:

- fitScore;
- materialsFitScore;
- deadline;
- autorevolezza organizzazione;
- compenso;
- funding;
- applicationEffort;
- readiness;
- valore professionale;
- valore artistico;
- urgenza.

Non confondere priorityScore con fitScore.

Una opportunità Fit 4 con deadline domani può avere Priority 5.

Una candidatura spontanea Fit 5 senza deadline può avere Priority 3.


==================================================
33. VISUALIZZAZIONE PUNTEGGI
==================================================

Subito sotto il titolo mostra:

Profilo:    ●●●●● 5/5
Materiali:  ●●●●○ 4/5
Prontezza:  PARTIAL
Priorità:   5/5

Poi mostra:

APPLICATION OPEN: YES / NO / TO_VERIFY
APPLICATION ACCESS: YES / NO / TO_VERIFY
MATERIAL READINESS: READY / PARTIAL / BLOCKED / NOT_VERIFIED
APPLY PRIORITY: URGENT / HIGH / NORMAL / LOW

Deadline:
...

Mancano:
...

Application:
applicationUrl


Se Materials non verificato:

Materiali: N/V


==================================================
34. WHY THIS SCORE
==================================================

Mostra sempre:

fitReason
materialsFitReason

Massimo 1-2 frasi ciascuno.

I punteggi devono essere spiegabili.


==================================================
35. ACTION REQUIRED
==================================================

Per ogni opportunità prioritaria mostra:

APPLICATION OPEN

APPLICATION ACCESS

MATERIAL READINESS

APPLY PRIORITY

deadline

daysRemaining

applicationUrl

applicationMethod

requiresAccount

applicationEffort

materials

matchedMaterials

missingMaterials

materialsToAdapt

recommendedMaterials

applicationFee

compensation / funding

eligibility

matchedSkills

gaps

dealBreakers

contactEmail

contactPhone

NEXT ACTION


NEXT ACTION deve essere concreta.

Esempi:

- Aggiornare il reel.
- Preparare portfolio DMP.
- Richiedere recommendation letter.
- Creare account.
- Preparare artist statement.
- Inviare candidatura.
- Scrivere al referente.
- Verificare requisito linguistico.


==================================================
36. DATI PUBBLICI E DATI PERSONALI
==================================================

data/current.json deve contenere soltanto informazioni
pubbliche sulle opportunità.

Valutazioni personali come:

fitScore
materialsFitScore
matchedMaterials
missingMaterials
materialsToAdapt
materialsFitNotes
dealBreakers personali
applicationReadiness
nextAction

devono idealmente essere mantenute nel layer privato
del sistema e non pubblicate nel repository pubblico.

Finché il layer privato non è operativo,
evita di aggiungere nuovi dati personali sensibili al repository.


==================================================
37. HISTORY
==================================================

history:

date
activeWork
activeArt
newItems
closedItems
changedItems

Conserva massimo 120 giorni.

Non creare history entry per semplici test tecnici.


==================================================
38. REPORT GIORNALIERO
==================================================

Il report deve essere leggibile rapidamente anche da smartphone.

Ordine:

REPORT DATE

APPLY TODAY

URGENT DEADLINES

NEW HIGH FIT

NEW

CHANGED SINCE YESTERDAY

STILL LIVE

WORK

ART

CLOSED

LIVE TO_VERIFY

APPLICATION TO_VERIFY

TOP PRIORITIES

MATERIALS TO PREPARE

CONTACTS


==================================================
39. DATI RIASSUNTIVI
==================================================

Mostra sempre:

- data report;
- nuove opportunità;
- già presenti ancora valide;
- WORK LIVE;
- ART LIVE;
- LIVE (liveStatus: LIVE);
- LIVE TO_VERIFY (liveStatus: TO_VERIFY);
- APPLICATION TO_VERIFY (applicationStatus: TO_VERIFY, anche per call LIVE);
- CLOSED;
- deadline entro 3 giorni;
- deadline entro 7 giorni;
- application pronte;
- application bloccate.

Non presentare un generico TO_VERIFY = 0 se esistono application non verificate.
Per ogni scheda mostrare separatamente APPLICATION OPEN, APPLICATION ACCESS,
MATERIAL READINESS e APPLY PRIORITY.


==================================================
40. ORDINE
==================================================

Prima:

AI / VFX / CGI / Visual Development / WORK

Poi:

ART

Dentro ogni sezione:

1. URGENT
2. priorityScore
3. fitScore
4. NEW
5. deadline
6. STILL LIVE


==================================================
41. PRIVACY
==================================================

Non inserire nel repository pubblico:

- CV privati;
- portfolio privati;
- email personali;
- telefoni personali;
- recommendation letter;
- note personali;
- password;
- token;
- API key;
- credenziali;
- contenuti della memoria privata ChatGPT.

Sono consentiti:

- contatti aziendali pubblici;
- email professionali pubbliche;
- telefoni pubblici dell'organizzazione;
- nomi e ruoli pubblicati;
- source URL;
- application URL;
- FAQ;
- contact page.


==================================================
42. VALIDAZIONE
==================================================

Prima di terminare:

1. valida JSON;
2. controlla schemaVersion;
3. ID univoci;
4. usa sempre org;
5. non usare organization;
6. URL https;
7. sourceUrl verificato;
8. applicationUrl verificato;
9. canonicalUrl coerente;
10. nessun contatto inventato;
11. generatedAt aggiornato;
12. firstSeen preservato;
13. displayOrder valido;
14. deadline corretta;
15. timezone verificato;
16. daysRemaining corretto;
17. applicationStatus coerente;
18. liveStatus coerente;
19. LIVE supportato da prova reale;
20. nessun duplicato;
21. materiali corretti;
22. compensation corretta;
23. privacy rispettata;
24. isNew correttamente aggiornato;
25. eventuali CLOSED rimossi dal feed attivo secondo le regole
    ma mantenuti nello storico.


==================================================
43. GIT
==================================================

Se data/current.json cambia realmente:

crea commit locale:

Daily verified Opportunity Hub update YYYY-MM-DD

Non creare commit inutili.

Non fare push se richiede autorizzazione interattiva.

Non modificare file non necessari.


==================================================
44. LEGENDA OBBLIGATORIA
==================================================

Inserisci SEMPRE questa legenda in fondo al report.


PROFILO

●○○○○ 1/5
Compatibilità molto bassa

●●○○○ 2/5
Compatibilità bassa

●●●○○ 3/5
Compatibilità media

●●●●○ 4/5
Compatibilità alta

●●●●● 5/5
Compatibilità molto alta


MATERIALI

●○○○○ 1/5
Quasi tutto da preparare

●●○○○ 2/5
Materiali molto incompleti

●●●○○ 3/5
Parzialmente pronta

●●●●○ 4/5
Quasi pronta

●●●●● 5/5
Pronta

N/V
Materiali non ancora verificati


PRONTEZZA

READY
Puoi procedere sostanzialmente subito.

PARTIAL
Servono alcuni adattamenti o materiali.

BLOCKED
Manca un elemento indispensabile.

NOT_VERIFIED
Informazioni insufficienti.


URGENZA

URGENT
Deadline entro 3 giorni.

SOON
Deadline entro 7 giorni.

NORMAL
Oltre 7 giorni.


STATO

LIVE
Opportunità verificata e attiva.

TO_VERIFY
Verifica incompleta.

CLOSED
Opportunità chiusa.

NEW
Nuova rispetto al report precedente.

STILL LIVE
Già presente e ancora valida.

CHANGED
Informazioni importanti modificate.


APPLICATION EFFORT

LOW
Candidatura rapida.

MEDIUM
Richiede preparazione moderata.

HIGH
Richiede preparazione significativa.

APPLICATION OPEN
YES: call ufficialmente aperta; NO: chiusa; TO_VERIFY: apertura non verificata.

APPLICATION ACCESS
YES: modulo accessibile verificato o canale email ufficiale verificato.
NO: accesso verificato come chiuso. TO_VERIFY: accesso al modulo non verificato,
anche se è raggiungibile una pagina di login. Non effettuare login automatici.

MATERIAL READINESS
READY / PARTIAL / BLOCKED / NOT_VERIFIED: prontezza dei materiali personali,
indipendente dall’apertura e dall’accessibilità della candidatura.

APPLY PRIORITY
URGENT: azione urgente per scadenza ravvicinata.
HIGH: priorità operativa alta.
NORMAL: priorità ordinaria.
LOW: priorità bassa.

LIVE TO_VERIFY e APPLICATION TO_VERIFY sono conteggi distinti e possono
sovrapporsi: non sommarli come categorie mutuamente esclusive.


==================================================
45. GRIM OPPORTUNITY HUB V3 - FULL DAILY REPORT OVERRIDES
==================================================

Questa sezione definisce il formato operativo V3 del briefing giornaliero.

In caso di conflitto con sezioni precedenti di AGENTS.md, questa sezione
prevale, in particolare su ordinamento del report, classificazione urgenza,
completezza delle opportunità mostrate e profondità di scansione.

Il briefing giornaliero deve essere AUTOSUFFICIENTE.

Non assumere mai che l'utente abbia letto o ricordi i briefing precedenti.

TUTTE le opportunità ancora LIVE devono comparire nel briefing di ogni giorno,
anche se scoperte giorni o settimane prima.

Una opportunità può essere più sintetica se già nota, ma non deve sparire
finché resta LIVE / OPEN e non è scaduta o verificata CLOSED.


==================================================
46. MACRO-AREE DEL REPORT
==================================================

Il report quotidiano deve essere diviso chiaramente in:

00. EXECUTIVE SUMMARY
01. WORK - MILANO / LOMBARDIA
02. WORK - ITALIA
03. WORK - INTERNATIONAL / REMOTE
04. ART - ITALIA
05. ART - EUROPA
06. ART - INTERNATIONAL
07. GRAFFITI / WRITING / STREET ART / MURALISM - ITALIA
08. GRAFFITI / WRITING / STREET ART / MURALISM - EUROPA
09. GRAFFITI / WRITING / STREET ART / MURALISM - INTERNATIONAL
10. OPEN CALL / RESIDENCIES / GRANTS / COMMISSIONS
11. DEADLINES
12. SCAN LOG COMPLETO
13. CHANGES SINCE YESTERDAY
14. LEGENDA

GRAFFITI / WRITING / STREET ART / MURALISM è una macro-area autonoma
e non deve essere nascosta dentro ART.

Per nuove opportunità specificamente graffiti/writing/muralismo è consentito:
area: "graffiti"

Le opportunità storiche già classificate ART non devono essere riclassificate
solo per ragioni cosmetiche, salvo revisione esplicita e sicura.


==================================================
47. DATE DA MOSTRARE SEMPRE
==================================================

Per ogni opportunità mostra distintamente:

DATA PUBBLICAZIONE UFFICIALE
publishedAt, se esposta dalla fonte.

APERTURA CANDIDATURE
applicationOpenDate, se ufficialmente disponibile.

PRESENTE NEL RADAR DAL
firstSeen.

ULTIMA VERIFICA
lastVerifiedAt.

DEADLINE
deadline originale.

DEADLINE ORA ITALIANA
deadlineEuropeRome, quando verificabile.

GIORNI MANCANTI
daysRemaining.

Non confondere mai firstSeen con publishedAt o applicationOpenDate.

Se una data ufficiale non è esposta, scrivere chiaramente:
"non esposta dalla fonte".

applicationOpenDate deve essere aggiunto allo schema pubblico
e deve restare null quando non verificabile.


==================================================
48. URGENZA V3
==================================================

La classificazione urgenza V3 sostituisce la classificazione precedente.

CRITICAL
0-3 giorni alla deadline.

URGENT
4-7 giorni.

SOON
8-14 giorni.

ACTIVE
15-30 giorni.

LONG_RANGE
oltre 30 giorni.

NO_DEADLINE
talent pool, candidatura spontanea o opportunità permanente.

Una opportunità NO_DEADLINE con fit molto alto resta visibile,
ma non deve superare automaticamente una opportunità equivalente
con deadline imminente.


==================================================
49. ORDINAMENTO PER PRIORITÀ REALE
==================================================

Dentro ogni sezione ordina considerando insieme:

1. fitScore / compatibilità;
2. priorityScore / importanza operativa;
3. deadline;
4. daysRemaining;
5. autorevolezza dell'organizzazione;
6. compensation / grant / funding;
7. applicationReadiness;
8. eventuali dealBreakers.

La priorità deve essere spiegabile.

Una opportunità scoperta settimane prima può essere la priorità numero 1
se oggi è più importante, più compatibile o più vicina alla deadline.

NEW non prevale automaticamente su una opportunità già nota.


==================================================
50. SCHEDA COMPLETA DI OGNI OPPORTUNITÀ
==================================================

Ogni opportunità deve essere leggibile senza cercare informazioni altrove.

Mostrare, quando disponibili:

TITOLO
ORGANIZZAZIONE

Profilo: punteggio 1-5 a pallini
Materiali: punteggio 1-5 a pallini oppure N/V
Priorità: 1-5
Prontezza: READY / PARTIAL / BLOCKED / NOT_VERIFIED

Stato:
LIVE / TO_VERIFY / CLOSED

Tipo:
VACANCY / SPONTANEA / TALENT_POOL / OPEN_CALL / RESIDENCY / GRANT /
COMMISSION / FESTIVAL / GRAFFITI_JAM / MURAL_CALL / OTHER

Località
Remote policy
Data pubblicazione
Apertura candidature
Presente nel radar dal
Ultima verifica
Deadline
Deadline ora italiana
Giorni mancanti
Urgenza

Sintesi breve ma sufficiente
Perché è compatibile
Gap
Deal breaker

Materiali richiesti
Formati
Fee
Compenso / Grant / Funding

Metodo candidatura
Account necessario

Contatto ufficiale
Email ufficiale
Telefono ufficiale

NEXT ACTION concreta.


==================================================
51. LINK DENTRO LA SCHEDA
==================================================

I link devono stare SEMPRE dentro la scheda della relativa opportunità.

Mostrare, quando disponibili:

FONTE UFFICIALE:
sourceUrl

APPLY / APPLICATION:
applicationUrl oppure metodo EMAIL se la candidatura avviene via email.

CONTATTI / FAQ:
questionsOrContactUrl

Non creare una lista di link separata dal corpo del report.

Non costringere l'utente a cercare il link in un'altra sezione.


==================================================
52. OPPORTUNITÀ GIÀ PRESENTI
==================================================

Una opportunità già presente e ancora LIVE deve continuare a comparire
ogni giorno.

Deve mostrare almeno:

- title;
- org;
- fit score;
- materials score o N/V;
- priority;
- firstSeen;
- publishedAt;
- applicationOpenDate;
- lastVerifiedAt;
- deadline;
- daysRemaining;
- urgency;
- location;
- liveStatus;
- applicationStatus;
- sourceUrl;
- applicationUrl o metodo di candidatura;
- materials;
- fee;
- funding / compensation;
- contactEmail;
- contactPhone;
- NEXT ACTION.

Può avere una sintesi più corta delle NEW.

VIETATO usare formulazioni come:
"rimane nello storico"
oppure
"non la duplico perché era nel briefing precedente".

Lo storico non sostituisce il briefing corrente.


==================================================
53. NEW E CHANGED
==================================================

NEW identifica soltanto opportunità entrate nel radar dall'ultimo report.

Le NEW devono comparire anche nella loro sezione tematica/geografica.

CHANGED deve essere una informazione aggiuntiva e non deve sostituire
la scheda completa dell'opportunità.

La sezione CHANGES SINCE YESTERDAY viene DOPO il report completo e mostra:
NEW
UPDATED
CLOSED
REOPENED
DEADLINE_CHANGED
APPLICATION_CHANGED


==================================================
54. WORK - MILANO / LOMBARDIA: SCANSIONE OBBLIGATORIA
==================================================

Milano / Lombardia ha priorità speciale.

Ogni giorno mostra:

A. tutte le opportunità LIVE pertinenti;
B. tutte le candidature spontanee pertinenti;
C. tutti i talent pool pertinenti;
D. l'elenco completo degli studi realmente controllati quel giorno.

Per ogni studio controllato mostra:

STUDIO
STATUS SCAN
RISULTATO
ULTIMA VERIFICA
URL ufficiale quando disponibile.

Status scan consentiti:

SCANNED - OPPORTUNITY_FOUND
SCANNED - NO_VACANCY
SCANNED - NO_MATCH
TO_VERIFY
ACCESS_ERROR
LOGIN_REQUIRED

Non usare frasi generiche come:
"sono state controllate altre realtà".

Mostra i nomi effettivamente scansionati.

Mantieni priorità speciale su EDI, 22DOGS, BAND VFX e Proxima Milano,
ma amplia quotidianamente la scansione alle altre post-produzioni,
VFX house, CGI studio, finishing/post e studi creativi pertinenti
di Milano e Lombardia.


==================================================
55. WORK - ITALIA
==================================================

Scansiona quotidianamente anche studi italiani fuori Milano.

Priorità disciplinari:

VFX
CGI
AI / Generative
Digital Matte Painting
Concept Art
Visual Development
Character Design
Storyboard
Art Department
CG Supervision
VFX Supervision
Advertising Post-production

Non limitare la ricerca alle aziende già presenti nel feed.


==================================================
56. WORK - INTERNATIONAL / REMOTE
==================================================

Effettua una ricerca internazionale quotidiana specifica per:

REMOTE WORLDWIDE
REMOTE EUROPE
FREELANCE REMOTE
HYBRID EUROPE

Ruoli prioritari:

AI Creative
Generative AI
VFX
CGI
Digital Matte Painting
Environment
Concept Art
Character Design
Storyboard
Visual Development
Art Department
CG Supervisor
VFX Supervisor

Includi talent pool e freelance pool rilevanti.

Non limitare la ricerca internazionale alle aziende già note.


==================================================
57. ART - SCANSIONE AMPIA
==================================================

ART non deve essere limitata a 2 nuove opportunità o a una top 5.

Scansiona un numero ampio di fonti e mostra nel report tutte le opportunità
LIVE pertinenti.

Dividi sempre:

ART - ITALIA
ART - EUROPA
ART - INTERNATIONAL

Categorie da monitorare:

OPEN CALL
RESIDENCIES
GRANTS
COMMISSIONS
PUBLIC ART
PHOTOGRAPHY
VIDEO
MEDIA ART
DIGITAL ART
AI ART
CGI ART
INSTALLATION
PRINTMAKING
ENGRAVING
PAINTING
SCULPTURE
SITE-SPECIFIC
ART & SCIENCE
COMMUNITY ART
FESTIVALS
EXHIBITIONS

Non limitarti alle novità del giorno.


==================================================
58. GRAFFITI / WRITING / STREET ART / MURALISM
==================================================

Questa è una macro-area autonoma.

Dividi sempre:

ITALIA
EUROPA
INTERNATIONAL

Ricerca esplicitamente anche con query equivalenti a:

graffiti writer application
graffiti jam
writing jam
style writing
mural open call
street art open call
urban art festival application
artist wall application
mural commission
public art mural
Meeting of Styles application
live painting call
street art residency
graffiti festival
urban art residency
mural festival artist application

Includi anche:

- jam;
- festival;
- meeting;
- convention;
- wall commission;
- artist registration;
- mural project;
- live painting;
- eventi rilevanti di networking;

anche senza grant economico quando hanno reale valore per writing,
muralismo, street art o networking professionale.


==================================================
59. PROFONDITÀ MINIMA DELLA SCANSIONE
==================================================

L'obiettivo non è produrre soltanto 5 risultati.

L'obiettivo è effettuare una ricerca ampia PRIMA della selezione.

Target indicativi per ogni vera esecuzione giornaliera:

WORK MILANO / ITALIA:
25-40 fonti o studi controllati.

WORK INTERNATIONAL / REMOTE:
25-40 fonti o studi / ATS controllati.

ART:
30-50 fonti / istituzioni / call / database controllati.

GRAFFITI / WRITING / MURAL:
15-30 fonti / festival / reti / organizzazioni controllati.

Questi target misurano FONTI SCANSIONATE, non risultati artificiali.

Non inventare opportunità per raggiungere una quota.

Se una fonte non è accessibile, registrala nel scan log.


==================================================
60. SCAN LOG OBBLIGATORIO
==================================================

Ogni report deve contenere un SCAN LOG completo.

Mostra:

FONTI WORK MILANO / ITALIA SCANSIONATE
numero totale + elenco completo dei nomi realmente controllati.

FONTI WORK INTERNATIONAL / REMOTE SCANSIONATE
numero totale + elenco completo.

FONTI ART SCANSIONATE
numero totale + elenco completo.

FONTI GRAFFITI SCANSIONATE
numero totale + elenco completo.

Per ogni fonte registra almeno:

name
url
category
status
result
lastCheckedAt

status / result devono distinguere:

OPPORTUNITY_FOUND
NO_VACANCY
NO_MATCH
TO_VERIFY
ACCESS_ERROR
LOGIN_REQUIRED

Il feed pubblico deve mantenere un oggetto top-level scanLog aggiornato
all'ultima esecuzione, senza dati privati.


==================================================
61. EXECUTIVE SUMMARY V3
==================================================

All'inizio del report mostra:

REPORT DATE
TOTAL LIVE
WORK LIVE
ART LIVE
GRAFFITI LIVE
NEW
CHANGED
CLOSED
TO_VERIFY
CRITICAL DEADLINES
URGENT DEADLINES
APPLICATION OPEN
APPLICATION TO_VERIFY

Poi mostra:

TOP 10 PRIORITIES TODAY

La TOP 10 deve includere sia opportunità nuove sia già presenti.


==================================================
62. TOP 10 PRIORITIES TODAY
==================================================

Per ogni voce mostra almeno:

1. titolo;
2. organizzazione;
3. area;
4. fitScore / score;
5. priorityScore quando disponibile;
6. firstSeen;
7. deadline;
8. daysRemaining;
9. urgency;
10. NEXT ACTION;
11. applicationUrl o metodo di candidatura;
12. sourceUrl.

Una opportunità vecchia ma ancora LIVE può essere prima in classifica.


==================================================
63. INSTAGRAM PUBLIC DISCOVERY
==================================================

Monitora anche informazioni PUBBLICAMENTE ACCESSIBILI sul web
collegate ai profili:

https://www.instagram.com/grim_dcc/
https://www.instagram.com/grim.dcc/
https://www.instagram.com/grimdcc.ai/
https://www.instagram.com/grim.dcc_photo/

Senza login.

Usa esclusivamente contenuti pubblicamente visibili o indicizzati.

Cerca opportunità, organizzazioni, festival, account pubblici,
open call, graffiti jam, mural project, residenze e collaborazioni
pubblicamente collegate a questi profili o alla loro rete visibile.

NON:
- accedere ai DM;
- tentare accesso a contenuti privati;
- effettuare login;
- aggirare limitazioni di Instagram;
- dichiarare completa la rete di contatti/follower se non è pubblicamente visibile.

Instagram è una fonte di DISCOVERY, non sostituisce la verifica
sulla fonte ufficiale dell'opportunità.


==================================================
64. SCHEMA V3
==================================================

Lo schema pubblico passa a:

schemaVersion: "3.0"

Ogni opportunità deve includere anche:

applicationOpenDate

quando verificabile.

Il feed pubblico deve inoltre supportare top-level:

scanLog

con struttura minima:

lastRunAt
workItaly
workInternationalRemote
art
graffiti

Ogni array scanLog contiene record pubblici delle fonti realmente scansionate
con name, url, category, status, result, lastCheckedAt.

La history futura deve includere anche activeGraffiti quando pertinente.

Non retro-modificare dati storici se il valore non è ricostruibile con certezza.


==================================================
65. REGOLA FINALE V3
==================================================

Il briefing di oggi deve bastare da solo per conoscere l'intera situazione
corrente.

L'utente NON deve aprire briefing precedenti per sapere quali opportunità
sono ancora attive.

Completezza, leggibilità, trasparenza della scansione e link contestuali
hanno priorità sulla brevità.

Le opportunità LIVE restano visibili fino a chiusura/scadenza verificata.
