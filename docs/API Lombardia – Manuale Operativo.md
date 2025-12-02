# API Lombardia – Manuale Operativo

**Codice Documento:** ARIA-AF-API Lombardia-Manuale Operativo  
**Revisione del Documento:** 1.1  
**Data revisione:** 26/11/2025  

> Nota: le immagini verranno aggiornate non appena quelle definitive saranno disponibili.

---

## Contents

1. Glossario  
2. Introduzione  
3. Registrazione ad API Lombardia  
   3.1 Creazione di una nuova utenza  
   3.2 Associazione al Soggetto  
   &nbsp;&nbsp;&nbsp;&nbsp;3.2.1 Associazione a un Soggetto esistente  
   &nbsp;&nbsp;&nbsp;&nbsp;3.2.2 Associazione a nuovo Soggetto  
4. Gestione Profilo  
5. Adesione di un Soggetto a un Ecosistema  
   5.1 Individuazione dell’Ecosistema  
   5.2 Richiesta di adesione a un Ecosistema e valutazione  
6. Richiesta di Fruizione  
   6.1 Fruitore API  
   &nbsp;&nbsp;&nbsp;&nbsp;6.1.1 Individuazione dell’API  
   &nbsp;&nbsp;&nbsp;&nbsp;6.1.2 Compilazione e invio della richiesta  
   &nbsp;&nbsp;&nbsp;&nbsp;6.1.2.1 API su approvazione  
   &nbsp;&nbsp;&nbsp;&nbsp;6.1.2.2 API libera  
   &nbsp;&nbsp;&nbsp;&nbsp;6.1.3 (Eventuale) Integrazione dell’API nel Caso d’uso  
   6.2 Erogatore  
   &nbsp;&nbsp;&nbsp;&nbsp;6.2.1 Valutazione della richiesta  
   &nbsp;&nbsp;&nbsp;&nbsp;6.2.2 Gestione dell’autenticazione  
7. Pubblicazione di un’API  
   7.1 Creazione della scheda API e invio della richiesta  
   7.2 Validazione e pubblicazione API  
8. Modifica Caso d’uso  

---

## 1. Glossario

### API

Un’API (Application Programming Interface) è un’interfaccia di programmazione che consente di accedere ai servizi e ai dati di un’altra applicazione, consentendo lo scambio di informazioni e la condivisione di funzionalità tra più sistemi.

### API libera

Un’API libera su API Lombardia è un’API il cui utilizzo non richiede alcuna approvazione formale. L’API è immediatamente disponibile all’utilizzo non appena l’utente ne richiede l’accesso.

### API su approvazione

Un’API su approvazione su API Lombardia è un’API il cui utilizzo richiede la validazione da parte dell’erogatore dell’API. Dopo aver inviato la richiesta per utilizzare l’API, l’utente deve attendere che l’erogatore la approvi prima di potervi accedere.

### Utente registrato

L'utente registrato è un utente che ha effettuato la registrazione su API Lombardia ma non è associato a un Soggetto (persona giuridica) ovvero l’ente o l’azienda di appartenenza.

### Soggetto

Il Soggetto (persona giuridica) è l’ente o l’azienda a cui un utente appartiene e a nome del quale potrà richiedere o pubblicare API.

### Utente registrato associato a un Soggetto

Un utente associato a un Soggetto è un utente registrato su API Lombardia che agisce per conto dell’ente o azienda di appartenenza. 

### Amministratore di un Soggetto

L’amministratore di un Soggetto è un utente registrato associato ad un Soggetto che gestisce le associazioni tra gli utenti ed il Soggetto di cui è amministratore e le adesioni del Soggetto agli Ecosistemi Digitali.

### Ecosistema Digitale

Un Ecosistema Digitale è caratterizzato da un insieme di Soggetti (persone giuridiche) che hanno la finalità di valorizzare il proprio patrimonio informativo mettendolo a disposizione reciprocamente. All’interno dell’Ecosistema, tali Soggetti condividono informazioni e funzionalità che, secondo regole definite, possono essere scambiate e utilizzate in una logica di interoperabilità, abilitata dalle API, per realizzare nuove applicazioni e servizi.

### TMB di un Ecosistema

Il TMB (Technical Management Board) di un Ecosistema è il team responsabile della gestione dell’Ecosistema.

In particolare: valuta le richieste di adesione all’Ecosistema e di pubblicazione delle API, coordina le richieste di fruizione delle API e garantisce il corretto funzionamento e l’applicazione delle regole definite per l’Ecosistema. 

