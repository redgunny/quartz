# Layer di Rete
#TCP/IP #Network_Layer #reti 

![[Studio/It Support/Bits and Bytes of Networking/Modello TCP IP#^5bomxv]]
In una LAN i nodi possono comunicare tra di loro tramite mac address ma per poter comunicare con nodi e host di un'altra rete c'è bisogno dell:
## Indirizzo IP (Internet Protocol)
#IP
- Composto da 32 bit spesso divisi in quattro ottetti (8bit)
- Solitamente rappresentato da 4 numeri decimali separati dal punto (dotted decimal notation)
Gli indirizzi IP appartengono a una rete invece che ai dispositivi collegati sulla stessa, l'IP viene fornitogli anche per tempo limitato. Il DHCP si può occupare in modo automatico di assegnare IP ai dispositivi nella rete locale, gli IP assegnati in questo modo vengono definiti <u>**IP dinamici**</u> (gli IP <u>**statici**</u> vengono assegnati manualmente e solitamente a dispostivi di rete e server)

#inserire_immagine 

## Datagramma IPv4 (IP Datagram)
[[Studio/It Support/Bits and Bytes of Networking/Data-Link Layer#Data Packet pacchetto dati|Pacchetto Dati]] del layer 3, è una raccolta di dati altamente strutturati, con campi (fields) ben definiti.

### IPv4 Datagram Header
Ha una dimensione minima di 20 Bytes [128 bit]
#inserire_immagine 
### IPv4 Datagram Fields:
#inserire_immagine 

- # Campi del Datagramma IP (fields):
	- **Version** [4bit]: Quale versione del protocollo IP sta venendo usata
	
	- **Header Length**: Dichiara quanto è lungo l'intero header. Ha un valore fra 5 e 15 che indica quante "righe" da 4 Bytes[32 bit] verranno usate. Quasi sempre la lunghezza dell'<u>**header**</u> IPv4 è di 20 Bytes
	 ^z60t86
	- **Service Type** [8bit]: Specifica dettagli QoS (Quality of Service) per i servizi dei router che possono decidere quali datagrammi sono più importanti
	
	- **Total Length**: Indica la lunghezza totale del [[Studio/It Support/Bits and Bytes of Networking/Network Layer#Datagramma IPv4 IP Datagram |Datagramma IP]] (header+payload)
	
	- **Identification** [16bit]: numero di 16bit che serve a raggruppare i messaggi assieme, usato quando dei programmi hanno dovuto essere divisi
	
	- **Flags Field**: Indica se il programma ha il permesso di essere frammentato o indica sa sia già stato [[Fragmented)](#^k8hk5m|frammentato (Fragmented)]]
	
	- **TTL** (Time To Live, #TTL)[[Studio/It Support/Bits and Bytes of Networking/Alcuni Dispositivi di Rete#Router|Router]]. Solitamente ha un valore di 64.
	 ^2262cc
	- **Protocol**[8bit]: Contiene dati su quale protocollo è usato dal layer di trasporto (TCP/UDP) ^i9ndhq
	
	- **Header Checksum**: Checksum dell'intero [[Studio/It Support/Bits and Bytes of Networking/Network Layer#IPv4 Datagram Header |Datagram header]], visto che il [[#^2262cc|TTL]]  deve essere modificato da ogni router questi dovrà ricalcolare anche il checksum in modo da garantire l'integrità dell'intero datagramma.
	
	- **Source IP** [[Studio/It Support/Bits and Bytes of Networking/Network Layer#Indirizzo IP Internet Protocol|l'indirizzo IP]]  del dispositivo che ha inviato il datagramma ^vry423
	 
	- **Destination IP** [[Studio/It Support/Bits and Bytes of Networking/Network Layer#Indirizzo IP Internet Protocol|l'indirizzo IP]] del dispositivo che deve riceve il datagramma
	
	- **Option Field:** Campo opzionale usato per impostare caratteristiche speciali per i datagrammi, usato  solitamente per scopi di test ^hnn17v
	
	- **Padding:** Visto che l'[[Studio/It Support/Bits and Bytes of Networking/Network Layer#^hnn17v|option field]] è di grandezza variabile, questo campo si assicura che l'header (tramite [[Studio/It Support/Bits and Bytes of Networking/Network Layer#^z60t86|header length]]) sia della lunghezza giusta riempendo lo spazio rimanente di bit con valore 0

>[!NOTE]+ Frammentazione Datagramma (Datagram Fragmentation)
>Processo di prendere un singolo datagramma IP e dividerlo in molteplici più piccoli  ^k8hk5m

## Incapsulamento IP
L'intero contenuto del datagramma IP viene inserito (incapsulato) [[Studio/It Support/Bits and Bytes of Networking/Data-Link Layer#^q8571z|come payload di un frame ethernet ]] 
#inserire_immagine 

## Classi di Indirizzi IP (IP Address classes)
#inserire_immagine 

Sistema per definire come gli indirizzi IP  globali vengono suddivisi fra rete e host

### Classe A
#inserire_immagine 
Primo ottetto usato per gli [[Studio/It Support/Bits and Bytes of Networking/Subnetting#^xc3loc|ID di Rete]], i rimanenti 3 per gli [[Studio/It Support/Bits and Bytes of Networking/Subnetting#^2g7zhu|ID HOST]].
[[Studio/It Support/Bits and Bytes of Networking/Subnetting#Subnet Mask|Subnet Mask]]: 255.0.0.0
### Classe B
#inserire_immagine 
Primi due ottetti usati per gli [[Studio/It Support/Bits and Bytes of Networking/Subnetting#^xc3loc|ID di Rete]], i rimanenti 2 per gli [[Studio/It Support/Bits and Bytes of Networking/Subnetting#^2g7zhu|ID HOST]].
255.255.0.0
### Classe C
#inserire_immagine 
Primi tre ottetti usati per gli [[Studio/It Support/Bits and Bytes of Networking/Subnetting#^xc3loc|ID di Rete]], il rimanente 1 per gli [[Studio/It Support/Bits and Bytes of Networking/Subnetting#^2g7zhu|ID HOST]].
255.255.255.0
### Classe D
Riservata indirizzi multicast
#inserire_immagine 
### Classe E
Riservata utilizzi futuri
#inserire_immagine 

## Protocollo ARP (Address Resolution Protocol)
- Protocollo per scoprire l'indirizzo hardware ([[Studio/It Support/Bits and Bytes of Networking/Data-Link Layer#Mac Address Media Access Control address|MAC Address]]) di un nodo con un determinato IP

- Tabella ARP (ARP Table): Lista di indirizzi IP con associati i loro [[Studio/It Support/Bits and Bytes of Networking/Data-Link Layer#Mac Address Media Access Control address|MAC Address]]  ^92b627

#inserire_immagine 
Nel caso la nostra [[#^92b627|tabella ARP]] non contenga l'associazione IP/mac address del dispositivo ricevente il nostro dispositivo invierà un messaggio ARP in broadcast (al [[Studio/It Support/Bits and Bytes of Networking/Data-Link Layer#Mac Address Media Access Control address|MAC Address]] destinato al broadcast; FF:FF:FF:FF:FF:FF) che viene quindi inviato a tutti i dispositivi nella rete local. Se viene ricevuto dal possessore dell'IP desiderato esso risponderà con un ARP RESPONSE fornendo il proprio [[Studio/It Support/Bits and Bytes of Networking/Data-Link Layer#Mac Address Media Access Control address|MAC Address]] associato al suo IP. Il nostro dispositivo ora aggiornerà la propria ARP table in caso gli serva di nuovo.
Le voci della [[#^92b627|tabella ARP]] scadono dopo un breve periodo 

#inserire_immagine 

# Prossima lezione: [[Studio/It Support/Bits and Bytes of Networking/Subnetting]]
![[Studio/It Support/Bits and Bytes of Networking/Subnetting]]

---

## [[Studio/It Support/Bits and Bytes of Networking/IPv6]]
![[Studio/It Support/Bits and Bytes of Networking/IPv6]]