#reti 
# Usenet
# Public Switched Telephone Network (PSTN)
#nonbroadband
Conosciuto anche come
## Plain Old Telephone Service (POTS)

### Dial Up Connection (narrow Band)
Una connessione dial up usa il POTS per i trasferimenti di dati visto che la connessione è stabilita componendo (chiamando?) un numero di telefono

### Modem (MODulator DEMmodulator)
Prende dati che il computer è in grado di capire e li trasforma in onde sonore che possono essere trasmesse con il POTS

## Baud Rate
Misura di quanti bits possono passare attraverso una linea telefonica in secondi

Di 14.4 Kbps (kilobit per secondo) => velocità di quando è stata commercializzata per i consumatori

# Broadband (Banda Larga)
Qualsiasi tecnologia di connessione che non sia [[Studio/It Support/Bits and Bytes of Networking/Broadband Connections (and more]].md#Dial%20Up%20Connection%20narrow%20Band%7Cdial%20up)  internet
Sono connessioni di lunga durata che non hanno bisogno di essere stabilite ogni volta che si usano

## Digital Subscriber Lines
Si scoprì che una linea telefonica moderna era in grado di trasmettere molti più dati rispetto a quelli richiesti per le sole chiamate vocali (voice to voice). Usando una frequenza che non interferisce con le telefonate normali si sviluppò una tecnologia:

### DSL (Digital Subscriber Line)
E' in grado di spedire molti più dati rispetto alle più tradizionali tecnologie dial-up
Trasferimento di dati e telefonate in contemporanea sulla stessa linea

#### DSLAM (Digital Subscriber Line Access Multiplexer)
<u>**Modem** **DLS**</u>, questi dispositivi stabiliscono connessioni attraverso la linea telefonica ma differentemente dalla connessione dial-up sono di più lunga durata.
La connessione rimane stabilita da quando il modem DLSAM si accende e viene tirata giù quando il modem DLSAM si spegne
![[Studio/It Support/WebPages/Week 5 Google IT Support Professional Certificate 12  Course 2 WEEK 5 Connecting to the Internet — Steemit/modem.jpg]]
#### ADSL (Asymmetric Digital Subscriber Lines)
Velocità differenti in uscita (un minore upload) e in entrata (un maggiore download) 

#### SDSL (Symmetric Digital Subscriber Lines)
Upload e Download sono uguali

#### HDSL (High Bit-rate Digital Subscriber Line)
Tecnologie DSL che vanno oltre 1544 Mbps di velocità

## Cable Broadband
Le compagnie tv via cavo realizzarono presto che anche i loro cavi coassiali (coaxial cable) potevano trasmettere molti altri dati oltre a quelli necessari per far vedere la TV

>[!info]+ Shared Bandwidth
>Il Cable broadband è generalmente usato in  <u>shared bandwidth</u> (banda condivisa) ovvero gli utenti connessi allo stesso cavo condividono la banda di trasferimento, cosa che può risultare in rallentamenti nelle ore con più traffico internet se la banda non basta
> ![[Studio/It Support/WebPages/Week 5 Google IT Support Professional Certificate 12  Course 2 WEEK 5 Connecting to the Internet — Steemit/cable vsdsl.jpg|cable%20vsdsl.jpg]]

### Cable Modem
Dispositivo che sta al bordo di una rete per consumatori e la connette al cable modem termination system

### Cable Modem Termination System (CMTS)
Connette un sacco di cable connection alla rete core di un ISP



# T-Carrier Technologies
Originariamente inventate da AT&T al fine di trasmettere multiple chiamate telefoniche attraverso un unico collegamento (o cavo), usate principalmente dalle imprese/corporazioni/organizzazioni

| Tecnologia T-carrier  | chiamate contemporanee                                                               | Mbit/s |
| --------------------- | ------------------------------------------------------------------------------------ | ------ |
| Transmission System 1 | 24 attraverso singolo [[Studio/It Support/Bits and Bytes of Networking/Physical Layer#Doppino Interlacciato Twisted Pair\|doppino]] | 1544   |
| Transmission System 2 | 28 volte il Transmission System 1 (28*24=672)                                        |  44736      |


# Fibra Ottica
Usa la luce invece della corrente elettrica
## Tipi di fibra
![[Studio/It Support/Bits and Bytes of Networking/Cavi di Rete#^08foh8]]

### FFTX (Fiber to the X)
La "x" può essere una ti tante cose

### FTTP (Fiber To The Premises)
![[Studio/It Support/WebPages/Week 5 Google IT Support Professional Certificate 12  Course 2 WEEK 5 Connecting to the Internet — Steemit/fttn fttb ftth.jpg|fttn%20fttb%20ftth.jpg]]
#### FTTN
Fiber to the neighborhood (fibra al vicinato)
#### FTTB
Fiber to the building/basement/business (fibra all'edificio)
#### FTTH
Fiber to the home (fibra fino in casa)


### ONT (Optical Network Terminator)
Invece che un modem il punto di [[Studio/It Support/Bits and Bytes of Networking/Demarcation Point|demarcazione]] è conosciuto come Optical Network Terminator.

Converte dai protocolli che la rete in fibra può coprire ai protocolli più tradizionali come quello delle reti di [[Studio/It Support/Bits and Bytes of Networking/Physical Layer#Doppino Interlacciato Twisted Pair|doppini interlacciati]]