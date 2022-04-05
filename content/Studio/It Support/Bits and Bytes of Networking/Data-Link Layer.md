# Layer Data-Link
#ethernet #mac_address #switch #Data-Link_Layer #reti 
![](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Modello%20TCP%20IP.md#^4c42e6)
Il [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Modello%20TCP%20IP.md#2%20Data-Link%20Layer%20Layer%20altri_nomi%7CData-Link%20Layer) (assieme il protocollo Ethernet) ha il compito di eliminare il bisogno dei layer superiori (Network, Transport, Application) del bisogno di sapere quello che succede nel layer fisico e di che hardware è in uso. In questo modo i layer superiori [^1]  possono funzionare grossomodo in modo indipendente dalla connessione del dispositivo in funzione

>[!INFO]-  Esempi
> Ad esempio il browser non ha bisogno di sapere se si è connessi per avviarsi

>[!NOTE]- CSMA/CD (Carrier Sense Multiple Access w/ Collision Detection)
> Protocollo di rete Ethernet (Layer 2), che risolve il problema dell [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Alcuni%20Dispositivi%20di%20Rete.md#^3b7c91%20%7CCollision%20Domain) in reti utilizzanti l'hub (o qualsiasi altro "ripetitore" del layer fisico). 
> Il Protocollo determina quando i canali di comunicazioni sono liberi e quindi quando un dispositivo è libero di trasmettere i dati ([](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Physical%20Layer.md#Half%20Duplex%20%7CHalf%20Duplex))

## Mac Address (Media Access Control  address):
Indirizzo <u>univoco</u> collegato a una singola interfaccia di rete (NIC, Network Interface Card)

- Formato da 48 Bit rappresentati solitamente da sei gruppi di numeri esadecimali
#inserire_immagine 
- Un altro modo di chiamare un gruppo dell'indirizzo è Octet (Ottetto)
	- **Ottetto:** Nelle reti di computer significa una qualsiasi cifra rappresentata da 8bit 
- Nel caso del Mac Address un ottetto viene rappresentato da 2 cifre Esadecimali
- 2<sup>48</sup> possibili Mac Address 
>[!INFO]- Esempio Mac address
>18-C0-4D-98-E3-38

#inserire_immagine 
- Primi 3 ottetti decisi dall'OUI (Organizationally Unique Identifier)
#inserire_immagine 
- Ultimi 3 ottetti assegnati dal venditore della scheda di rete

## Trasmissione Unicast:
#Unicast
- Pensata solo per un <u>indirizzo ethernet</u>[^2] di ricezione
- Se il bit meno significante del primo ottetto (il primo bit a partire da destra nell'ottetto) è 0 significa che il frame è destinato solo all'indirizzo di destinazione.
#inserire_immagine 
## Trasmissione Multicast:
#Multicast
- SE il bit meno significante del primo ottetto è 1 significa che il frame è multicast, verrà accettato o scartato da ciascun dispositivo in base ai criteri indipendenti dal mac address (le interfacce di rete possono essere configurate per accettare elementi di indirizzi multicast)
#inserire_immagine 
## Trasmissione Broadcast (Layer 2):
#Broadcast
Una trasmissione internet Broadcast viene inviata a ogni singolo indirizzo u una LAN (nel caso del layer fisico).
Eseguita attraverso un indirizzo speciale, il broadcast address.
Usata in modo che i dispositivi possano ricevere prime informazioni l'uno sull'altro

>[!Note] ## Data Packet (pacchetto dati):
#data_packet
Viene così genericamente chiamato ogni singolo insieme di dati binari che attraversano un collegamento di rete. 
Non è legato a nessuna tecnologia in particolare, rappresenta solo un concetto di dati inviati da punto da  punto A ad punto ^8meg81

Un pacchetto di dati di livello 2 con uso dell'Ethernet viene chiamato:
## Ethernet Frames
#Ethernet_Frame #frame #Ethernet_Header
 Raccolta altamente strutturata di informazioni presentate in un ordine specifico. In questo modo possono convertire una stringa di bit in dati.
Quasi tutte le sezioni di un frame ethernet sono obbligatorie e la maggior parte di essi ha quindi la stessa dimensione 
#inserire_immagine 
### Ethernet Frames Fields:

#inserire_immagine 

- ### Campi del Frame Ethernet: ^otqerp
	- Preamble (preambolo) [64 bit, 8 Byte]:  Può essere diviso in 2 sezioni;
		- Un alternanza di 0 e di 1 che fanno da buffer e possono essere usati dalle interfacce di rete per sincronizzarsi i clock interni che usano per regolare la velocità di invio dati [56bit ,7Byte]
		- SFD (Start Frame Delimiter) [8 bit, 1 Byte]: Segnala al dispositivo ricevente che il preambolo è finito e che ora seguirà il contenuto del frame
	- Destination (Mac address) Address [48 bit, 6 Byte]: Indirizzo hardware del dispositivo destinatario desiderato
	- Source (Mac) Address [48 bit, 6 Byte]:  Indirizzo hardware di dove il frame è stato generato
	- Ether-Type [18 bit, 2 Byte]: usato per descrivere il protocollo del contenuto del frame
		- VLAN Header: si potrebbe trovare prima dell [Ether-Type](#VLAN)
	- Payload [Da 46 a 1500 byte]: In termini di "rete" sono gli effettivi dati trasportati, contiene tutti i dati provenienti dai livelli superiori [^1] ^q8571z
	- FCS (Frame Check Sequence) [32 bit, 4 Byte]: numero che rappresenta il valore Checksum dell'intero frame. Il Checksum value è calcolato eseguendo un cyclical redundancy check rispetto al frame ^2cbeac

## Cyclical Redundancy Check (CRC):
#CRC #Checksum #controllo_dati
Concetto importante per l'integrità dei dati (usato un po' ovunque nei computer).
Trasformazione matematica che usa la divisione polinomiale per creare un numero che rappresenta un grande insieme di dati.
Ogni volta che si esegue CRC contro i dati dovrebbe dovresti ottenere lo stesso Checksum number.
Quando un dispositivo si prepara a inviare un frame colleziona tutte l informazioni (tutti i campi dell'header) quindi esegue un CRC contro quei dati e allega il risultato come numero Checksum alla fine del frame ethernet nel [FCS](#%5E2cbeac) 

## VLAN
#VLAN
Tecnica che permetti di avere più LAN logiche che operano sullo stesso equipaggiamento fisico. Ogni frame con il <u>tag VLAN</u> verrà solo consegnato da un interfaccia switch configurata per inoltrare questo specifico <u>tag</u>
#inserire_immagine 
In questo modo è possibile avere solo una rete fisica che funziona come fossero LAN multiple. Vengono solitamente usate per separare diverse fonti di traffico




## WI-FI Frame
### WiFi Frames Fields
- **Frame Control**
	- contiene un numero di sottocampi (subfields) usati per descrivere come il frame andrebbe processato (include la versione di 802.11 usata) 

- **Duration Id** 
	- Specifica quanto è lungo in totale il frame WiFi così il ricevitore (destinatario) sa quanto a lungo deve ascoltare questa trasmissione

- **Source address**
	- Mac address del dispositivo sorgente (inviante)

- **Intended Destination**
	- Mac address di destinazione

- **Receiving address**
	- Mac address dell'access point che dovrebbe ricevere il frame (spesso è lo stesso di destinazione)

- **SCF (Sequence Control Field)**
	- Principalmente contiene un numero di sequenza per tenere conto dell'ordine dei frame 

- **Transmitter address**
	- Mac address di chiunque abbia appena trasmesso il frame (potrebbe essere lo stesso del source address)

- **Data Payload**
	- Tutti i dati dei protocolli superiori
	
- **FCS (Frame Check Sequence)**
	- contiene un checksum usato per un controllo ridondante (esattamente come quello [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Data-Link%20Layer.md#Ethernet%20Frames%20Fields%7Cethernet))

>[!info]- Wireless Access Point (AP)
>![](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Alcuni%20Dispositivi%20di%20Rete.md#Wireless%20Access%20Point)






---
[^1]: Network, Transport, Application
[^2]: Diverso dal mac o IP?