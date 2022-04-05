---
banner: "![[OSI_TCP_IP_large.jpg]]"
banner_y: 0.5
---

#Reti #TCP/IP #Network #Physical_layer #Data-Link_Layer #Network_Layer #Transport_Layer #Application_Layer 



# [[Modello TCP IP]]:

| N°| Layer Name                    | Protocols             | Protocol Data Unit     | Addressing     | Devices                                      |
| --| ----------------------------- | --------------------- | ---------------------- | -------------- | -------------------------------------------- |
| [[#5 Application Layer\|5]] | [[Application Layer]]             | Http, Https, Smtp, etc| Messages (Messaggi)    | n/a            | Browser, Email Client, etc                   |
| [[Modello TCP IP#4 Transport Layer Layer di trasporto\|4]] | [[Transport Layer]]                     | TCP/UDP               | Segments (Segmenti)    | Port Number :# |                                              |
| [[#3 Network Layer Layer di Rete altri_nomi_network\|3]] | [[Network Layer]]                       | IPv4/IPv6             | Datagrams (Datagrammi) | IP Address     | Routers                                      |
| [[#2 Data Link Layer altri_nomi\|2]] | [[Data-Link Layer]]                     | Ethernet/Wifi         | Frames                 | Mac Adress     | Switch                                       |
| [[#1 Physical Layer Layer Fisico\|1]] | [[Physical Layer]] | 10 Base T, 802.11  | Bits (0 1)             | n/a            | [[Alcuni Dispositivi di Rete#Hub\|Hubs]], Cavi di Rame, Fibra Ottica, Onde Radio |

Si compara con il [[OSI model|modello OSI]]

## 1.[[Physical Layer]]:
Rappresenta il dispositivo "fisico" che connette i computer. Il suo obiettivo è quello di gestire il mezzo trasmissivo (Ad esempio: Onde radio, corrente elettrica, segnale cavo) ^a6c30f

---


## 2.[[Data-Link Layer]] Layer: [^altri_nomi]
Responsabile di definire un via comune di interpretare i segnali in modo da fare comunicare i dispositivi nella rete. (Ad esempio: [[#^4093fe |Standard Ethernet]], [[Standard WIFI]]). ^4c42e6


- **Standard Ethernet:** Protocollo responsabile per l'acquisizione di dati sulla stessa rete o collegamento ^4093fe


## 3.[[Network Layer#Layer di Rete|Network Layer]]: [^altri_nomi_network]
Permette a diverse reti di comunicare fra di loro attraverso i Router. I dati possono attraversare molteplici reti e nodi ^5bomxv

- Internetwork: Collezioni di reti connesse tramite routers, la più famosa è Internet
- Protocollo IP: Cuore di internet e reti più piccole
- **Categorie Nodo di rete:** Un Nodo di rete può essere indicato principalmente come Client o Server, in base al suo scopo principale.  ^9b37b2


## 4. Transport Layer:
Si occupa di individuare quale programma client deve inviare dati e quale programma server deve ricevere quei dati. Fa uso principalmente di uno di due protocolli:
- **Protocollo TCP (Transmission Control Protocol):** Si assicura che i dati siano inviati correttamente attendendo conferma dal dispositivo ricevente. ^87c1fb
- **Protocollo UDP (User Datagram Protocol):** Non affidabile quanto il [[#^87c1fb|Protocollo TCP]] ma un po' più veloce



## 5. [[Application Layer]]:
 Primo layer da cui la trasmissione di pacchetti di dati ha inizio, ultimo layer a ricevere pacchetti dei dati, un sacco di protocolli lavorano su questo layer come ad esempio quelli per navigare sui siti internet o ricevere email.![[Client-server-base.excalidraw|right-wrap]]
 
 Un singolo programma può essere definito per la funzione che ha nella rete, quella di richiedere dati (Client) e quella di ricevere richieste e rispondere con i dati (Server)  ^28682e



---
[^altri_nomi]: Altri Nomi: Network Interface Layer, Network Access Layer
[^altri_nomi_network]: Altri Nomi: Internet Layer