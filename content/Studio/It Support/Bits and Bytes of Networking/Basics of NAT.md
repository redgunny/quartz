E' una tecnica più che essere uno standard definito

Prende un indirizzo IP e lo traduce in un altro (per molte ragioni: dalle questioni di sicurezza al volere semplicemente risparmiare indirizzi IPv4)

# NAT (Network Address Translation)

Tecnologia che permette a un Gateway ( solitamente un [[Studio/It Support/Bits and Bytes of Networking/Subnetting#^afaac9|Router]] o un firewall) di riscrivere il [[Studio/It Support/Bits and Bytes of Networking/Network Layer#^vry423|source IP]] di un [[Studio/It Support/Bits and Bytes of Networking/Network Layer#IPv4 Datagram Header|datagramma IP]] in uscita mentre mantenendo (salvando?) l'IP originale in modo da riscriverlo nella risposta

#inserire_immagine 
![[Studio/It Support/WebPages/Week 4 Google IT Support Professional Certificate 11  Course 2 WEEK 4 Networking Services — Steemit/nat 1.jpg|nat%201.jpg]]

Ciò permette di avere 2 tipologie di IP:

1. **IP Pubblici**: 

2. **IP Privati**:


## IP Masquerading
Quello che in pratica sta facendo il router usando la NAT, ovvero nasconder l'IP del client dal Server (in questo caso).
Il NAT è un modo che permette l'IP Masquerading (di mascherare il proprio IP)

Questo previene connessione dirette fra i PC di queste reti

## One to Many NAT
Inoltre è possibile avere molteplici host (PC) a cui l'IP viene "tradotto" dal router che maschererà tutti gli IP dei pc con lo stesso IP NAT


## Nat e il [[Studio/It Support/Bits and Bytes of Networking/Transport Layer]]
### Port Preservation
Tecnica nella quale la source port scelta dal client è la stessa usata dal router (Le porte per le connessioni in uscita usano una [[Studio/It Support/Bits and Bytes of Networking/Transport Layer#Ephemeral Port|porta effimera]])

Un router che effettua NAT terrà traccia delle source port e le userà per dirigere il traffico di ritorno al computer giusto

#inserire_immagine 

### Port Forwarding
Una Tecnica dove una specifica porta di destinazione può essere configurata per essere inviata a nodi specifici

Permette il trasferimento dati da un computer ad un altro tramite una specifica [[Studio/It Support/Bits and Bytes of Networking/Transport Layer#Porta Port|porta]] di comunicazione.

Permette a un host esterno alla rete di raggiungere un host con indirizzo IP privato
![[Studio/Materiali/NAPT-en.svg]]
