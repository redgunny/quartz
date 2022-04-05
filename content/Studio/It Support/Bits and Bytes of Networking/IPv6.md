# IPv6
Creato per risolvere la mancanza di abbastanza combinazioni IPv4

Scritto in otto gruppi da 16bit

16bit:16bit:16bit:16bit:16bit:16bit:16bit:16bit

Quattro numeri esadecimali per gruppo

## IPv6 riservati
Tutti quelli inizianti per 2001:0db8 => riservati per documentazioni, educazione, libri e corsi

Tutti quelli inizianti con FF00:: => Indirizzi di multicast, modo per indirizzare traffico a più host alla volta

Tutti quelli inizianti con FE80:: => Link local unicast, premettono a un singolo segmento della rete locale comunicazioni e sono configurate sul mac address. Usata dagli indirizzi IPv6 per ricevere la loro configurazione di rete, neighbor discovery o quando nessun router è presente

## Regole per abbreviare IPv6

1. Si possono rimuovere tutti gli zero a sinistra di un numero (non in mezzo o a destra), in caso ci siano soli zero se ne lascia uno
2. Si possono rimuovere un gruppo consecutivo di 0 rimpiazzandolo con 2 doppi punti (::), si può fare solo una volta per IPv6

## Host e Network ID 
L'IPv6 risolve il problema delle classi di indirizzi IP riconoscendo direttamente la prima metà dell'indirizzo (i primi 64bit, le prime 4 cifre esadecimali) nell'ID di rete e la seconda metà (ultimi 64bit, le ultime 4 cifre esadecimali) all'ID Host

## IPv6 e CIDR
La notazione del CIDR può essere usata anche sugli IPv6

## IPv6 Header 

### IPv6 Header Fields
- Version field[4bit]: Definisce la versione in uso

- Traffic Class field [8bit]: definisce il tipo di traffico contenuto nel datagramma IP e permette a differenti classi di traffico di ricevere priorità diversa

- Flow Label [20bit]: campo usato in congiunzione al <u>traffic class field</u> per far fare ai router decisioni sulla qualità del servizio di uno specifico datagramma

- Payload Length field [16bit]: è il campo che definisce quanto è lungo il data payload del datagramma

- Next Header field [8bit]: concetto unico IPv6, definisce quale tipo di header è presente immediatamente dopo quello corrente. Questi ultimi header sono opzionali, possono essenzialmente essere concatenati per inserire un sacco di opzioni

- Hop Limit [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Network%20Layer.md#^2262cc%7CTTL) di un IPv4

- Source Address [128bit]: Indirizzo da cui il datagramma è stato spedito

- Destination Address [128bit]: Indirizzo di destinazione del datagramma


## IPv6 e IPv4 Harmony
### IPv4 map address space
Qualsiasi IP che inizia con 80 bit con valore "0" (zero), che poi è seguito da 16 bit aventi valore "1" (uno), sono considerati facenti parte degli IPv4

>[!example]
>192.168.1.1 = 0:0:0:FFFF:d1ad:35a7

### IPv6 Tunnel
Server che ricevono il traffico IPv6 in arrivo e lo incapsulano nel più tradizionale IPv4

Consistono di server tunnel IPv6 alle estremità di una connessione

![](https://i.imgur.com/1Yya6pK.jpg)


#### IPv6 Tunnel Broker
Compagnie che provvedono IPv6 tunneling endpoints in modo che tu non debba introdurre equipaggiamento addizionale alla tua rete