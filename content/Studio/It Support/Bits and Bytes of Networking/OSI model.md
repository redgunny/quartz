#reti 
# Modello OSI

Il modello "ufficiale" per quando si parla di reti

Aggiunge 2 layer che nel [Modello TCP IP](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Modello%20TCP%20IP.md) sono inclusi (sottointesi) nell'[Application Layer](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Application%20Layer.md) 

| N°                                                         | Layer Name            | Protocols              | Protocol Data Unit     | Addressing     | Devices                                                                         |
| ---------------------------------------------------------- | --------------------- | ---------------------- | ---------------------- | -------------- | ------------------------------------------------------------------------------- |
| [7](#5%20Application%20Layer%5C)                                | [Application Layer](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Application%20Layer.md) | Http, Https, Smtp, etc | Messages (Messaggi)    | n/a            | Browser, Email Client, etc                                                      |
| 6                                                          | Presentation Layer         |  [TLS](https://it.wikipedia.org/wiki/Transport_Layer_Security),[IPsec](https://it.wikipedia.org/wiki/IPsec)                    |                        |                |                                                                                 |
| 7                                                          | Session Layer                      | SSH,SQL,NetBIOS                       |                        |                |                                                                                 |
| [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Modello%20TCP%20IP.md#4%20Transport%20Layer%20Layer%20di%20trasporto%5C%7C4) | [Transport Layer](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Transport%20Layer.md)   | TCP/UDP                | Segments (Segmenti)    | Port Number :# |                                                                                 |
| [3](#3%20Network%20Layer%20Layer%20di%20Rete%20altri_nomi_network%5C)   | [Network Layer](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Network%20Layer.md)     | IPv4/IPv6              | Datagrams (Datagrammi) | IP Address     | Routers                                                                         |
| [2](#2%20Data%20Link%20Layer%20altri_nomi%5C)                       | [Data-Link Layer](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Data-Link%20Layer.md)   | Ethernet/Wifi          | Frames                 | Mac Adress     | Switch                                                                          |
| [1](#1%20Physical%20Layer%20Layer%20Fisico%5C)                      | [Physical Layer](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Physical%20Layer.md)    | 10 Base T, 802.11      | Bits (0 1)             | n/a            | [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Alcuni%20Dispositivi%20di%20Rete.md#Hub%5C%7CHubs), Cavi di Rame, Fibra Ottica, Onde Radio |

## Session Layer
Responsabile di facilitare la comunicazione fra le applicazioni e il layer di trasporto. 
E' la parte del sistema operativo che prende i dati dell'[Application Layer](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Application%20Layer.md) che sono stati decapsulati dai livelli sottostanti e li consegna al layer più in alto

## Presentation Layer
Responsabile di assicurarsi che i dati decapsulati ("spacchettati") siano comprensibili dall'applicazione in questione. 
Questa è la parte del sistema operativo che potrebbe gestire crittazione/decrittazione e compressione dei dati



![](https://i.imgur.com/zBKlhra.png)
