---
title: "Network Layer"
tags:
- reti
entabletoc: true
---
# Layer di Rete
#TCP/IP #Network_Layer #reti 

![](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Modello%20TCP%20IP.md#^5bomxv)
In una LAN i nodi possono comunicare tra di loro tramite mac address ma per poter comunicare con nodi e host di un'altra rete c'è bisogno dell:
## Indirizzo IP (Internet Protocol)
#IP
- Composto da 32 bit spesso divisi in quattro ottetti (8bit)
- Solitamente rappresentato da 4 numeri decimali separati dal punto (dotted decimal notation)
Gli indirizzi IP appartengono a una rete invece che ai dispositivi collegati sulla stessa, l'IP viene fornitogli anche per tempo limitato. Il DHCP si può occupare in modo automatico di assegnare IP ai dispositivi nella rete locale, gli IP assegnati in questo modo vengono definiti <u>**IP dinamici**</u> (gli IP <u>**statici**</u> vengono assegnati manualmente e solitamente a dispostivi di rete e server)

#inserire_immagine 

## Datagramma IPv4 (IP Datagram)
[](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Data-Link%20Layer.md#Data%20Packet%20pacchetto%20dati%7CPacchetto%20Dati) del layer 3, è una raccolta di dati altamente strutturati, con campi (fields) ben definiti.

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
	
	- **Total Length**: Indica la lunghezza totale del [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Network%20Layer.md#Datagramma%20IPv4%20IP%20Datagram%20%7CDatagramma%20IP) (header+payload)
	
	- **Identification** [16bit]: numero di 16bit che serve a raggruppare i messaggi assieme, usato quando dei programmi hanno dovuto essere divisi
	
	- **Flags Field**: Indica se il programma ha il permesso di essere frammentato o indica sa sia già stato [](Fragmented)%5D(#^k8hk5m%7Cframmentato%20(Fragmented))
	
	- **TTL** (Time To Live, #TTL)[](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Alcuni%20Dispositivi%20di%20Rete.md#Router%7CRouter). Solitamente ha un valore di 64.
	 ^2262cc
	- **Protocol**[8bit]: Contiene dati su quale protocollo è usato dal layer di trasporto (TCP/UDP) ^i9ndhq
	
	- **Header Checksum**: Checksum dell'intero [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Network%20Layer.md#IPv4%20Datagram%20Header%20%7CDatagram%20header), visto che il [TTL](#%5E2262cc)  deve essere modificato da ogni router questi dovrà ricalcolare anche il checksum in modo da garantire l'integrità dell'intero datagramma.
	
	- **Source IP** [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Network%20Layer.md#Indirizzo%20IP%20Internet%20Protocol%7Cl'indirizzo%20IP)  del dispositivo che ha inviato il datagramma ^vry423
	 
	- **Destination IP** [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Network%20Layer.md#Indirizzo%20IP%20Internet%20Protocol%7Cl'indirizzo%20IP) del dispositivo che deve riceve il datagramma
	
	- **Option Field:** Campo opzionale usato per impostare caratteristiche speciali per i datagrammi, usato  solitamente per scopi di test ^hnn17v
	
	- **Padding:** Visto che l'[](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Network%20Layer.md#^hnn17v%7Coption%20field) è di grandezza variabile, questo campo si assicura che l'header (tramite [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Network%20Layer.md#^z60t86%7Cheader%20length)) sia della lunghezza giusta riempendo lo spazio rimanente di bit con valore 0

>[!NOTE]+ Frammentazione Datagramma (Datagram Fragmentation)
>Processo di prendere un singolo datagramma IP e dividerlo in molteplici più piccoli  ^k8hk5m

## Incapsulamento IP
L'intero contenuto del datagramma IP viene inserito (incapsulato) [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Data-Link%20Layer.md#^q8571z%7Ccome%20payload%20di%20un%20frame%20ethernet%20) 
#inserire_immagine 

## Classi di Indirizzi IP (IP Address classes)
#inserire_immagine 

Sistema per definire come gli indirizzi IP  globali vengono suddivisi fra rete e host

### Classe A
#inserire_immagine 
Primo ottetto usato per gli [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Subnetting.md#^xc3loc%7CID%20di%20Rete), i rimanenti 3 per gli [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Subnetting.md#^2g7zhu%7CID%20HOST).
[](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Subnetting.md#Subnet%20Mask%7CSubnet%20Mask): 255.0.0.0
### Classe B
#inserire_immagine 
Primi due ottetti usati per gli [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Subnetting.md#^xc3loc%7CID%20di%20Rete), i rimanenti 2 per gli [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Subnetting.md#^2g7zhu%7CID%20HOST).
255.255.0.0
### Classe C
#inserire_immagine 
Primi tre ottetti usati per gli [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Subnetting.md#^xc3loc%7CID%20di%20Rete), il rimanente 1 per gli [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Subnetting.md#^2g7zhu%7CID%20HOST).
255.255.255.0
### Classe D
Riservata indirizzi multicast
#inserire_immagine 
### Classe E
Riservata utilizzi futuri
#inserire_immagine 

## Protocollo ARP (Address Resolution Protocol)
- Protocollo per scoprire l'indirizzo hardware ([](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Data-Link%20Layer.md#Mac%20Address%20Media%20Access%20Control%20address%7CMAC%20Address)) di un nodo con un determinato IP

- Tabella ARP (ARP Table): Lista di indirizzi IP con associati i loro [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Data-Link%20Layer.md#Mac%20Address%20Media%20Access%20Control%20address%7CMAC%20Address)  ^92b627

#inserire_immagine 
Nel caso la nostra [tabella ARP](#%5E92b627) non contenga l'associazione IP/mac address del dispositivo ricevente il nostro dispositivo invierà un messaggio ARP in broadcast (al [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Data-Link%20Layer.md#Mac%20Address%20Media%20Access%20Control%20address%7CMAC%20Address) destinato al broadcast; FF:FF:FF:FF:FF:FF) che viene quindi inviato a tutti i dispositivi nella rete local. Se viene ricevuto dal possessore dell'IP desiderato esso risponderà con un ARP RESPONSE fornendo il proprio [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Data-Link%20Layer.md#Mac%20Address%20Media%20Access%20Control%20address%7CMAC%20Address) associato al suo IP. Il nostro dispositivo ora aggiornerà la propria ARP table in caso gli serva di nuovo.
Le voci della [tabella ARP](#%5E92b627) scadono dopo un breve periodo 

#inserire_immagine 

# Prossima lezione: [Subnetting](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Subnetting.md)
![Subnetting](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Subnetting.md)

---

## [IPv6](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/IPv6.md)
![IPv6](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/IPv6.md)