### TMB di API Lombardia

Il TMB (Technical Management Board) di API Lombardia è il team responsabile della gestione di API Lombardia, che supervisiona tutti i processi del portale.

### Richiesta di fruizione di API

La richiesta di fruizione di un’API è una richiesta inviata da un Soggetto (persona giuridica) per poter utilizzare un’API. La richiesta può essere valutata dal referente amministrativo del servizio, che ne autorizza o meno l’utilizzo secondo le regole definite.

### Referente amministrativo di un’API

Il referente amministrativo di un’API è l’utente registrato associato a un Soggetto (persona giuridica) che è responsabile della gestione dell’API. Può essere nominato al momento della pubblicazione di un’API e valuta le richieste di fruizione ricevute dai potenziali utilizzatori dell’API stessa.

### Erogatore API

L’erogatore è un Soggetto (persona giuridica) pubblico o privato che rende disponibili le proprie API ad altri Soggetti all’interno del catalogo di API Lombardia. 

Ogni Soggetto può essere contemporaneamente erogatore di alcune API e fruitore di altre.

### Fruitore API

Il fruitore è un Soggetto (persona giuridica) pubblico o privato che richiede ed utilizza le API messe a disposizione da un Soggetto erogatore.

Ogni Soggetto può essere contemporaneamente fruitore di alcune API ed erogatore di altre.

### Stati di una richiesta di fruizione di API

Gli stati della richiesta di fruizione di un’API, previsti durante l’avanzamento del processo, sono i seguenti:

- **Da compilare**: la richiesta è stata creata, ma deve ancora essere compilata con le informazioni necessarie.  
- **Da inviare**: la richiesta è stata compilata, ma non è ancora stata inoltrata.  
- **In attesa**: la richiesta è stata inviata ed è in fase di valutazione da parte del TMB di API Lombardia o dell’Ecosistema specifico.  
- **Approvata | in attesa di credenziali**: la richiesta è stata accettata, ma le chiavi di accesso devono essere ancora generate e il certificato validato.  
- **Approvata**: la richiesta è stata accettata, le credenziali sono state generate e l’API può essere utilizzata.  
- **Rifiutata**: la richiesta non è stata approvata, è possibile consultare i motivi del rifiuto e, se previsto, modificarla o ripresentarla. 

### Caso d’uso

Un Caso d’uso descrive come una o più API possono essere integrate all’interno di soluzioni digitali, mettendo in evidenza il valore generato dal loro utilizzo in contesti reali.

### Richiesta di pubblicazione di un’API

La richiesta di pubblicazione di un’API è una richiesta inviata da un Soggetto per rendere disponibile un’API sul catalogo di API Lombardia. La richiesta viene gestita dal TMB dell’Ecosistema o dal TMB di API Lombardia secondo le regole e i criteri definiti.

### Scheda API

Una scheda API è la pagina dedicata all’API: al suo interno sono presenti le informazioni relative all’API, da essa è possibile iniziare anche il processo di fruizione della stessa.

Gli stati di una scheda API, previsti durante l’avanzamento del processo di pubblicazione e l’intero ciclo di vita dell’API, sono i seguenti:

- **In Bozza**: la scheda API è stata creata e salvata, ma non è stata inoltrata la richiesta di pubblicazione.  
- **In attesa di approvazione**: la scheda API è stata completata e inoltrata, la richiesta di pubblicazione è in fase di valutazione da parte del TMB di API Lombardia o dell’Ecosistema specifico.  
- **In attesa di integrazioni**: la scheda API è stata valutata, ma sono richieste integrazioni prima dell’approvazione.  
- **In arrivo**: la scheda API è stata approvata ed è visibile nel catalogo API, ma non è ancora disponibile all’utilizzo da parte di altri Soggetti.  
- **Disponibile**: la scheda API è stata approvata e pubblicata nel catalogo API e l’API è disponibile per l’utilizzo da parte di altri Soggetti.  
- **In manutenzione**: la scheda API è temporaneamente non disponibile in quanto l’API è soggetta a interventi di manutenzione.  
- **In dismissione**: un’API in fase di dismissione non può più essere richiesta da nuovi utenti, poiché la relativa scheda viene rimossa dal catalogo. Gli utilizzatori già attivi possono comunque continuare ad accedervi per un periodo transitorio, la cui durata dipende dalle regole dell’Ecosistema di riferimento. Al termine di questo periodo, l’API verrà definitivamente eliminata dall’ecosistema. 

