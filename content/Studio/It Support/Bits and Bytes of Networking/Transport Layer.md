#reti
# Layer di Trasporto
Permette al traffico di essere inviato/ricevuto da applicazioni di rete specifiche
![[Studio/It Support/Bits and Bytes of Networking/Modello TCP IP#4 Transport Layer]]

### Multiplexing ([[Studio/It Support/Bits and Bytes of Networking/Transport Layer]])
#inserire_immagine 
Multiplexing nel layer di trasporto significa che i nodi di rete hanno l'abilità di dirigere il traffico verso multipli servizi
### Demultiplexing ([[Studio/It Support/Bits and Bytes of Networking/Transport Layer]])
#inserire_immagine 
Demultiplexing nel layer di trasporto significa che un nodo può ricevere il traffico diretto verso un nodo e consegnarlo verso l'appropriato servizio ricevente

## Porta (Port)
Una porta è un unico numero di 16bit (0-65535) che è usato per dirigere il traffico a un servizio (o servizi) specifico in esecuzione su un computer connesso alla rete

Servizi di rete differenti stanno in ascolto su specifiche porte in attesa([[Studio/It Support/Bits and Bytes of Networking/Alcuni Dispositivi di Rete#Servers and Clients|server]]) di ricevere richieste ([[Studio/It Support/Bits and Bytes of Networking/Alcuni Dispositivi di Rete#Servers and Clients|client]])

Quando scritto dopo i due punti (":") è conosciuto come socket address/socket number/socket port

| Alcuni dei Servizi più conosciuti                        | Porta |
| ------------------------------- | ----- |
| Servizi pagine web HTTP         | 80    |
| Servizi pagine web sicure HTTPS | 443   |
| Servizi eMail                   | 25    |
| Servizi trasferimento file      | 21    |
| Servizio stampa                 | 9100  |

^ifnqih

Il [[Studio/It Support/Bits and Bytes of Networking/Transport Layer|Layer di Trasporto]] usa il concetto di [[Studio/It Support/Bits and Bytes of Networking/Transport Layer#Porta Port|Porte]], il [[Studio/It Support/Bits and Bytes of Networking/Transport Layer#Multiplexing Transport Layer|Multiplexing]] e il [[Studio/It Support/Bits and Bytes of Networking/Transport Layer#Demultiplexing Transport Layer|Demultiplexing]] per inviare dati individualmente ai servizi in ascolto sui nodi di rete. Questa serie di numeri di porte è stata poi suddivisa dallo IANA in sezioni indipendenti

- Porta 0: Non in uso per il traffico di rete ma ogni tanta usata in comunicazioni tra programmi nello stesso computer

### System Port (porte di sistema)
- Porte 1-1023: <u>**System Port**</u> conosciute anche come "<u>well known port</u>", rappresentano le porte ufficiali per i [[Studio/It Support/Bits and Bytes of Networking/Transport Layer#^ifnqih|servizi di rete più conosciuti]] 

### Registered Ports
- Porte 1021-4951: <u>**Registered Port**</u>, porte usate per una serie di altri servizi di rete non conosciuti bene come quelli usanti le [[Studio/It Support/Bits and Bytes of Networking/Transport Layer#System Port porte di sistema|porte di sistema]]. Ogni tanto riconosciute dallo IANA ma non sempre

### Ephemeral Port
- Porte 49152-65535: <u>**Ephemeral Port**</u>, porte effimere o "private". Non possono essere registrate dallo IANA e sono generalmente usate per generare connessioni in uscita. 
  
  >[!Example] Esempio
  >Quando un client vuole comunicare con un server gli verrà assegnata (al Client) una ephemeral port solo per quella connessione, mentre il server è in ascolto su una porta statica (in base al servizio)

>[!info]-  NAT e le Porte
>![[Studio/It Support/Bits and Bytes of Networking/Basics of NAT#Nat e il Transport Layer]]

## Segmento TCP (Transmission Control Protocol segment)
Composto dall'header TCP e una sezione di dati (Payload)
### TCP Header
#inserire_immagine 
### Composizione TCP Header
- **Destination Port** [[Studio/It Support/Bits and Bytes of Networking/Transport Layer#Porta Port|Porta]] del servizio a cui è destinato il traffico

- **Source Port**: [[Studio/It Support/Bits and Bytes of Networking/Transport Layer#Porta Port|Porta]] con un numero alto scelto da una selezione di porte conosciute come ephemeral ports (porte "effimere?"). La source [[Studio/It Support/Bits and Bytes of Networking/Transport Layer#Porta Port|Port]] permette al nostro client di far ricevere i dati all'applicazione che ne aveva fatto richiesta.

- **Sequence Number:** Numero usato per tenere traccia di dove il segmento TCP dovrebbe essere rispetto alla sua sequenza. Tiene traccia di dove in una sequenza di segmenti TCP questo dovrebbe essere (E' il [[Studio/It Support/Bits and Bytes of Networking/Transport Layer]] che si occupa di frammentare i dati in più parti) ^1854f1

- **Acknowledgment Number**: Numero del prossimo [[Studio/It Support/Bits and Bytes of Networking/Transport Layer#Segmento TCP Transmission Control Protocol segment|segmento]] previsto. (es [[Studio/It Support/Bits and Bytes of Networking/Transport Layer#^1854f1|Seq]]=2 [[Studio/It Support/Bits and Bytes of Networking/Transport Layer#^ttyhvl|Ack]]=3 =>Questo è secondo [[Studio/It Support/Bits and Bytes of Networking/Transport Layer#Segmento TCP Transmission Control Protocol segment|segmento]], il prossimo in arrivo sarà il numero tre) ^ttyhvl

 - **Data Offset Field**/**Header Length**: Indica quanto è lungo (grande) il [[Studio/It Support/Bits and Bytes of Networking/Transport Layer#TCP Header|TCP Header]] di questo segmento ^hdt4ae
 
- Empty (spazio vuoto):

- **TCP Control Flags**: campo riservato per le 6 Flag di controllo TCP (URG[0o1]-ACK[0o1]-PSH-RST-SYN-FIN)

- **TCP window**: specifica l'intervallo dei sequence number che potrebbero essere inviati prima che un ACKNOLEDGMENT sia richiesto

- **TCP Checksum**: Controllo dell'integrità dei dati (come in altri layer)

- **Urgent Pointer Field**: Usato in congiunzione con una delle flag di controllo TCP (URG) per indicare che un particolare [[Studio/It Support/Bits and Bytes of Networking/Transport Layer#Segmento TCP Transmission Control Protocol segment|segmento]] potrebbe essere più importante ^yk5t2m

- Option Field: Usato per più complessi controlli di protocolli di flusso

- **Padding**: Sequenza di zero per assicurarsi che il Payload inizi nel punto che ci si aspetta (Indicato dal [[Studio/It Support/Bits and Bytes of Networking/Transport Layer#^hdt4ae|Header Length]])

## TCP Flags
Il modo in cui TCP stabilisce una connessione è tramite le flag di controllo TCP

- **URG**: Un valore di 1 indica che il segmento è urgente e che il campo [[Studio/It Support/Bits and Bytes of Networking/Transport Layer#^yk5t2m|Urgent Pointer]] dell'[[Studio/It Support/Bits and Bytes of Networking/Transport Layer#TCP Header|Header]] ha più dati al riguardo

- **ACK** (Acknowledged): un valore di 1 in questo campo significa che il campo [[Studio/It Support/Bits and Bytes of Networking/Transport Layer#^ttyhvl|Acknowledgment Number]] va esaminato dal dispositivo ricevente
 ^cqoosc
- **PSH**(Push): Il dispositivo di trasmissione(invio) vuole che il dispositivo ricevente "spinga" (push) dati [[Studio/It Support/Bits and Bytes of Networking/Transport Layer#^z4gmun|buffered]] nell'applicazione ricevente il prima possibile 

- **RST** (Reset): significa che una delle parti in una connessione TCP non è stata in grado di recuperare correttamente dati da un serie di segmenti mancanti o malformati. In pratica è una richiesta da una delle due parti di re-iniziare da capo

- **SYN** (Synchronize): Usato la prima volta quando si stabilisce una connessione TCP, assicura che la parte ricevente esamini il campo [[Studio/It Support/Bits and Bytes of Networking/Transport Layer#^1854f1|del numero di sequenza]] 

- **FIN** (Finish): Quando impostato su 1 significa che il computer trasmittente (invio), non ha più dati da inviare la connessione può essere chiusa

##

>[!Note]+ Buffer
>Tecnica di calcolo/computazione dove un certo ammontare di dati viene tenuta da qualche parte prima di essere inviata altrove. Nel TCP serve a inviare grandi "pezzi" di dati in maniera più efficiente.
>Tenendo un certo ammontare di dati in un buffer il TCP può consegnare i dati più significativi ai programmi in attesa di essi. In altri casi potresti star inviando un piccolo ammontare di informazione di cui hai bisogno subito poiché il programma possa rispondere immediatamente
> ^z4gmun




## Three Way Handshake
Metodo In cui la connessione TCP viene stabilita
#inserire_immagine 
![|500x400](https://i.imgur.com/i5L95QN.png)

![[Studio/It Support/WebPages/Week 3 Google IT Support Professional Certificate 9  Course 2 WEEK 3 The Transport and Application Layers  — Steemit/three way handshake.jpg|three%20way%20handshake.jpg]]
Quando entrambi le parti hanno inviato sia un SYN che un ACK, in questo stato una connessione TCP opera in Full Duplex



##

>[!info] Handshake
>Modo per 2 dispositivi di assicurarsi che "parlino" usando lo stesso protocollo e siano quindi in grado di comprendersi

## Four Way Handshake
Usato per per la chiusura della connessione
![](https://i.imgur.com/KiZQ63H.png)
Ipoteticamente una connessione TCP potrebbe restare aperta in modalità Simplex con solo una parte che chiude la connessione, anche se raro.

## Socket
[[Studio/It Support/Bits and Bytes of Networking/Transport Layer#^e3apua|Istanza]] di un endpoint in una potenziale connessione TCP. I socket TCP hanno bisogno di programmi che li istanzino. Si possono mettere in contrapposizione alle porte che sono più una roba virtuale/descrittiva.

In altre parole puoi inviare traffico a qualsiasi porta ma otterrai una risposta solo se il programma (Server/Client) ha aperto un socket su quella porta

>[!Note]+ Istanza (Instantiation)
>L'attuale implementazione di qualcosa definito altrove ^e3apua

## TCP Socket States
- LISTEN
- SYN_SENT
- SYN_RECEIVED
- ENSTABLISHED
- FIN_WAIT
- CLOSE_WAIT
- CLOSED

Esistono altri stati del TCP socket. Inoltre i nomi degli stati potrebbero variare da un sisteama operativo all'altro, questo perchè esistono fuori dalla definizione del protocollo TCP stesso

TCP come protocollo è universale ne suo uso visto che ogni dispositivo "parlante" il protocollo TCP opera nella stessa maniera

# Connection Oriented e Connectionless protocols
## Connection oriented protocols
Stabilisce una connessione e la usa per assicurarsi che tutti i dati siano stati trasmessi correttamente

Una connessione così nel layer di trasporto significa che ogni segmento di dati sia  [[Studio/It Support/Bits and Bytes of Networking/Transport Layer#^cqoosc|ACKnowledged]] (riconosciuto). Così entrambe le parti sanno sempre quale parte di dati è stata <u>sicuramente</u> consegnata correttamente all'altra parte e quale parte non lo è stata

E' Generalmente più sicuro dalle perdite e può tollerare l'arrivo di dati leggermente fuori ordine, ma genera più traffico

- Protocolli connection oriented:
	- TCP

## Connectionless protocols 
- ### UDP (User Datagram Protocol)
	- Non si affida alle connessione e nemmeno supporta il concetto di [[Studio/It Support/Bits and Bytes of Networking/Transport Layer#^cqoosc|ACKnowledgment]]. E' più veloce, usa meno banda ma è anche meno affidabile (i pacchetti persi non vengono rispediti), utile se la perdita di qualche dato non è importante. 
	- Non imposta e smantella una connessione

#inserire_immagine 

# Firewall
![[Studio/It Support/Bits and Bytes of Networking/Alcuni Dispositivi di Rete#Firewall]]