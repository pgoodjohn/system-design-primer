*[English](README.md) ∙ [简体中文](README-zh-Hans.md) | [Brazilian Portuguese](https://github.com/donnemartin/system-design-primer/issues/40) ∙ [Japanese](https://github.com/donnemartin/system-design-primer/issues/100) ∙ [Polish](https://github.com/donnemartin/system-design-primer/issues/68) ∙ [Russian](https://github.com/donnemartin/system-design-primer/issues/87) ∙ [Traditional Chinese](https://github.com/donnemartin/system-design-primer/issues/88) ∙ [Turkish](https://github.com/donnemartin/system-design-primer/issues/39) | [Add Translation](https://github.com/donnemartin/system-design-primer/issues/28)*

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

* [Argomenti di progettazione di sistemi: inizia qui](#system-design-topics-start-here).
	* [Passo 1: rivisita la video lezione sulla scalabilità](#step-1-review-the-scalability-video-lecture)
	* [Passo 2: rivisita l'articolo sulla scalabilità](#step-2-review-the-scalability-article)
	* [Passi successivi](#next-steps)
* [Prestazioni vs scalabilità](#performance-vs-scalability)
* [Latenza vs throughput](#latency-vs-throughput)
* [Disponibilità vs coerenza](#availability-vs-consistency)
	* [Il teorema di CAP](#cap-theorem)
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