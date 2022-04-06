---
title: "Name Resolution"
tags:
- reti 
entabletoc: true
#reti
---

[Servizi di Rete](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Servizi%20di%20Rete.md)
#reti 
# Name Resolution
>[!note]- ICANN
> Internet Corporation for Assigned Names and Numbers. Organizzazione sorella dello IANA, assieme controllano gli indirizzi IP  globali e i sistemi DNS  globali

>[!note] Registrar
>Compagnia che ha un accordo con ICANN per vendere [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Name%20Resolution.md#Domain%20name%20nome%20di%20dominio%7Cnomi%20dominio) ancora non registrati
>Organizzazione responsabile per l'assegnazione di nomi dominio individuali ad altre organizzazioni o individui, le assegnazioni scadono dopo un certo periodo (solitamente un anno) e vanno rinnovate ^al2xn7


## DNS (Domain Name System)
Un sistema per assegnare nomi ai nodi della rete. Indica anche il protocolla che regola  il funzionamento del servizio, i programmi che lo implementano, i server su qui questi vengono elaborati, l'insieme di questi server che cooperano per fornire il servizio più intelligente

Un servizio globale di rete che "risolve"(resolve, "traduce") stringhe di lettere in indirizzi IP al posto tuo.
Sistema che garantisce la risoluzione (cioè la conversione) di nomi host collegati ad una rete (tipo internet) in indirizzi IP e viceversa

>[!example]- Esempi
>Se ad esempio vogliamo raggiungere il sito italiano di Google, scriveremo l'URL, quindi l'indirizzo sotto forma di nome _www.google.it_ .  
Effettuiamo così una richiesta all'interno di una immensa rete (www), e i cosiddetti server di nomi DNS - grazie ai loro database - traducono questo nome "google.it" nell'indirizzo IP corrispondente, indirizzando il nostro computer verso il sito corrispondente, il tutto in alcuni decimi di secondi o pochi secondi.  
Nell'esempio, google.it, come qualsiasi sito Web, ha un indirizzo IP, ed è quello che utilizza il nostro computer tramite un browser e una connessione Internet.

### Domain name (nome di dominio)
>[!info]-
>Chiamati anche nomi DNS

Termine per qualcosa che può essere "risolto" (tradotto) dal [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Name%20Resolution.md#DNS%20Domain%20Name%20System%7CDNS), costruito da una serie di stringhe (testo) separate da punti.

In generale un Nome dominio rappresenta uno (o più) IP, ad esempio un computer utilizzato per accedere ad internet (Host), un server che ospita un sito web o il sito stesso, oppure qualsiasi altro servizio comunicato tramite internet.
>[!example]- esempi vari
>www.example.com 
>www.google.it
>www.goole.com
>it.wikipedia.org
>forum.paradoxplaza.com
>www.crunchyroll.com
>store.steampowered.com
>www.coursera.com
>academyrapido.eduflow.com
>www.academyrapido.com

Usando il [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Name%20Resolution.md#DNS%20Domain%20Name%20System%7CDNS) un organizzazione o un individuo può cambiare in quale IP il proprio [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Name%20Resolution.md#Domain%20name%20nome%20di%20domini%7Cdominio)

Il DNS permette anche di tradurre un nome dominio in IP in base alla regione in cui si trova il client
#### Anatomia di un nome dominio
DNS può supportare fino a 127 livelli di dominio per il totale di un singolo [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Name%20Resolution.md#Fully%20Qualified%20Domain%20Name%20FQDN%7CFQDN) con al massimo 255 caratteri totali, ogni sezione dominio può avere massimo 63 caratteri


##### Fully Qualified Domain Name (FQDN)
Chiamato anche "Absolute domain name"

Ha minimo 3 parti ognuna con un scopo specifico, è la stringa completa che si andrà a digitare nella barra degli indirizzi. E' composto da tutti i domini presenti


![FQDN.excalidraw](Studio/Excalidraw/FQDN.excalidraw.md)
Un nome a dominio pienamente qualificato ([](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Name%20Resolution.md#Fully%20Qualified%20Domain%20Name%20FQDN%7CFQDN)) si distingue per la sua mancanza di ambiguità: può essere interpretato solo in un modo

##### Root Zone
In cima alla gerarchia, rappresentata semplicemente da un punto ("."), solitamente si può omettere ma in alcuni casi potrebbe essere richiesto

##### TLD (Top Level Domain)
Dominio di primo livello, ogni server è responsabile per un TLD diverso (.com, .it, .org, .etc)
"padre" del dominio di secondo livello

##### Dominio di secondo livello (SLD)
Chiamato generalmente dominio, è "figlio" del [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Name%20Resolution.md#TLD%20Top%20Level%20Domain%7CTLD), ovvero è la parte che lo precede. (sottodominio del [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Name%20Resolution.md#TLD%20Top%20Level%20Domain%7CTLD)), "padre" del sottodominio.

##### Sottodominio (dominio dal terzo livello in poi)
Parte di un altro dominio, "figlio" del dominio superiore, si possono avere un sacco di sottodomini

>[!example]- esempio
> www.google.it
> il sottodominio sarà www.
> host.sub.sub.subdomain.domain.tld
> 


### TTL
Tutti i nomi di dominio nel sistema DNS globale hanno un TTL, valore in secondi configurabile dal proprietario del dominio, di quanto a lungo un server (ad esempio un [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Name%20Resolution.md#^t0l6w4%7Cserver%20cache)) possa tenere in cache la traduzione domino=>IP prima di effettuare di nuova una resolution name request e re-immagazzinare l'associazione dominio=IP.

### Tipi di server DNS
Ci sono principalmente 5 tipi di server DNS

1. **Caching Name Resolver**: generalmente forniti dagli ISP. il loro scopo è di immagazzinare un [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Name%20Resolution.md#Domain%20name%20nome%20di%20dominio%7Cnome%20dominio) conosciuto per un periodo di tempo, permette di tenere pronti i nomi più utilizzati senza ogni volta avviare una ricerca  ^t0l6w4

2. **Recursive Name server**: Esegue una Full DNS Resolution Request (DNS Lookup) ^j1msyp

3. **Root Name server**: Responsabili di indirizzare le queries("ricerche") al TLD name server appropriato ^frmrvu

4. **TLD** (Top Level Domain) Name Server: responsabile della parte più a destra di un dominio ^fd92gq

5. **Authoritative** (autoritativi): responsabili per le ultime 2 parti di qualsiasi dominio, tipicamente sotto il controllo di un'organizzazione indipendente o fuori ICANN ^a6447k

### Full Resolution Name Request/DNS Lookup/DNS Request
- Step da parte del Caching Name resolver/Recursive Name Server
	1. Contattare [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Name%20Resolution.md#^frmrvu%7Croot%20name%20server)
	2. Risposta con quale [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Name%20Resolution.md#^fd92gq%7CTLD%20name%20server) da contattare (quale TLD interrogare)
	3. Query [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Name%20Resolution.md#^fd92gq%7CTLD%20name%20server), per ogni TLD in esistenza esiste "un" suo TLD server
	4. Risposta da parte del TLD con il nome dell'[](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Name%20Resolution.md#^a6447k%7CAuthoritative%20server) da contattare
	5. Query delle ultime parti del nome dominio dell'[](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Name%20Resolution.md#^a6447k%7CAuthoritative%20server) 
	6. Risposta da parte dell'[](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Name%20Resolution.md#^a6447k%7CAuthoritative%20server) con l'indirizzo IP associato al dominio
	7. Immagazzinare nella cache del [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Name%20Resolution.md#^t0l6w4%7Cserver%20cache) l'abbinamento IP e dominio (alla scadenza in caso di richiesta DNS il processo dovrà essere ripetuto da capo)

Assicurarsi che le risoluzioni DNS passino attraverso una serie di lookup regolamentati e controllati in modo da ottenere risposte corrette è il modo migliore di proteggersi

>[!Example]- Esempio
>www.wikipedia.org .(root)
>	1. Caching Name server/Recursive Name Server: Root server quale IP ha www.wikipedia.org??
>	2. Root server: Devi contattare il server TLD .org
>	3. Caching Name server/Recursive Name Server: Server TLD del .org che IP ha www.wikipedia.org ??
>	4. .org TLD: devi contattare il [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Name%20Resolution.md#^a6447k%7CAuthoritative%20server) di www.wikipedia
>	5. Caching Name server/Recursive Name Server: [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Name%20Resolution.md#^a6447k%7CAuthoritative%20server) di www.wikipedia  che indirizzo IP ha www.wikipedia.org??
>	6.  [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Name%20Resolution.md#^a6447k%7CAuthoritative%20server)  di www.wikipedia: controllo i miei resource records di www.wikipedia.com ........ che ha come indirizzo IP 208.80.154.224
>	7. Caching Name server/Recursive Name Server: Mi salvo l'abbinamento www.wikipedia.org con IP 208.80.154.224 .. per 24 ore (deciso dai possessori di Wikipedia)

### Resource Records Types
Il DNS opera con un set si resource record types definiti, questi permettono a tipi differenti di risoluzioni dei nomi DNS di avere successo e ottenere l'indirizzo IP associato al domain name

Ci sono dozzine di resource records types definiti i più comuni sono:
#### A Record
Usato per associare un determinato domain name a un determinato IP address. Nel suo uso più basico è configurato per un nome di dominio singolo, ma è possibile per un singolo nome di dominio avere multipli **A Record**. Questo gli permette di usare una tecnica chiamata [DNS Round Robin](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/DNS%20Round%20Robin.md) 
#inserire_immagine 
#### AAAA Record (Quad A)
Molto simile all'[](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Name%20Resolution.md#A%20Record%7CA%20record) solo che restituisce un indirizzo IPv6 invece che IPv4
#inserire_immagine 
#### CName Record (Canonical Name)
Usato per reindirizzare il traffico da un nome dominio all'altro
#inserire_immagine 
#### MX Record (Mail eXchange)
Questo resource type record  viene usato per inviare email al server corretto. Si assicura che il traffico mail venga indirizzato al mail server mentre quello web venga indirizzato al web-server.

Indica a quali server debba essere inviata la posta elettronica per un certo dominio.
#inserire_immagine 

#inserire_immagine 
#### SRV Record (Service)
Simile al [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Name%20Resolution.md#MX%20Record%20Mail%20eXchange%7CMX%20record) usato per definire la posizione di servizi specifici. Ha lo stesso scopo del server MX eccetto per un caso; mentre [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Name%20Resolution.md#MX%20Record%20Mail%20eXchange%7CMX%20record) è solo per servizi mail un SRV record può essere definito per restituire le specifiche di molti tipi di servizi diversi

Identificano il _server_ per un determinato servizio all'interno di un dominio. Possono essere considerati una generalizzazione dei record MX.

#inserire_immagine 
#### TXT Record (TeXT)
Usato per trasmettere dati aggiuntivi da far processare ad altri computer. Ha un campo totalmente libero (free-form)

Associano campi di testo arbitrari a un dominio. Questi campi possono contenere una descrizione informativa oppure essere utilizzati per realizzare servizi.

#inserire_immagine 

---

#### SoA Record(Start of Authority)
Dichiara la zona e il nome del name server che ha autorità sopra di esso
Restituisce informazioni autorevoli sulla zona DNS, incluso il server DNS principale, l'e-mail dell'amministratore, il numero seriale del dominio (utile per sapere se i dati della zona sono stati variati)

#### NS Record:
Indica altri name server che potrebbero essere responsabili di una zona

Delega una zona DNS ad essere gestita da un server DNS autorevole per quel nome di dominio.


#### PTR Record (PoinTer Resource)
Da un IP risolve un nome dominio, grazie al [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Name%20Resolution.md#Reverse%20Lookup%20Zone%20File%7CReverse%20Lookup%20Zone%20File)


--- 
--- 


### DNS Zones
Concetto gerarchico in cui uno specificato server è responsabile per una [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Name%20Resolution.md#DNS%20Zones%7CZona%20DNS) 
| Server dns                                             | Zona responsabilità                                                  |
| ------------------------------------------------------ | -------------------------------------------------------------------- |
| [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Name%20Resolution.md#^frmrvu%5C%7Croot%20name%20server)          | root zone                                                            |
| [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Name%20Resolution.md#^fd92gq%5C%7CTLD%20name%20server)           | ogni TLD è responsabile per la sua specifica zona (.org, .com, .etc) |
| [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Name%20Resolution.md#^a6447k%5C%7CAuthoritative%20name%20server) | Responsabile di zone più dettagliate al disotto, ognuno avrà il suo dominio e sottodomini (www.google,it.wikipedia)                      |                                                                     |

Hanno lo scopo di permettere un più semplice controllo su livelli multipli di un dominio
![](https://i.imgur.com/wIOXxjg.png)
#### Zone Files
Semplici file di configurazione che dichiarano tutti i resource records per una zona in particolare
![](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Name%20Resolution.md#SoA%20Record%20Start%20of%20Authority)

##### Reverse Lookup Zone File
Permettono ai DNS resolver di fornire un indirizzo IP e ottenere il [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Name%20Resolution.md#Fully%20Qualified%20Domain%20Name%20FQDN%7CFQDN) di un dominio




### DNS e UDP
DNS è un ottimo esempio di un servizio dell'[Application Layer](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Application%20Layer.md) che nel [Transport Layer](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Transport%20Layer.md) utilizza il protocollo [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Transport%20Layer.md#Connectionless%20protocols%7CUDP) invece che TCP

Una singola [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Name%20Resolution.md#Full%20Resolution%20Name%20Request%20DNS%20Lookup%20DNS%20Request%7Crichiesta%20DNS) e la sua risposta può solitamente essere contenuta in un singolo datagramma UDP, rendendola la candidata ideale per tale protocollo.

Vale anche la pena dire che il DNS può generare un sacco di traffico

L'UDP è ideale anche perché un [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Name%20Resolution.md#Tipi%20di%20server%20DNS%7Cserver%20DNS) non deve fare nulla solo rispondere alle richieste di lookup in arrivo.

Un [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Name%20Resolution.md#^j1msyp%7CDNS%20resolver) ha il semplice bisogno di effettuare lookups e ripeterli se non hanno successo.

---


## Private DNS Server
Ogni tanto le organizzazioni usano DNS privati internamente in modo da associare IP della rete interna a dispositivi connessi

>[!example]- Esempio
>Assegnare alla stampante 192.168.1.45 il nome stampante.ufficio in modo da usare quel nome invece che digitare l'ip

## DNS as a Service
![](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Name%20Resolution.md#^al2xn7)
### Public DNS Server
Name server specificatamente impostati in modo che chiunque possa usarli, gratuitamente.

La maggioranze dei DNS pubblici risponde agli [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Troubleshooting%20Networks.md#ICMP%20Internet%20Control%20Message%20Protocol%7CICMP%20message) 

>[!example]-
>DNS pubblico google 8.8.8.8
>DNS pubblico Cloudflare 1.1.1.1

# Host Files
Il metodo originale con cui un indirizzo di rete numerato (IP) veniva collegato con delle parole.

Un flat file che contiene in ogni riga un indirizzo di rete(IP) seguito dall' host name
![](https://i.imgur.com/rfV63yy.jpg)

Sul computer dove sta questo host file un utente può digitare www.dominio.ext invece di usare l'indirizzo IP: 123.123.123.123

Gli host file vengono valutati direttamente dallo Network Stack del computer che quindi non starà nemmeno ad interrogare un server DNS

>[!warning]- Host files
>Sono un modo popolare per i virus di interrompere e/o reindirizzare il traffico degli utenti

Tutti i sistemi operativi hanno ancora host files anche per una ragione il **il loopback address**

### Loopback Address 
- IPv4: 127.0.0.1
Ogni host file in esistenza conterrà la linea
>127.0.0.1  localhost

Il loopback address punta sempre a se stesso , quindi è una maniera di mandare traffico di rete a te stesso
Mandare traffico al loopback address bypassa qualsiasi infrastruttura di rete, così il traffico non lascia mai il nodo