---

## 2. Introduzione

API Lombardia nasce per implementare a livello regionale gli obblighi e le opportunità definiti dal Codice dell’Amministrazione Digitale e dallo Sviluppo Nazionale dell’Agenda Digitale. Il progetto si pone l’obiettivo di realizzare un ecosistema di interoperabilità, conforme al Modello di Interoperabilità (ModI) di AgID, integrando API sicure e standardizzate per garantire lo scambio di dati tra la Giunta Regionale, il Sistema Regionale (SiReg), altre Pubbliche Amministrazioni e soggetti privati.

Nel mondo digitale, le API (Application Programming Interface) sono come ponti invisibili che permettono alle applicazioni di comunicare tra loro. Grazie a queste interfacce, i servizi si connettono e collaborano senza che ce ne accorgiamo. Oggi, con le tecnologie più avanzate, la linea che separa il mondo fisico da quello digitale è sempre più sottile, creando connessioni che coinvolgono persone, imprese e persino oggetti.

In questo contesto, le API sono strumenti fondamentali di interoperabilità tecnica e diventano un elemento centrale per l’evoluzione della Pubblica Amministrazione e la costruzione di un rapporto digitale sempre più diretto ed efficace con cittadini e aziende: erogano servizi applicativi attraverso pattern e profili conformi alle Linee guida AgID (Determina 547/2021 e successive) in materia di sicurezza, logging, SLA e governance.

Il catalogo API Lombardia rappresenta il punto unico di accesso per la consultazione, la richiesta e l’integrazione delle API messe a disposizione all’interno di ecosistemi digitali, ognuno con proprie regole di adesione e fruizione. La sua adozione risponde a quanto stabilito dal CAD, dal ModI e dalle Linee Guida sull’Interoperabilità delle Pubbliche Amministrazioni emanate dall’Agenzia per l’Italia Digitale, garantendo standardizzazione e tracciabilità. L’iniziativa si colloca inoltre nel quadro della Piattaforma Digitale Nazionale Dati (PDND), favorendo l’allineamento ai modelli nazionali di interoperabilità e alle tecnologie standard (REST, OAuth2, JSON, certificati qualificati).

API Lombardia mira a semplificare l’interazione con il patrimonio informativo digitale, rendendo più agevole la consultazione, la richiesta e l’integrazione delle API. All’interno del presente manuale sono descritti i ruoli, le modalità di accesso, le procedure di richiesta e gli strumenti di supporto, con un linguaggio chiaro e orientato all’operatività. Infatti, questo manuale è stato realizzato per accompagnare gli utenti nell’utilizzo del nuovo portale, fornendo indicazioni pratiche e dettagliate sui principali passaggi da seguire. L’obiettivo è facilitare l’accesso alle funzionalità disponibili, chiarire i requisiti necessari per operare correttamente e offrire un supporto in ogni fase del processo di erogazione e di fruizione delle API.

Questo manuale definisce ruoli, modalità di accesso, procedure di richiesta e strumenti di supporto, accompagnando tutti gli utenti, indipendentemente dal livello di familiarità con gli strumenti digitali, nell’utilizzo della piattaforma, come riferimento utile per operare in autonomia, consapevolezza e precisione. Garantisce una governance strutturata delle API, in ottemperanza al nuovo modello di API Governance conformemente all’art. 50ter del CAD, e supporta il principio “once-only”, evitando duplicazioni informative e promuovendo un approccio digitale integrato, sicuro ed efficiente.

---

## 3. Registrazione ad API Lombardia

La registrazione al portale è il primo passo fondamentale per accedere ai servizi e alle funzionalità offerte da API Lombardia. Questo processo consente agli utenti di creare un account personale, garantendo un accesso sicuro e personalizzato. 

All’interno di questa sezione verranno illustrate tutte le fasi necessarie per completare la registrazione, con l’obiettivo di rendere l’esperienza utente semplice e intuitiva sin dal primo utilizzo. 

Il processo di registrazione si suddivide in due principali fasi:

1. **Creazione di una nuova utenza**: l’utente effettua l’autenticazione con la propria identità digitale, diventando a tutti gli effetti un utente registrato del portale.  
2. **Associazione al Soggetto**: l’utenza deve essere associata ad un Soggetto (persona giuridica) esistente o crearne uno nuovo, unendosi come membro o amministratore del Soggetto stesso.

### 3.1 Creazione di una nuova utenza

