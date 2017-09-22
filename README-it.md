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