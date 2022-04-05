E' una tecnica più che essere uno standard definito

Prende un indirizzo IP e lo traduce in un altro (per molte ragioni: dalle questioni di sicurezza al volere semplicemente risparmiare indirizzi IPv4)

# NAT (Network Address Translation)

Tecnologia che permette a un Gateway ( solitamente un [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Subnetting.md#^afaac9%7CRouter) o un firewall) di riscrivere il [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Network%20Layer.md#^vry423%7Csource%20IP) di un [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Network%20Layer.md#IPv4%20Datagram%20Header%7Cdatagramma%20IP) in uscita mentre mantenendo (salvando?) l'IP originale in modo da riscriverlo nella risposta

#inserire_immagine 
![nat%201.jpg](nat%25201.jpg)

Ciò permette di avere 2 tipologie di IP:

1. **IP Pubblici**: 

2. **IP Privati**:


## IP Masquerading
Quello che in pratica sta facendo il router usando la NAT, ovvero nasconder l'IP del client dal Server (in questo caso).
Il NAT è un modo che permette l'IP Masquerading (di mascherare il proprio IP)

Questo previene connessione dirette fra i PC di queste reti

## One to Many NAT
Inoltre è possibile avere molteplici host (PC) a cui l'IP viene "tradotto" dal router che maschererà tutti gli IP dei pc con lo stesso IP NAT


## Nat e il [Transport Layer](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Transport%20Layer.md)
### Port Preservation
Tecnica nella quale la source port scelta dal client è la stessa usata dal router (Le porte per le connessioni in uscita usano una [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Transport%20Layer.md#Ephemeral%20Port%7Cporta%20effimera))

Un router che effettua NAT terrà traccia delle source port e le userà per dirigere il traffico di ritorno al computer giusto

#inserire_immagine 

### Port Forwarding
Una Tecnica dove una specifica porta di destinazione può essere configurata per essere inviata a nodi specifici

Permette il trasferimento dati da un computer ad un altro tramite una specifica [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Transport%20Layer.md#Porta%20Port%7Cporta) di comunicazione.

Permette a un host esterno alla rete di raggiungere un host con indirizzo IP privato
![NAPT-en](Studio/Materiali/NAPT-en.svg)