Come nuovo utente, il primo passo consiste nell’effettuare l’autenticazione ad API Lombardia utilizzando la propria identità digitale (SPID, CIE o CNS); per gli utenti di Regione Lombardia e ARIA, invece, è previsto l’accesso tramite il rispettivo login unico.

*Figura 1. Autenticazione*

Per completare il proprio profilo si richiede di inserire i contatti, indicare i contenuti di interesse e confermare di aver preso visione e accettato l’informativa sulla privacy.

*IMMAGINE REGISTRAZIONE PROFILO*  

*Figura 2. Creazione profilo*

### 3.2 Associazione al Soggetto

A seguito della creazione del profilo, l’utente dovrà richiedere l’associazione al Soggetto di appartenenza. Se in API Lombardia risulta essere presente il Soggetto, l’utente potrà sceglierlo ed associarsi, altrimenti sarà necessario crearne uno. 

#### 3.2.1 Associazione a un Soggetto esistente

Nel caso in cui il Soggetto a cui l’utente appartiene sia già presente all’interno di API Lombardia, il sistema consente una rapida associazione: l’utente potrà cercare il nome del Soggetto dal menu ed inviare la richiesta di associazione, che dovrà essere successivamente approvata dall’amministratore del Soggetto. 

*Figura 3. Associazione a un Soggetto esistente*

#### 3.2.2 Associazione a nuovo Soggetto

Qualora il Soggetto a cui l’utente appartiene non sia ancora presente all’interno di API Lombardia, l’utente potrà crearne uno nuovo, inserendo i dati identificativi del Soggetto e indicando sé stesso o un altro utente come amministratore del Soggetto. 

Per semplificare l'operazione, non è necessario essere il Legale Rappresentante del Soggetto per il quale si inizia il processo di creazione del nuovo Soggetto.

La creazione di un nuovo Soggetto è poi sottoposta a controlli di validità da parte del TMB (Technical Management Board) di API Lombardia per garantire l’univocità e la correttezza delle informazioni inserite. Una volta accettata la richiesta di creazione, l’utente verrà associato correttamente al Soggetto di appartenenza creato.

*Figura 4. Associazione a nuovo Soggetto*

---

## 4. Gestione Profilo

L’utente ha la possibilità di modificare le informazioni relative al proprio profilo in qualsiasi momento dalla sezione “Il mio profilo” (vedi Figura 5). 

*Figura 5. Il mio profilo*

Da questa pagina è possibile modificare i propri dati di contatto e le preferenze relative agli ambiti di interesse, salvando le modifiche apportate (vedi Figura 6).

*Figura 6. Gestione profilo*

In questa sezione è anche possibile eliminare il proprio profilo, scorrendo la pagina fino in fondo e cliccando sul pulsante “Elimina profilo” (vedi Figura 7).

*Figura 7. Eliminazione profilo*

---

## 5. Adesione di un Soggetto a un Ecosistema

L’adesione a un Ecosistema è un passaggio necessario per permettere a un Soggetto (persona giuridica) di pubblicare nuove API o fruire delle API già disponibili in quell’Ecosistema, nel rispetto delle regole e dei requisiti previsti.

Ogni Soggetto può aderire a uno o più Ecosistemi, a condizione che soddisfi i requisiti di accesso previsti da ciascuno. In tal caso, il processo di adesione dovrà essere ripetuto per ogni Ecosistema di interesse.

L’adesione a un Ecosistema può essere effettuata esclusivamente da un utente con ruolo di amministratore del Soggetto e solo dopo che la registrazione del Soggetto è stata completata e validata dal TMB di API Lombardia.

In questa sezione verranno illustrate tutte le fasi previste dal processo di adesione a un Ecosistema, con l’obiettivo di guidare l’utente.

Il processo di adesione si articola in due fasi principali:

1. **Individuazione dell’Ecosistema**: il Soggetto individua l’Ecosistema a cui intende aderire, consultando i requisiti richiesti.  
2. **Richiesta di adesione a un Ecosistema e valutazione**: il Soggetto presenta la richiesta di adesione, che viene esaminata dal TMB dell’Ecosistema. In caso di esito positivo, il Soggetto viene abilitato a operare all’interno dell’Ecosistema.

### 5.1 Individuazione dell’Ecosistema

Tutti gli utenti, registrati o non registrati, possono visualizzare, dalla sezione “Ecosistemi” accessibile dalla Homepage, l’elenco completo degli Ecosistemi presenti su API Lombardia e, per ciascuno di essi, consultare le informazioni generali e le API associate cliccando sul pulsante “Scopri di più” (vedi Figura 8).

