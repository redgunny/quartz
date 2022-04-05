---
title: "Subnetting"
tags:
- sottoreti
- reti
- subnetting
- subnetID
- subnetMASK
- Nework_layer
- Network
- IP 
entabletoc :true
---

# Subnetting
Il processo di suddivisione di prendere una rete più grande e dividerla in più piccole sotto-reti individuali. Le sotto-reti  avranno poi bisogno ognuna di un [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Subnetting.md#^afaac9%7CGateway%20Router) che faccia da ingresso e uscita per la subnet. 

>[!NOTE]+ Gateway Router
>Il gateway router serve da punto di ingresso e uscita da una rete, gli serve l'intero IP comprensivo di [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Subnetting.md#^2g7zhu%7CID%20HOST) per inviare il datagramma al dispositivo desiderato
^afaac9

>[!note]+ Core Router
>Invece un Core Router comunicherà principalmente solo con altri router
>Ai Core Router importa solo dell'[](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Subnetting.md#^xc3loc%7CID%20di%20Rete) che usano per instradare il datagramma al  giusto [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Subnetting.md#^afaac9%7CGateway%20Router) ^s4jvmg

## Subnet ID
Un indirizzo IP viene diviso in 2 parti: ^gs8iaj
- Network ID (ID di rete): "Pezzo", Frazione dell'Indirizzo IP dell'host che ci dice di che rete (o segmento di rete) fa parte servono principalmente ai [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Subnetting.md#^s4jvmg%7CCore%20Routers) ^xc3loc
- Host ID (ID dell'Host): E' il pezzo di un indirizzo IP che riconosce unicamente l'host su una specificata rete. Un host può comunicare direttamente con un altro host solamente se è nella stessa rete, sono necessari ai [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Subnetting.md#^afaac9%7CGateway%20Router) ^2g7zhu

Visto che un singolo ottetto [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Subnetting.md#^2g7zhu%7CID%20HOST) contenuti in essa

Vengono "calcolati" tramite [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Subnetting.md#Subnet%20Mask%7CSubnet%20Mask) (maschera di sottorete)

## Subnet Mask
Numeri di 32 bit (come l'IP) divisi in 4 ottetti e spesso rappresentata con 4 numeri decimali separati dal punto.
Può essere indicata anche con il [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Subnetting.md#CIDR%20(Classless%20Inter-Domain%20Routing)%7CCIDR)
Si possono usare operatori [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Basic%20Binary%20Math.md#Operatore%20AND%7CAND) per determinare se un indirizzo IP esiste sulla stessa rete
#inserire_immagine 

## Host ID generalmente "riservati"
- Come [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Subnetting.md#^2g7zhu%7CHOST%20ID) lo "0" (x.x.x.0) o equivalente non è generalmente usato.

- Mentre il "255" (x.x.x.255) o equivalente è riservato solitamente come indirizzo di Broadcast per la sottorete.

Questo ci indica che normalmente possiamo togliere 2 (-2) possibili indirizzi [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Subnetting.md#^2g7zhu%7CHOST) 
>[!example]- Esempio
ad esempio la rete 192.168.1.0/24 userà come indirizzi [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Subnetting.md#^2g7zhu%7CHOST) solo quelli che vanno da "1" a 254 (255-2 ).
Una rete 192.168.1.128/26 userà come [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Subnetting.md#^2g7zhu%7CHOST) solo quelli che vanno da "129" (lo zero qui "equivale" al 128) a 190  (il 191 qui "equivale" al 255 ovvero l'indirizzo Broadcast"). La rete avrà quindi 64-2 (62) host disponibili

>[!attention]+ Attenzione
>Nonostante non siano usati come [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Subnetting.md#^2g7zhu%7CHOST%20ID) fanno comunque parte della  sottorete


## CIDR (Classless Inter-Domain Routing)
Le [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Network%20Layer.md#Classi%20di%20Indirizzi%20IP%20IP%20Address%20classes%7CClassi%20di%20Indirizzi%20IP) furono il primo tentativo di dividere gli IP globalmente disponibili con il [Subnetting](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Subnetting.md) introdotto quando divenne chiaro che le classi non fossero efficienti. 
Con le [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Network%20Layer.md#Classi%20di%20Indirizzi%20IP%20IP%20Address%20classes%7CClassi%20di%20Indirizzi%20IP) l'[](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Subnetting.md#^xc3loc%7CID%20di%20Rete) era sempre limitato dagli ottetti che andavano usati per intero, senza la possibilità di dividere un singolo ottetto in più (sotto)reti. 

Il [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Subnetting.md#CIDR%20(Classless%20Inter-Domain%20Routing)%7CCIDR) entra qui in gioco, permettendo di riservare singoli bit in un ottetto (invece che l'ottetto intero) come [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Subnetting.md#^xc3loc%7CID%20di%20Rete)

Ovvero permette una nuova notazione della maschera di rete attraverso uno "/" (slash) dopo l'indirizzo IP che indica quanti bit complessivi sono dedicati all'[](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Subnetting.md#^xc3loc%7CID%20di%20Rete)

| Netmask equivalente | CIDR notation | Class  | "Age" | Host Disponibili per rete |
| ------------------- | ------------- | ------ | ----- | ------------------------- |
| 255.0.0.0           | /8            | A      | "Old" | 16777214                  | 
| 255.255.0.0         | /16           | B      | "Old" | 65534                     |
| 255.255.255.0       | /24           | C      | "Old" | 254                       |
| 255.255.240.0       | /20           | "CIDR" | "New" | 4094                      |
| 255.255.255.128     | /25           | "CIDR" | "New" | 126                       |
| 255.255.255.248     | /29           | "CIDR" | "New" | 6                         |
| 224.0.0.0           | /3            | "CIDR" | "New" | 536870910                 |

Per capire in che [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Subnetting.md#^xc3loc%7CID%20di%20Rete) "risiede" un indirizzo host si può usare la [Basic Binary Math](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Basic%20Binary%20Math.md) "comparando" l'IP scelto con la maschera di [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Subnetting.md#Subnet%20Mask%7Cmaschera%20di%20sottorete) scelta
>[!tip]-
>In pratica per ogni bit che verrà "impostato" come [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Subnetting.md#^xc3loc%7CID%20di%20Rete) si andrà a indicare un'intervallo normalmente dedicato agli indirizzi finali (0-255) in più sottoreti.
> - Se prendo il primo bit da sinistra avrò: 255 diviso 2 reti
> 	- Ovvero una rete da 0~127
> 	- E una rete da 128~255
> - Se prendo il primi DUE bit da sinistra avrò 255 diviso 4 reti
> 	- Ovvero Una rete da 0~63
> 	- Una rete da 64~127
> 	- Una rete da 128~191
> 	- Una rete da 191~255
> Essendo Reti diverse un host 192.1.1.54/26 e un host 192.1.1.91/26 non potranno comunicare se non attraverso un router
> Un host 192.1.1.150 e un host 192.1.1.190 invece potranno comunicare direttamente (possibile tramite [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Alcuni%20Dispositivi%20di%20Rete.md#Switch%7C%20Switch))

![Demarcation Point](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Demarcation%20Point.md)