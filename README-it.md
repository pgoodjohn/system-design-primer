*[English](README.md) ∙ [简体中文](README-zh-Hans.md) | [Brazilian Portuguese](https://github.com/donnemartin/system-design-primer/issues/40) ∙ [Japanese](https://github.com/donnemartin/system-design-primer/issues/100) ∙ [Polish](https://github.com/donnemartin/system-design-primer/issues/68) ∙ [Russian](https://github.com/donnemartin/system-design-primer/issues/87) ∙ [Traditional Chinese](https://github.com/donnemartin/system-design-primer/issues/88) ∙ [Turkish](https://github.com/donnemartin/system-design-primer/issues/39) | [Add Translation](https://github.com/donnemartin/system-design-primer/issues/28)*
**Nota: questa traduzione è ancora un progetto in corso**
# La base del design di sistemi

<p align="center">
  <img src="http://i.imgur.com/jj3A5N8.png">
  <br/>
</p>

## Perché?

> Impara a progettare sistemi di ampia scala.
> 
> Preparati per un colloqui sulla progettazione di sistemi.

### Impara come progettare sistemi di ampia scala

Imparare a progettare sistemi scalabili è un grande aiuto per diventare un migliore ingegnere.

La progettazione di sistemi è un argomento molto ampio. Ci sono **numerose risorse disperse in giro per il web** riguardanti i principi di progettazione di sistemi.

Questa repository è una **collezione organizzata** di risorce per aiutarti ad imparare come realizzare sistemi su scala.

### Impara dalla comunità Open Source

Questo documento è una prima bozza ed è un progetto Open Source in continuo aggiornamento.

Ogni [contribuzione](#contributing) è benvenuta!

### Preparati al colloquio per la progettazione di sistemi

Oltre ai test di programmazione, la progettazione di sistemi è un **passaggio fondamentale** dei **colloqui tecnici** presso numerose compagnie nel mondo dell'informatica.

È dunque necessario **esercitarsi attraverso alcune domande comuni** e **comparare** i propri risultati con le **soluzioni di esempio**: discussioni, codici e diagrammi.

Altri argomenti per la preparazione al colloqui sono:

* [Study guide](#study-guide)
* [How to approach a system design interview question](#how-to-approach-a-system-design-interview-question)
* [System design interview questions, **with solutions**](#system-design-interview-questions-with-solutions)
* [Object-oriented design interview questions, **with solutions**](#object-oriented-design-interview-questions-with-solutions)
* [Additional system design interview questions](#additional-system-design-interview-questions)

## Flashcard Anki

<p align="center">
  <img src="http://i.imgur.com/zdCAkB3.png">
  <br/>
</p>

I [mazzi Anki](https://apps.ankiweb.net/) presenti in questa repository utilizzano la ripetizione distanziata per aiutarti a apprendere e ricordare i concetti base della progettazione di sistemi.

* [System design deck](resources/flash_cards/System%20Design.apkg)
* [System design exercises deck](resources/flash_cards/System%20Design%20Exercises.apkg)
* [Object oriented design exercises deck](resources/flash_cards/OO%20Design.apkg)

Questi strumenti sono fantastici per continuare a studiare e ripassare gli argomenti principali al volo.

### Risorse di programmazione: sfide di programmazione interattive

Se stai cercando risorse per preparartsi al [**Colloquio di Programmazione**](https://github.com/donnemartin/interactive-coding-challenges)?

<p align="center">
  <img src="http://i.imgur.com/b4YtAEN.png">
  <br/>
</p>

Ti consigliamo di andare a controllare la repo __sorella__ [**Interactive Coding Challenges**](https://github.com/donnemartin/interactive-coding-challenges), la quale contiene un addizionale mazzo di carte per Anki:

* [Mazzo di Programmazione](https://github.com/donnemartin/interactive-coding-challenges/tree/master/anki_cards/Coding.apkg)

## Contribuire

> Impara dalla community.

Sentiti libero di aprire pull request per aiutare a:

* Correggere Errori
* Migliorare delle sezioni
* Aggiungere delle sezioni
* [Tradurre](https://github.com/donnemartin/system-design-primer/issues/28)

Tutto il contenuto che necessita raffinamento si trova in [under development](#under-development).

Riferisciti alle [Guide di Contribuzione](CONTRIBUTING.md).

## Indice degli argomenti di sistem design.

> Riassunto dei vari argomenti della progettazione di sistemi. **Ttutto è un trade-off**.
> 
> Ogni sezione contiene link a risorse più dettagliate.

<p align="center">
  <img src="http://i.imgur.com/jrUBAF7.png">
  <br/>
</p>

* [Argomenti di progettazione di sistemi: inizia qui](#argomenti-di-progettazione-di-sistemi-inizia-qui).
	* [Passo 1: rivisita la video lezione sulla scalabilità](#passo-1-rivisita-la-video-lezione-sulla-scalabilità)
	* [Passo 2: rivisita l'articolo sulla scalabilità](#passo-2-rivisita-l-articolo-sulla-scalabilità)
	* [Passi successivi](#passi-successivi)
* [Prestazioni vs scalabilità](#prestazioni-vs-scalabilità)
* [Latenza vs throughput](#latenza-vs-throughput)
* [Disponibilità vs coerenza](#disponibilità-vs-coerenza)
	* [Il teorema di CAP](#il-teorema-di-CAP)
		* [CP - consistenza e tolleranza di partizione](#cp---consistency-and-partition-tolerance)
		* [DP - disponibilità e tolleranza di partizione](#ap---availability-and-partition-tolerance)
* [Modelli di coerenza](#consistency-patterns)
	* [Coerenza debole](#weak-consistency)
	* [Coerenza eventuale](#eventual-consistency)
	* [Coerenza forte](#strong-consistency)
* [Modelli di disponibilità](#availability-patterns)
	* [Fail-over](#fail-over)
	* [Replicazione](#replication)
* [Sistema dei Nomi di Dominio (DNS)](#domain-name-system)
* [Rete di distribuzione di contenuto (CDN)](#content-delivery-network)
	* [Push CDNs](#push-cdns)
	* [Pull CDNs](#pull-cdns)
* [Bilanciatori di carico](#load-balancer)
	* [Attivo-passivo](#active-passive)
	* [Attivo-attivo](#active-active)
	* [Bilanciamento di carico di livello 4](#layer-4-load-balancing)
	* [Bilanciamento di carico di livello 7](#layer-7-load-balancing)
	* [Scalamento orizzontale](#horizontal-scaling)
* [Proxy inverso (server web)](#reverse-proxy-web-server)
	* [Bilanciatore di carico vs proxy inverso](#load-balancer-vs-reverse-proxy)
* [Livello di applicazione](#application-layer)
	* [Microservizi](#microservices)
	* [Scoperta di servizi](#service-discovery)
* [Database](#database)
	* [Sistemi di gestione di database relazionali (RDBMS)](#relational-database-management-system-rdbms)
		* [Replicazione master-slave](#master-slave-replication)
		* [Replicazione master-master](#master-master-replication)
		* [Federazione](#federation)
		* [Cristallizzazione](#sharding)
		* [Denormalizzazione](#denormalization)
		* [Messa a punto SQL](#sql-tuning)
	* [NoSQL](#nosql)
		* [Memorizzazione chiave-valore](#key-value-store)
		* [Memorizzazione di documenti](#document-store)
		* [Memorizzazione a larghe colonne](#wide-column-store)
		* [Database a grafo](#graph-database)
	* [SQL o NoSQL](#sql-or-nosql)
* [Cache](#cache)
	* [Caching sul client](#client-caching)
	* [Caching su una CDN](#cdn-caching)
	* [Caching sul server](#web-server-caching)
	* [Caching del database](#database-caching)
	* [Caching dell'applicazione](#application-caching)
	* [Caching al livello delle query del datbase](#caching-at-the-database-query-level)
	* [Caching al livello degli oggetti](#caching-at-the-object-lavel)
	* [Quando aggiornare la cache](#when-to-update-the-cache)
		* [Cache-aside](#cache-aside)
		* [Write-throguh](#write-through)
		* [Write-behind (write-back)](#write-behind-write-back)
		* [Refresh-ahead](#refresh-ahead)
* [Asincronia](#asynchronism)
	* [Code di messaggi](#message-queues)
	* [Code di lavori](#task-queues)
	* [Contropressione](#back-pressure)
* [Comunicazione](#communication)
	* [Transmission Control Protocol (TCP)](#transmission-control-protocol-tcp)
	* [User Datagram Protocol (UDP)](#user-datagram-protocol-udp)
	* [Procedura di chiamata remota (RPC)](#remote-procedure-call-rpc)
	* [Representational state transfer (REST)](#representational-state-transfer-rest)
* [Sicurezza](#security)
* [Appendice](#appendix)
    * [Tavola delle potenze di due](#powers-of-two-table)
    * [Numeri di latenza che ogni programmatore dovrebbe conoscere](#latency-numbers-every-programmer-should-know)
    * [Domande extra sulla progettazione di sistemi](#additional-system-design-interview-questions)
    * [Architetture reali](#real-world-architectures)
    * [Architetture di diverse compagnie](#company-architectures)
    * [Blog tecnici di diverse compagnie](#company-engineering-blogs)
* [In sviluppo](#under-development)
* [Crediti](#credits)
* [Informazioni di contatto](#contact-info)
* [License](#license)

## Guida allo studio

> Argomenti suggeriti in base al tempo rimanente prima del colloquio (breve, medio, lungo)

![Imgur](http://i.imgur.com/OfVllex.png)

**Q: Per i colloqui, devo sapere tutto ciò che è contenuto in questa guida?**

**A: No, non è necessario sapere tutto ciò che è contenuto qui per preparare il colloquio**

Che cosa ti viene richiesto durante un'intervista dipende da variabili come:

* Quanta esperienza hai
* Qual è il tuo background tecnico
* Per quale posizione stai effettuando il colloquio
* Presso quale compagnia stai effettuando il colloquio
* Fortuna

È solito che da candidati più esperti ci si aspetti una maggiore conoscenza della progettazione di sistemi. È normale che da Architetti o capi team ci si aspetti più conoscenza che rispetto a membri individuali.

Inizia studiando tutti gli argomenti in generale eapprofondisci su alcune aree. È utile avere conoscenze riguardo a tutti gli aspetti della progettazione di sistemi. Adatta queste guide in bbase al tempo a tua disposizione, alla tua sperienza, alla posizione per la quale stai effettuando il colloquio e la compagnia presso la quale stai effettuando il colloquio.

* **Timeline breve** - Punta ad una conoscenza **ampia** su tutti gli argomenti di progettazione di sistemi. Esercitati risolvendo **alcuni** problemi classici dei colloqui.
* **Timeline media** - Punta ad una conoscnza **ampia** in generale, ma **approfondisci** alcuni argomenti. Esercitati risolvendo **molti** problemi classici dei colloqui.
* **Timeline lunga** - Punta ad una conoscenza **ampia** in generale, ma **approfondisci più** argomenti. Esercitati risolvendo **la maggior parte** dei problemi classici dei colloqui.

| | Breve | Media | Lunga |
| --- | --- | --- | --- |
| Leggi gli [argomenti della progettazione di sistemi](#index-of-system-design-topics) per farti un'idea di come questi funzionano | :+1: | :+1: | :+1: |
| Leggi alcuni dei [blog tecnici di compagnie](#company-engineering-blogs) concentrandoti sui blog delle compagnie per cui stai effettuando un colloquio | :+1: | :+1: | :+1: |
| Studia alcune [architetture reali](#real-world-architectures) | :+1: | :+1: | :+1: |
| Rivedi [come approcciare una domanda di un colloquio sulla progettazione di sistemi](#how-to-approach-a-system-design-interview-question) | :+1: | :+1: | :+1: |
| Rivedi passo a passo delle [domande di progettazione di sistemi con soluzione](#system-design-interview-questions-with-solutions) | Alcune | Molte | La maggior parte |
| Rivedi passo a passo delle [domande di progettazione ad oggetti con soluzione](#object-oriented-design-interview-questions-with-solutions) | Alcune | Molte | La maggior parte |
| Rivedi [ulteriori domande relative alla progettazione di sistemi](#additional-system-design-interview-questions) | Alcune | Molte | La maggior parte |

## Come approcciare una domanda di progettazione di sistemi

> Come affrontare una domanda di progettazione di sistemi

Il colloquio dio progettazione di sistemi è una **discussione aperta**. Ci si aspetta che sia tu a condurla.

Puoi usare i seguenti passaggi per raggiungere questo risultato. Per aiutarti a solidificare questo processo, rivedi passo a passo alcune delle [domande di progettazione di sistemi con soluzione](#system-design-interview-questions-with-solutions) utilizzando i seguenti passaggi.

### Passaggio 1: delinea gli scenari di utilizzo, i vincoli e i tuoi presupposti

Raccogli tutti irequisiti e la portata del problema. Fai domande per chiarire tutti gli scenari di utilizzo e i vincoli. Discuti i tuoi presupposti.

* Chi utilizzerà il sistema?
* Come lo utilizzeranno?
* Quanti utenti ci si può aspettare?
* Che cosa fa il sistema?
* Quali sono gli input e gli output del sistema?
* Quanti dati dovremmo aspettarci di gestire?
* Quante richieste al secondo ci aspettiamo?
* Qual è il rapporto lettura/scritture previsto?

### Passaggio 2: crea un progretto di alto livello.

Delina un progetto di alto livello indicando tutti i componenti principali.

* Abbozza i principali componenti e le loro connessioni
* Giustifica le tue idee

### Passaggio 3: progetta i componenti principali

Concentrati sui dettagli di ognuno dei componenti principali. Per esempio, se ti è stato richiesto di [progettare un servizion di abbreciazione di url](solutions/system_design/pastebin/README.md), parla di:

* Generazione e memorizzazione di un hash dell'url completo
	* [MD5](solutions/system_design/pastebin/README.md) e [Base62](solutions/system_design/pastebin/README.md)
	* Collisioni di Hash
	* SQL o NoSQL
	* Schema del database
* Traduzione dell'url accorciato nell'url completo
	* Ricerca nel database
* API e design orientato a oggetti

### Passaggio 4: scala il design

Identifica e risolvi eventuali colli di bottiglia, dati i vincoli del progetto. Per esempio, hai bisogno di risolvere problemi di scalabilità?

* Distributore di carico
* Scalabilità orizzontale
* Caching
* Frammentazione del database

Discuti possibili soluzioni e trade-off. Ogni soluzione è un trade-off. Risolvi i bottleneck fornendoti dei [principi di progettazione di sistemi scalabili](#index-of-system-design-topics).

### Calcoli mentali

Potrebbe esserti richiesto di effettuare delle stime a mano. Rivedi l'[Appendice](#appendix) concentrandoti sui seguenti argomenti: 

* [Effettua calcoli mentali](http://highscalability.com/blog/2011/1/26/google-pro-tip-use-back-of-the-envelope-calculations-to-choo.html)
* [Tavola delle potenze di due](#powers-of-two-table)
* [Numeri di latenza che ogni programmatore dovrebbe conoscere](#latency-numbers-every-programmer-should-know)

### Risorse e ulteriori argomenti di lettura

Rivedi i seguenti link per farti un'idea di che cosa aspettarti (in inglese):

* [How to ace a systems design interview](https://www.palantir.com/2011/10/how-to-rock-a-systems-design-interview/)
* [The system design interview](http://www.hiredintech.com/system-design)
* [Intro to Architecture and Systems Design Interviews](https://www.youtube.com/watch?v=ZgdS0EUmn70

## Domande di colloquio sulla progettazione di sistemi con soluzione

> Domande di progettazione di sistemi comuni per un colloquio con un esempio di discussione, codice e diagrammi.
> 
> Le soluzioni rimandano al contenuto nella cartella `solutions/`.

| Question | |
| --- | --- |
| Progetta Pastebin.com (o Bit.ly) | [Soluzione](solutions/system_design/pastebin/README.md) |
| Progetta la timeline di Twitter (o il feed di Facebook )<br/>Progetta la ricerca di Twitter (o di Facebook) | [Soluzione](solutions/system_design/twitter/README.md) |
| Progetta a web crawler | [Soluzione](solutions/system_design/web_crawler/README.md) |
| Progetta Mint.com | [Soluzione](solutions/system_design/mint/README.md) |
| Progetta le strutture di dati per un social network | [Soluzione](solutions/system_design/social_graph/README.md) |
| Progetta un sistema di memorizzazione chiave-valore per un motore di ricerca | [Soluzione](solutions/system_design/query_cache/README.md) |
| Progetta la funzionalità di amazon per le classifiche di vendita di prodotti per categoria | [Soluzione](solutions/system_design/sales_rank/README.md) |
| Progetta un sistema che scali a milioni di utenti usando AWS | [Soluzione](solutions/system_design/scaling_aws/README.md) |
| Aggiungi una domanda | [Contribuisci](#contributing) |

### Progetta Pastebin.com (o Bit.ly)

[Vedi l'esercizio e la soluzione](solutions/system_design/pastebin/README.md)

![Imgur](http://i.imgur.com/4edXG0T.png)

### Progetta la timeline e la ricerca di Twitter (o di Facebook)

[Vedi l'esercizio e la soluzione](solutions/system_design/twitter/README.md)

![Imgur](http://i.imgur.com/jrUBAF7.png)

### Progetta un web crawler

[Vedi l'esercizio e la soluzione](solutions/system_design/web_crawler/README.md)

![Imgur](http://i.imgur.com/bWxPtQA.png)

### Progetta Mint.com

[Vedi l'esercizio e la soluzione](solutions/system_design/mint/README.md)

![Imgur](http://i.imgur.com/V5q57vU.png)

### Progetta le strutture di dati per un social network

[Vedi l'esercizio e la soluzione](solutions/system_design/social_graph/README.md)

![Imgur](http://i.imgur.com/cdCv5g7.png)

### Progetta un sistema di memorizzazione chiave-valore per un motore di ricerca

[Vedi l'esercizio e la soluzione](solutions/system_design/query_cache/README.md)

![Imgur](http://i.imgur.com/4j99mhe.png)

### Progetta la funzionalità di amazon per le classifiche di vendita di prodotti per categoria

[Vedi l'esercizio e la soluzione](solutions/system_design/sales_rank/README.md)

![Imgur](http://i.imgur.com/MzExP06.png)

### Progetta un sistema che scali a milioni di utenti usando AWS

[Vedi l'esercizio e la soluzione](solutions/system_design/scaling_aws/README.md)

![Imgur](http://i.imgur.com/jj3A5N8.png)

## Domande di progettazione orientata a oggetti con soluzioni

> Comuni domande di progettazione orientata a oggetti con esempi di discussione, codici e diagrammi.
> 
> Le soluzioni rimandano al contenuto nella cartella `solutions/`.

>**Nota: questa sezione è ancora in sviluppo**

| Domande | |
|---|---|
| Progetta una mappa ad hash | [Soluzione](solutions/object_oriented_design/hash_table/hash_map.ipynb)  |
| Progetta una cache per un sistema di 'Utilizzati di Recente' | [Soluzione](solutions/object_oriented_design/lru_cache/lru_cache.ipynb)  |
| Progetta un call center | [Soluzione](solutions/object_oriented_design/call_center/call_center.ipynb)  |
| Progetta un mazzo di carte | [Soluzione](solutions/object_oriented_design/deck_of_cards/deck_of_cards.ipynb)  |
| Progetta un parcheggio | [Soluzione](solutions/object_oriented_design/parking_lot/parking_lot.ipynb)  |
| Progetta un server per un servizio di chat | [Soluzione](solutions/object_oriented_design/online_chat/online_chat.ipynb)  |
| Progetta una array circolare | [Contribuisci](#contribuisci)  |
| Aggiungi una domanda di progettazione orientata ad oggetti | [Contribuisci](#contribuisci) |

### Argomenti di progettazione di sistemi: inizia qui

Novizio alla progettazione di sistemi?

Per incominciare, avrai bisogno di un'infarinatura dei principi base, imparare quali sono, come sono utilizzati e i loro pro e contro.

### Passo 1: rivisita la video lezione sulla scalabilità

[Lezione sulla scalabilità ad Harvard](https://www.youtube.com/watch?v=-W9F__D3oY4)

* Argomenti trattati:
	* Scalatura verticale
	* Scalatura orizzontale
	* Caching
	* Bilanciamento di carico
	* Replicazione di database
	* Partizionamento di database

### Passo 2: rivisita l'articolo sulla scalabilità

[Scalabilità](http://www.lecloud.net/tagged/scalability)

* Argomenti trattati:
    * [Cloni](http://www.lecloud.net/post/7295452622/scalability-for-dummies-part-1-clones)
    * [Database](http://www.lecloud.net/post/7994751381/scalability-for-dummies-part-2-database)
    * [Cache](http://www.lecloud.net/post/9246290032/scalability-for-dummies-part-3-cache)
    * [Asincronia](http://www.lecloud.net/post/9699762917/scalability-for-dummies-part-4-asynchronism)

### Passi successivi

Successivamente, trattiamo alcuni dei trade-off di alto livello:

* **Prestazioni** vs **scalabilità**
* **Latenza** vs **throughput**
* **Disponibilità** vs **coerenza**

Ricordati che nella progettazione di sistemi, ogni scelta è un trade-off.

Andremo poi a trattare argomenti più specifici come DNS, CDN e bilanciatori di carico.

## Prestazioni vs scalabilità

Un servizio è **scalabile** se risulta avere un incremento di **prestazioni** proporzionale alla quantità di risorse aggiunte. Generalmente, aumentare le prestazioni significa servire più unità di lavoro, ma potrebbe anche indicare l'abilità di gestire unità di lavoro di maggiori dimensioni come, per esempio, un dataset di dimensioni aumentate.<sup><a href=http://www.allthingsdistributed.com/2006/03/a_word_on_scalability.html>1</a></sup>

Un altro modo per riflettere al problema di prestazioni vs scalabilità è il seguente:

* Se hai problemi di **prestazioni**, il tuo sistema risulta lento per un singolo utente.
* Se hai problemi di **scalabilità**, il tuo sistema risulta veloce per un singolo utente ma rallenta sotto un grosso carico di lavoro.

### Risorse e ulteriori spunti di lettura

* [A word on scalability](http://www.allthingsdistributed.com/2006/03/a_word_on_scalability.html)
* [Scalability, availability, stability, patterns](http://www.slideshare.net/jboner/scalability-availability-stability-patterns/)

## Latenza vs throughput

La **latenza** è il tempo per eseguire un certo comando o per produrre uno specifico risultato.

Il **throughput** è la quantità del sopracitato tipo di azioni che possono essere eseguite in un unità di tempo.

In genere, l'obiettivo è avere **massimo throughput** con **latenza accettabile**.

### Risorse e ulteriori spunti  di lettura

* [Understanding latency vs throughput](https://community.cadence.com/cadence_blogs_8/b/sd/archive/2010/09/13/understanding-latency-vs-throughput)

## Disponibilità vs consistenza

### Il teorema di CAP

<p align="center">
  <img src="http://i.imgur.com/bgLMI2u.png">
  <br/>
  <i><a href=http://robertgreiner.com/2014/08/cap-theorem-revisited>Fonte: il teorema di CAP, revisitato</a></i>
</p>

In un sistema di calcolo distribuito, è possibile garantire solo due delle seguenti:

* **Consistenza** - Ogni lettura riceve la scrittura o l'errore più recente
* **Disponibilità** - Ogni richiesta riceve una risposta, senza la garanzia che questa contenga la versione dell'informazione più recente
* **Tolleranza di partizione** - Il sistema continua ad operare anche in caso di partizione arbitraria causata da fallimenti della rete

*Le reti non sono RELIABLE, dovrai quindi supportare la tolleranza di partizione. Sarà necessario che tu faccia dei trade off a livello di software fra coerenza e disponibilità*

#### CP - Coerenza e tolleranza di partizione

Attendere una risposta da un nodo partizionato potrebbe risultare in un errore di timeout. CP è una buona scelta se è richiesto che il sistema abbia lettura e scrittura atomica.

#### AP - Disponibilità e tolleranza di partizione

In questa situazione, le risposte che riferiscono la versione più recente dei dati presenti sul nodo che, però, potrebbe non essere la versione più recente presente sul sistema. Questa potrebbe richiedere del tempo prima che si possa propagare in tutti i nodi del sistema stesso.

La AP è una buona scelta se è richiesto che il sistema abbia [coerenza eventuale](#coerenza-eventuale) o quando è necessario che il sistema continui a lavorare nonostante errori esterni.

### Risorse e ulteriori spunti di lettura

* [CAP theorem revisited](http://robertgreiner.com/2014/08/cap-theorem-revisited/)
* [A plain english introduction to CAP theorem](http://ksat.me/a-plain-english-introduction-to-cap-theorem/)
* [CAP FAQ](https://github.com/henryr/cap-faq)

## Pattern di coerenza

Con diverse copie delle stesse informazioni, abbiamo diverse opzioni per sincornizzarle in modo tale che tutti i client abbiano una vista coerente dei dati. Rivedi la definizione del [teorema di CAP](#il-teorema-di-cap) - ogni lettura riceve la scrittura più recente o un errore.

### Coerenza debole

Dopo una operazione di scrittura, le operazioni di lettura potrebbero vederlo o non vederlo. Si tratta di un approccio _best effort_.

Questo approccio è usato in sistemi timpo memcached. La coerenza debole funziona bene in sistemi real-time come applicazioni VoIP, video chat e giochi multiplayer in tempo reale. Per esempio, se durante una telefonata la connessione viene persa per qualche secondo, al momento della riconnessione non verranno riprodotti i secondi di chiamata persi.

### Coerenza eventuale

Dopo un'operazione di scrittura, le operazioni di lettura, eventualmente (solitamente dopo qualche millisecondo) vedranno le informazioni aggiornate. I dati sono replicati in modo asincrono.

Questo approccio è tipicamente usato in sistemi come DNS e email. La coerenza eventuale funziona bene in sistemi ad alta disponibilità.

### Coerenza forte

Dopo una operazione di scrittura, le operazioni di lettura vedranno, immediatamente, i dati aggiornati.

Questo approccio è tipico in file-system e RDBMS. La coerenza forte funziona bene in sistemi che hanno bisogno della probabilità di transitività.

### Risorse e ulteriori spunti di lettura

* [Transactions across data centers](http://snarfed.org/transactions_across_datacenters_io.html)

## Pattern di disponibilità

Esistono due principali pattern che garantiscono alta disponibilità: il **fail-over** e la **replicazione**.

### Fail-over

#### Attivo-passivo

Con il fail-over attivo-passivo, dei _battiti_ sono inviati fra il server attivo e il server passivo in standby. Se questo battito viene interrotto, il sistema passivo prende il posto di quello attivo, assegnandosi il suo indirizzo IP, e continaundo il servizio.

La durata del downtime è determinata dal metodo in cui il server passivo è attivo: se si trova in 'hot' standby o in 'cold' standby. Tutto il traffico è gestito solamente dal server attivo.

Il fail-over attivo-passivo può anche essere chiamato fail-over master-slave.

#### Attivo-attivo

Nel fail-over attivo-attivo, entrambi i server gestiscono il traffico, dividendosi il carico fra di loro.

Se i server sono rivolti al pubblico, il DNS dovrebbe conoscere gli indirizzi IP pubblici di entrambi i server.
Se i server sono rivolti all'interno, la logica dell'applicazione dovrebbe avere informazioni riguardo a entrambi i server.

Il fail-over attivo-attivo può anche essere chiamato fail-over master-master.

### Svantaggi: fail-over

* Sistemi di fail-over aggiungono hardware alle richieste e creano maggiore complessità.
* C'è una potenziale perdita di dati se il sistema attivo fallisce prima che ogni data scritta sul sistema attivo può essere propagata sul passivo.

### Replica

#### Master-slave e master-master

Questo argomento è discusso nella sezione [Database](#database):

* [Replica master-slave](#replica-master-slave)
* [Replica master-master](#replica-master-master)

## Domain name system (DNS)

<p align="center">
  <img src="http://i.imgur.com/IOyLj4i.jpg">
  <br/>
  <i><a href=http://www.slideshare.net/srikrupa5/dns-security-presentation-issa>Source: DNS security presentation</a></i>
</p>

Un Domain Name System (DNS) traduce nomi di dominio come www.example.com in indirizzi IP.

I DNS sono gerarchici: con pochi server autoritativi al livello superiore. Il tuo router o il tuo ISP forniscono informazioni riguardanti i server DNS da contattare quando una operazione di lookup è in corso. Server DNS di livello più basso salvano le mappature nelle loro cache, che potrebbero diventare stale a causa dei ritardi di propagazione di DNS. I risultati DNS possono anche essere salavati nella cache dal tuo browser o dal sistema operativo per un certo periodo di tempo, solitamente determinato dal [tempo di vita (TTL)](https://en.wikipedia.org/wiki/Time_to_live).

* **NS Record (name server)** - Specifica i(l) server DNS per il tuo dominio/sottodominio.
* **MX Record (mail exchange)** - Specifica i(l) server mail per accettare messaggi.
* **A Record (address)** - Mappa un nome ad un indirizzo IP.
* **CNAME (canonical)** - Mappa un nome ad un altro nome o ad un altro `CNAME` (example.com a www.example.com) o a un `A` record.

Servizi come [CloudFlare](https://www.cloudflare.com/dns/) e Route 53](https://aws.amazon.com/route53/) forniscono servizi autogestiti di DNS. Alcuni servizi di DNS possono indirizzare il traffico utilizzando diversi metodi:

* [Round Robin ponderato](http://g33kinfo.com/info/archives/2657)
	* Evita che del traffico sia indirizzato a server in manutenzione
    * Garantisce un bilanciamento fra diverse dimensioni di cluster
    * Permette di effettuare A/B testing
* Basato sulla latenza
* Basato sulla geolocalizzazione

### Svanttaggi: DNS

* Accedere ad un server DNS introduce un piccolo ritardo che, però, è solitamente mitigato dalle operazioni di caching descritte sopra.
* Gestire un server DNS potrebbe risultare complicato, sebbene questi siano gestiti da [governi, ISP, e grandi compagnie](http://superuser.com/questions/472695/who-controls-the-dns-servers/472729).
* Servizi di DNS sono stati recentemente obiettivi di [attacchi DDoS](http://dyn.com/blog/dyn-analysis-summary-of-friday-october-21-attack/), i quali hanno impedito agli utenti di accedere a servizi come Twitter senza sapere gli indirizzi IP di Twitter.

### Risorse e ulteriori spunti di lettura

* [DNS architecture](https://technet.microsoft.com/en-us/library/dd197427(v=ws.10).aspx)
* [Wikipedia](https://en.wikipedia.org/wiki/Domain_Name_System)
* [DNS articles](https://support.dnsimple.com/categories/dns/)

## Content Delivery Network

<p align="center">
  <img src="http://i.imgur.com/h9TAuGI.jpg">
  <br/>
  <i><a href=https://www.creative-artworks.eu/why-use-a-content-delivery-network-cdn/>Fonte: perché usare una CDN</a></i>
</p>

Una Content Delivery Network (o CDN) è una rete di server proxy distribuita globalmente, il cui scopo è quello di servire contenuti da luoghi più vicini all'utente. In genere, le CDN sono utilizzate per servire file statici come file HTML/CSS/JS, immagini e video; alcune CDN come CloudFront di Amazon, però, supportano anche contenuti dinamici. La risoluzione DNS del sito collegato alla CDN fornirà i dettagli di quale server contattare al browser cliente.

Servire contenuti da una CDN può aumentare notevolmente l'efficenza in due modi:

* Gli utenti ricevono i contenuti da dei data center vicino a loro
* Il server non deve servire tutte le richieste che sono delegate alla CDN

### CDN Push

Le cosiddette CDN Push ricevono nuovi contenuti ogniqualvolta un cambiamento accade sul server. Ti viene data la completa responsabilità di fornire il contenuto, caricandolo direttamente sulla CDN e riscrivendo gli URL in modo tale che questi puntino alla CDN stessa. Puoi configurare quando il contenuto scade e quando viene aggiornato. I contenuti sono caricati solamente quando è nuovo o modificato, riducendo così il traffico ma sfruttando al massimo la memorizzazione.

### CDN Pull

Le CDN Pull richiedono il contenuto al server la prima volta che un utente ne effettua la richiesta. Tutti i contenuti rimangono sul server e è solo necessario che tu riscriva gli URL in modo tale che questi puntino alla CDN. Il risultato di questa operazione è richieste più lente fino a quando il contenuto non è salvato nella cache della CDN.

Il [time-to-live (TTL)](https://it.wikipedia.org/wiki/Time_to_live) determina quanto a lungo i contenuti sono salvati sulla CDN. Le CDN pull minimizzano la quantità di memoria usata, ma possono creare traffico ridondante se dei file scadono e vengono ri-richiesti prima che siano effettivamente cambiati.

I siti con traffico molto pesante sono quelli che traggono più vantaggio dalle CDN Pull in quanto questo è diviso più equamente con solamente i contenuti più recenti memorizzati sulla CDN.


### Svantaggi: CDN

* Il costo delle CDN potrebbe essere significativo, in base al traffico, anche se questo va pesato con i costi in cui incorreresti nel caso tu non usassi una CDN.
* I contenuti potrebbero essere obsoleti nel caso questi vengano aggiornati prima che il TTL li faccia sadere
* Le CDN richiedono che tutti gli URL vengano cambiati in modo tale da puntare alla CDN stessa.

### Risorse e ulteriori spunti di lettura

* [Globally distributed content delivery](http://repository.cmu.edu/cgi/viewcontent.cgi?article=2112&context=compsci)
* [The differences between push and pull CDNs](http://www.travelblogadvice.com/technical/the-differences-between-push-and-pull-cdns/)
* [Wikipedia](https://it.wikipedia.org/wiki/Content_Delivery_Network)

## Bilanciatori di Carico

<p align="center">
  <img src="http://i.imgur.com/h81n9iK.png">
  <br/>
  <i><a href=http://horicky.blogspot.com/2010/10/scalable-system-design-patterns.html>Fonte: Pattern di progettazione di software scalabile</a></i>
</p>

I Bilanciatori di carico distribuiscono le richieste dei clienti in arrivo a risorse di calcolo come server e database. In ogni caso, il bilanciatore di carico riporta la risposta dalla risorsa al cliente appropriato. I bilanciatori di carico sono molto effficenti a:

* Evitare che le richieste finiscano a server malsani
* Evitare un sovraccarico di risorse
* Aiutare ad eliminare i singoli punti di vulnerabilità

I bilanciatori di carico possono essere implementati sia tramite hardware (che risulta, però, essere meno economico) o tramite software come HAProxy.

Ulteriori benefici includono:

* **Terminazioni SSL** - Decifrare richieste in arrivo e cifrare risponse dei server in modo tale che i server back-end non debbano eseguire queste potenzialmente complicate operazioni
	* Rimuovono la necessità di installare i [certificati X.509](https://it.wikipedia.org/wiki/X.509) su ogni server
* **Persistenza di sessione** - Distribuiscono cookies e indirizzano le richieste di uno specifico client alla stessa istanza del server se le applicazioni web non mantengono traccia delle sessioni

PEr proteggere da fallimenti, è comune impostare diversi bilanciatori di carico, o in modalità [attiva-passiva](#attiva-passiva) o [attiva-attiva](#attiva-attiva)

I bilanciatori di carico possono instradare il traffico in base a diverse metriche, includendo:

* Casuale
* Meno carico
* Sessione/cookies
* [Round Robin o Round Robin ponderato](http://g33kinfo.com/info/archives/2657)
* [Livello 4](#bilanciamento-di-carico-al-livello-4)
* [Livello 7](#bilanciamento-di-carico-al-livello-7)

### Bilanciamento di carico al Livello 4

I bilanciatori di carico di Livello 4 controllano le informazioni al [livello di trasporto](#comunicazione) per decidere come distribuire le richieste. In genere, questo include l'origine, l'indirizzo IP di destinazione, ma non i contenuti del pacchetto. I bilanciatori di carico di livello 4 inoltrano i pacchetti di rete da e al server attraverso un'operazione di [Network Address Translation (NAT)](https://www.nginx.com/resources/glossary/layer-4-load-balancing/)/

### Bilanciamento di carico al Livello 7

I bilanciatori di carico di Livello 7 controllano le informazioni al [livello di applicazione](#comunicazione) per decidere come distribuire le richieste. Questo può includere contenuti della testata di pacchetto, messaggio e cookies. Un bilanciatore di carico a questo livello termina il traffico di rete, legge il messaggio, prende una decisione e poi apre una connessione con il server selezionato. Per esempio, un bilanciatore di carico di livello 7 può indirizzare traffico video a server che contengono file video, mentre può indirizzare traffico di fatturazione più sensitivo a un server a sicurezza reinforzata.

Pur essendo meno flessibili, bilanciatori di Livello 4 richiedono meno tempo e risorse rispetto a quelli di Livello 7; su hardware odierno, tuttavia, l'impatto può risultare minimo.

### Scalamento orizzontale

I bilanciatori di carico possono anche aiutare con lo scalamento orizzontale, miglioranto prestazioni e disponibilità. Lo scalamento aggiungendo macchine è più efficiente a livello di costi e disponibilità rispetto a spostare il server su una macchina più performante, operazione chiamata **Scalamento Verticale**. È anche più facile trovare impiegati con competenze lavorative su macchine comuni rispetto che a specifici hardware enterprise.

### Svantaggi: scalamento orizzontale

* Scalare orizzontalmente introduce complessità e richiede clonare i server
	* I server dovrebbero essere privi di stato: non dovrebbero contenere alcun dato collegato agli utenti come sessioni o immagini del profilo
	* Le sessioni possono essere salvate in un sistema di memorizzazione di dati centrali come un [Database](#database) (SQL, NoSQL) o in un sistema di [cache persistente](#cache) (Redis, Memcached)
* I server di basso livello come cache e database devono gestire più connessioni allo stesso tempo, più i server di più alto livello scalano orizzontalmente

### Svantaggi: bilanciatori dic arico

* Un bilanciatore di carico rischia di diventare un collo di bottiglia per le prestazioni se non ha abbastanza reisorse o non è configurato a dovere.
* Introdurre un bilanciatore di carico per eliminare i singoli punti di vulnerabilità introduce complessità.
* Un singolo bilanciatore di carico è un singolo punto di vulnerabilità, configurare multipli bilanciatori aumenta la complessità del sistema.

### Risorse e ulteriori spunti di lettura

* [NGINX architecture](https://www.nginx.com/blog/inside-nginx-how-we-designed-for-performance-scale/)
* [HAProxy architecture guide](http://www.haproxy.org/download/1.2/doc/architecture.txt)
* [Scalability](http://www.lecloud.net/post/7295452622/scalability-for-dummies-part-1-clones)
* [Wikipedia](https://en.wikipedia.org/wiki/Load_balancing_(computing))
* [Layer 4 load balancing](https://www.nginx.com/resources/glossary/layer-4-load-balancing/)
* [Layer 7 load balancing](https://www.nginx.com/resources/glossary/layer-7-load-balancing/)
* [ELB listener config](http://docs.aws.amazon.com/elasticloadbalancing/latest/classic/elb-listener-config.html)