*Figura 8. Ecosistemi*

### 5.2 Richiesta di adesione a un Ecosistema e valutazione

Per procedere con la richiesta di adesione a un Ecosistema, l’utente che riveste il ruolo di amministratore del Soggetto accede ad API Lombardia e sceglie la sezione “I miei soggetti” all’interno della propria Area personale “Il mio Profilo”.

*Figura 9. I miei soggetti*

Successivamente, seleziona il Soggetto di cui è amministratore e clicca su “Gestisci soggetto”, per accedere alla relativa scheda Soggetto. All’interno della scheda, è possibile selezionare l’opzione “Aggiungi ecosistemi”.

*Figura 10. Scheda Soggetto*

Per ciascun Ecosistema, è possibile cliccare su “Scopri di più” per accedere a una scheda informativa che ne descrive le caratteristiche principali. All’interno di questa scheda, è disponibile il pulsante “Richiedi adesione”, che consente di iniziare formalmente la procedura di adesione.  

Per il caso di alcuni Ecosistemi (come ad esempio E015), la richiesta di adesione avviene seguendo delle specifiche dell’Ecosistema stesso; quindi, una volta cliccato su “Richiedi adesione” API Lombardia rimanda al sito dell’Ecosistema che gestirà la richiesta internamente.

*Figura 11. Scheda Ecosistema*

Se l’Ecosistema prevede la stipula di un contratto, dopo aver cliccato sul pulsante “Richiedi adesione” verrà visualizzata una finestra che indica all’utente le azioni da completare prima di inviare la richiesta, come illustrato nella Figura 12. Nello specifico, viene richiesto di scaricare il documento cliccando il pulsante “Scarica documento”, compilarlo e farlo firmare dal legale rappresentante del Soggetto. Una volta caricato il contratto firmato, l’amministratore del Soggetto può completare l’operazione cliccando sul pulsante “Conferma e invia”.

*Figura 12. Contratto di adesione a un Ecosistema*

Se non è previsto alcun contratto, la richiesta viene inviata direttamente cliccando su “Richiedi adesione”, e viene visualizzata una finestra di conferma dell’avvenuta trasmissione. A questo punto, è necessario attendere la valutazione da parte del TMB dell’Ecosistema, che potrà approvare o rifiutare la richiesta.

*Figura 13. Richiesta di adesione a un Ecosistema inviata*

Nella scheda del Soggetto sarà visibile lo stato della richiesta: “In attesa di approvazione”. Se la valutazione da parte del TMB dell’Ecosistema è positiva, il Soggetto diventa aderente effettivo dell’Ecosistema. Questa informazione sarà visibile anche nella sezione “Ecosistemi”, che mostra l’elenco degli Ecosistemi a cui il Soggetto ha aderito. In caso di esito negativo, invece, la richiesta risulterà “Rifiutata”.

---

## 6. Richiesta di Fruizione

I Soggetti (persone fisiche) interessati a fruire di un’API e in possesso dei requisiti minimi richiesti dall'erogatore, potranno presentare una richiesta di fruizione. 

Per poter fruire di una API, è necessario che il Soggetto sia aderente all’Ecosistema in cui l’API è pubblicata e, qualora l’API sia “su approvazione”, è necessario che la richiesta venga approvata dall’erogatore dell’API.

In questa sezione verranno illustrate tutte le fasi del processo, suddivise tra le attività del fruitore API e quelle dell’erogatore dell’API.

### 6.1 Fruitore API

L’utente che intende fruire di una API pubblicata nel catalogo API dovrà presentare una richiesta di fruizione, corredata dalle motivazioni per l’utilizzo dell’API selezionata, e potrà utilizzarla nel rispetto delle regole di approvazione definite per ciascuna API.

Dal punto di vista del fruitore il processo si articola nelle seguenti fasi:

1. **Individuazione dell’API**: il fruitore individua l’API che intende richiedere.  
2. **Compilazione e invio della richiesta**: il fruitore compila la scheda di richiesta di fruizione dell’API indicando le informazioni richieste e la invia per l’eventuale approvazione da parte dell’erogatore.  
3. **(Eventuale) Integrazione dell’API nel Caso d’uso**: a seguito di una valutazione positiva, il fruitore integra l’API per realizzare il Caso d’uso.

#### 6.1.1 Individuazione dell’API

