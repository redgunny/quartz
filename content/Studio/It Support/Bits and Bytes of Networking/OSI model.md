#reti 
# Modello OSI

Il modello "ufficiale" per quando si parla di reti

Aggiunge 2 layer che nel [[Studio/It Support/Bits and Bytes of Networking/Modello TCP IP]] sono inclusi (sottointesi) nell'[[Studio/It Support/Bits and Bytes of Networking/Application Layer]] 

| N°                                                         | Layer Name            | Protocols              | Protocol Data Unit     | Addressing     | Devices                                                                         |
| ---------------------------------------------------------- | --------------------- | ---------------------- | ---------------------- | -------------- | ------------------------------------------------------------------------------- |
| [[#5 Application Layer\|7]]                                | [[Studio/It Support/Bits and Bytes of Networking/Application Layer]] | Http, Https, Smtp, etc | Messages (Messaggi)    | n/a            | Browser, Email Client, etc                                                      |
| 6                                                          | Presentation Layer         |  [TLS](https://it.wikipedia.org/wiki/Transport_Layer_Security),[IPsec](https://it.wikipedia.org/wiki/IPsec)                    |                        |                |                                                                                 |
| 7                                                          | Session Layer                      | SSH,SQL,NetBIOS                       |                        |                |                                                                                 |
| [[Studio/It Support/Bits and Bytes of Networking/Modello TCP IP#4 Transport Layer Layer di trasporto\|4]] | [[Studio/It Support/Bits and Bytes of Networking/Transport Layer]]   | TCP/UDP                | Segments (Segmenti)    | Port Number :# |                                                                                 |
| [[#3 Network Layer Layer di Rete altri_nomi_network\|3]]   | [[Studio/It Support/Bits and Bytes of Networking/Network Layer]]     | IPv4/IPv6              | Datagrams (Datagrammi) | IP Address     | Routers                                                                         |
| [[#2 Data Link Layer altri_nomi\|2]]                       | [[Studio/It Support/Bits and Bytes of Networking/Data-Link Layer]]   | Ethernet/Wifi          | Frames                 | Mac Adress     | Switch                                                                          |
| [[#1 Physical Layer Layer Fisico\|1]]                      | [[Studio/It Support/Bits and Bytes of Networking/Physical Layer]]    | 10 Base T, 802.11      | Bits (0 1)             | n/a            | [[Studio/It Support/Bits and Bytes of Networking/Alcuni Dispositivi di Rete#Hub\|Hubs]], Cavi di Rame, Fibra Ottica, Onde Radio |

## Session Layer
Responsabile di facilitare la comunicazione fra le applicazioni e il layer di trasporto. 
E' la parte del sistema operativo che prende i dati dell'[[Studio/It Support/Bits and Bytes of Networking/Application Layer]] che sono stati decapsulati dai livelli sottostanti e li consegna al layer più in alto

## Presentation Layer
Responsabile di assicurarsi che i dati decapsulati ("spacchettati") siano comprensibili dall'applicazione in questione. 
Questa è la parte del sistema operativo che potrebbe gestire crittazione/decrittazione e compressione dei dati



![](https://i.imgur.com/zBKlhra.png)
