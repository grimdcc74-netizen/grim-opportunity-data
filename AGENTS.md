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

Una voce TO_VERIFY non deve essere presentata come opportunità
verificata LIVE.


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

Quando possibile genera applicationSteps.

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

APPLY NOW
YES / NO

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

APPLY NOW

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

TO_VERIFY

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
- CLOSED;
- TO_VERIFY;
- deadline entro 3 giorni;
- deadline entro 7 giorni;
- application pronte;
- application bloccate.


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