Il fruitore accede ad API Lombardia e consulta il catalogo API, dove trova tutte le API disponibili. Dopo aver selezionato l’API di interesse e verificato che l’API può essere utilizzata nell’ambito di un Ecosistema a cui il Soggetto è aderente, il fruitore la aggiunge al proprio carrello selezionando il pulsante “Aggiungi al carrello”.

Accedendo al “Carrello”, il fruitore può visualizzare tutte le richieste di fruizione associate al proprio profilo utente. In particolare, quelle relative a:

- **API da richiedere**, le cui richieste di utilizzo devono ancora essere compilate e inviate dal fruitore;  
- **API richieste di recente**, le cui richieste di utilizzo sono già state inviate dal fruitore.

*Figura 14. Carrello*

#### 6.1.2 Compilazione e invio della richiesta

Per procedere con la richiesta dell’API di interesse, il fruitore deve accedere alla sezione Carrello e cliccare sul pulsante “Compila”. Dovrà quindi compilare il modulo di richiesta, il cui contenuto varia in base al livello di accesso dell’API (API su approvazione o API libera). 

##### 6.1.2.1 API su approvazione

Nel caso di un’API su approvazione, il modulo di richiesta prevede che il fruitore indichi il Soggetto per conto del quale sta effettuando la richiesta e l’Ecosistema di riferimento. La compilazione della richiesta prevede tre sezioni:

- **Motivazione della richiesta**  
- **Dettagli della richiesta**  
- **Riepilogo**

###### Motivazione della richiesta

In questa sezione il fruitore indica il motivo per il quale intende utilizzare l’API (es. benefici che vuole ottenere) e associa alla richiesta un Caso d’uso reale che descrive come verrà utilizzata effettivamente l’API. Per associare la richiesta a un Caso d’uso, il fruitore può selezionare:

- un Caso d’uso già esistente e appartenente al Soggetto per conto del quale richiede la API;  
- un Caso d’uso nuovo.

Nel primo caso, potrà scegliere il Caso d’uso già presente in un menu predefinito.

*Figura 15. Richiesta di fruizione API su approvazione – Motivazione della richiesta*

Nel caso in cui il fruitore desideri associare la richiesta di fruizione a un nuovo Caso d’uso, è necessario inserire una serie di informazioni (nome, descrizione, tipologia, ecc.) e, eventualmente, allegare una o più immagini rappresentative del Caso d’uso.

*Figura 16. Richiesta di fruizione API su approvazione – Creazione nuovo caso d'uso*

Una volta inserite tutte le informazioni obbligatorie, il fruitore può proseguire con la compilazione cliccando sul pulsante “Avanti”. 

###### Dettagli della richiesta

In questa sezione, il fruitore può indicare il numero di chiamate e, qualora l’API preveda l’autenticazione tramite certificato SSL Client, sarà richiesto di selezionare un certificato già disponibile oppure allegarne uno nuovo.

*Figura 17. Richiesta di fruizione API su approvazione – Dettagli della richiesta*

###### Riepilogo

In questa sezione il fruitore può verificare le informazioni inserite. Se i dati sono corretti, può confermare cliccando sul pulsante “Conferma e torna al carrello”. Tornato nella sezione Carrello, può completare il processo cliccando sul pulsante “Invia” per inoltrare ufficialmente la richiesta di fruizione. È possibile inviare più richieste di fruizione contemporaneamente, se presenti nel Carrello, cliccando “Invia tutte le richieste compilate”.

*Figura 18. Carrello: API da richiedere*

La richiesta sarà visibile nel Carrello con lo stato “In attesa di approvazione” e sarà sottoposta a valutazione da parte dell’erogatore. 

Il fruitore può monitorare lo stato della richiesta direttamente da questa sezione, verificando eventuali aggiornamenti o cambi di stato. Il fruitore, inoltre, riceverà una mail automatica da API Lombardia, sia in caso di approvazione, sia in caso di rifiuto della richiesta. In quest’ultimo caso, la comunicazione includerà anche la motivazione del rifiuto.

In caso di approvazione, API Lombardia renderà disponibili i documenti associati all’API, come il manuale utente, il descrittore, le policy di utilizzo e altri materiali utili all’integrazione, e sarà possibile scaricarli tramite il pulsante “Scarica documenti”.

Se l’API prevede un metodo di autenticazione, saranno disponibili anche i file di accesso (es. credenziali, API Key, token). Lo stato della richiesta sarà aggiornato con la dicitura “Approvata” e il fruitore riceverà un’ulteriore mail automatica con la conferma della disponibilità completa dell’API.

##### 6.1.2.2 API libera

Nel caso di un’API libera, il modulo di richiesta è semplificato e prevede che il fruitore inserisca il motivo della richiesta, la tipologia dell’applicazione in cui verranno integrati i dati e, qualora esistente, il relativo sito web.

*Figura 19. Richiesta di fruizione API libera*

Una volta compilati i campi obbligatori, il fruitore può cliccare sul pulsante “Conferma e torna al carrello”, con cui viene indirizzato nuovamente nella sezione Carrello e inviare la richiesta tramite il pulsante “Invia”.

La richiesta sarà visibile nel carrello con lo stato “Approvata” e sarà possibile scaricare i documenti necessari alla fruizione dell’API.

#### 6.1.3 (Eventuale) Integrazione dell’API nel Caso d’uso

In caso di approvazione della richiesta, il fruitore può procedere con l’integrazione dell’API per realizzare il Caso d’uso.

Per confermare l’avvenuta integrazione, è necessario accedere alla sezione “Casi d’uso” disponibile nel proprio profilo utente, selezionare il Caso d’uso associato alla richiesta e indicare che l’integrazione è stata completata.

Una volta confermata l’integrazione, il TMB dell’Ecosistema può pubblicare il Caso d’uso su API Lombardia, rendendolo visibile agli altri utenti e Soggetti aderenti all’Ecosistema.

*Figura 20. Casi d'uso*

### 6.2 Erogatore

Ogni erogatore troverà le richieste di fruizione presentate dai fruitori accedendo alla propria area personale nella sezione dedicata, dove potrà gestirle. 

Dal punto di vista dell’erogatore il processo si articola nelle seguenti fasi:

1. **Valutazione della richiesta**: l’erogatore valuta la richiesta di fruizione API ricevuta.  
2. **Gestione dell’autenticazione**: l’erogatore, qualora l’API richieda un metodo di autenticazione, verifica e abilita le credenziali necessarie all’accesso.

#### 6.2.1 Valutazione della richiesta

Quando un fruitore richiede di utilizzare un’API, l’erogatore riceve una notifica automatica da API Lombardia e può visualizzare la richiesta accedendo alla sezione “Il mio profilo”, quindi entrando in “Le mie API”. Dopo aver selezionato l’API di interesse, può accedere alla sezione “Gestione richieste”, dove sono elencate tutte le richieste ricevute.

*Figura 21. Gestione richieste di fruizione API*

Selezionando una richiesta, l’erogatore può visualizzarne i dettagli e consultare la scheda relativa al Caso d’uso presentato dal fruitore.

A questo punto può decidere se approvare la richiesta, rendendo l’API disponibile per l’integrazione, oppure rifiutarla. In caso di rifiuto, è obbligatorio indicare la motivazione, che sarà comunicata al fruitore tramite notifica mail.

#### 6.2.2 Gestione dell’autenticazione

Nel caso in cui l’API preveda un metodo di autenticazione, l’erogatore, dopo aver approvato la richiesta di fruizione, è responsabile della generazione delle chiavi di accesso e/o della validazione del certificato SSL Client necessari per consentire al fruitore l’utilizzo dell’API stessa.

In caso di autenticazione con chiavi d’accesso, al momento dell’approvazione, viene visualizzato un messaggio che invita l’erogatore a:

- caricare i file di accesso (es. credenziali, API Key, token) direttamente, cliccando su “Carica documenti”, e successivamente cliccare sul pulsante “Conferma e invia”;  
- oppure scegliere di sospendere l’operazione e rimandarla ad un secondo momento, cliccando su pulsante “Ricordamelo più tardi”.

*Figura 22. File di accesso API*

Nel secondo caso, all’interno della scheda della richiesta sarà visibile un messaggio che ricorda all’erogatore di completare l’upload, tramite il pulsante “Carica documenti”. Fino a quando i file richiesti non verranno caricati, il fruitore non potrà utilizzare l’API.

*Figura 23. Scheda richiesta di fruizione API – upload dei file di accesso*

Per le API che prevedono l’utilizzo di un certificato SSL Client, al momento dell’approvazione viene mostrato un messaggio che chiede all’erogatore di confermare la validazione del certificato. È possibile:

- cliccare sul pulsante “L’ho già validato”, se la verifica è già stata effettuata;  
- oppure scegliere l’opzione “Ricordamelo più tardi”, in questo caso nella scheda della richiesta apparirà un messaggio con il pulsante “Ho validato il certificato”, da utilizzare una volta completata la validazione.

*Figura 24. Validazione certificato*  

*Figura 25. Scheda richiesta di fruizione API – validazione certificato*

---

## 7. Pubblicazione di un’API

Un Soggetto (persona giuridica) che vuole rendere disponibile una propria API ad altri Soggetti, all’interno di uno o più Ecosistemi a cui aderisce, può avviare il processo di pubblicazione dalla sezione “Le mie API” nell’area personale.  

Una volta completata la pubblicazione, l’API sarà visibile nel catalogo API di API Lombardia.

In questo capitolo verranno illustrate tutte le fasi necessarie per completare la richiesta di pubblicazione.

Il processo di pubblicazione si articola nelle seguenti fasi:

1. **Creazione della scheda API e invio della richiesta**: l’erogatore crea una scheda API e invia la richiesta di pubblicazione.  
2. **Validazione e pubblicazione API**: il TMB dell’Ecosistema valuta la scheda API e, a seguito di esito positivo, pubblica l’API nel catalogo API.

### 7.1 Creazione della scheda API e invio della richiesta

Il primo passo per avviare il processo di pubblicazione di un’API è possibile farlo in diversi modi:

- accedere alla propria area riservata e, nella sezione “Le mie API”, cliccare sul pulsante “Richiedi pubblicazione API”;  
- oppure cliccare sul pulsante “Richiedi pubblicazione API” che è disponibile in fondo alla pagina del catalogo API.

*Figura 26. Catalogo API*

In entrambi i casi API Lombardia apre il modulo di pubblicazione, che deve essere compilato inserendo:

- tutti i campi obbligatori relativi all’API;  
- il Soggetto per conto del quale si richiede la pubblicazione;  
- l’Ecosistema di riferimento.

È inoltre necessario allegare la documentazione richiesta (manuale utente, descrittore, policy di utilizzo, file Swagger) e indicare uno o più referenti amministrativi e un referente tecnico per l’API.

È possibile salvare tale form anche se non sono stati inseriti tutti i dati necessari, in questo modo l’utente ha la possibilità di completare l’operazione in un secondo momento senza perdere i dati già inseriti.

*Figura 27. Richiesta pubblicazione API*

Una volta completato il modulo e caricati i documenti, l’utente invierà la richiesta di pubblicazione, che dovrà essere presa in carico per la valutazione da parte del TMB dell’Ecosistema se la richiesta di pubblicazione dell’API è relativa a un Ecosistema o il TMB di API Lombardia se la richiesta di pubblicazione dell’API non riguarda uno specifico Ecosistema.

Una volta effettuata questa operazione ed inoltrata la richiesta di pubblicazione, lo stato della richiesta è visibile nella sezione “Le mie API” della propria area personale, dove risulterà in stato “In attesa di approvazione”. 

### 7.2 Validazione e pubblicazione API

Il TMB verifica la richiesta di pubblicazione ed effettua dei test di funzionamento dell’API.

Se la scheda API non risulta completa e/o esaustiva o i test hanno esito negativo, il TMB dovrà richiede all’utente di integrare la richiesta con le informazioni necessarie. La richiesta sarà quindi rimandata all’utente con le indicazioni del caso.

L’utente, in caso di integrazioni, dovrà accedere nuovamente alla sezione “Le mie API”, aggiornare la scheda e reinviare la richiesta di pubblicazione. Lo stato della richiesta risulterà nuovamente nello stato “In attesa di approvazione” e la richiesta dovrà essere nuovamente valutata dal TMB dell’Ecosistema o dal TMB di API Lombardia.

A seguito di una valutazione positiva da parte del TMB, l’API verrà pubblicata nel catalogo API e risulterà disponibile ai Soggetti aderenti di quell’Ecosistema.

---

## 8. Modifica Caso d’uso

La modifica di un Caso d’uso è un’azione consentita solamente all’utente che lo ha creato.

Per visualizzare i propri Casi d’uso, è necessario accedere alla propria “Area Personale”, nella sezione dedicata ai Casi d’uso.

Nella scheda del Caso d’uso è presente il pulsante “Modifica” che permetterà all’utente di modificare il Caso d’uso precedentemente creato e, successivamente, salvare le modifiche apportate.

*Figura 28. Modifica Caso d'uso*

---

**API Lombardia - Manuale Operativo - Rev. 1.1**
