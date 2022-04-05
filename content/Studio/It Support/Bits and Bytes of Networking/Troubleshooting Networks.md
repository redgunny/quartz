2 concetti molto importanti sono 

# Error Detection
L'abilità di un programma o protocollo di determinare che qualcosa è andato storto

# Error Recovery
Abilità di un programma o protocollo di tentare di riparare/sistemare un problema

# ICMP (Internet Control Message Protocol)
Usato per comunicare problemi di connessione, usato spesso dai router o remote host per comunicare perchè una trasmissione è fallita mandando un "messaggio" all'origine della trasmissione (Fonte)

## ICMP Packet
L'ICMP Header inizia dopo l'header IPv4 che nel campo [[Network Layer#^i9ndhq|"Protocol"]] sarà identificato come "1" (Protocollo 1)
![](https://i.imgur.com/1ky4jL8.png)
### ICMP Packet Fields
- Type [8bit]: il tipo di messaggio che sta venendo spedito (Echo reply[0], Destination Unreachable[3], Time Exceeded[11], Echo Request[8])

- Code[8bit]: Indica una ragione più specifica (Per Destination Unreachable==>Destination <u>network</u> unreachable, Destination <u>port</u> unreachable, Destination host unknown)
![](https://i.imgur.com/EseWfxE.png)

- Rest of Header (Data) [32bit]: Opzionalmente usato da specifici tipi e codici d'errore, per inviare più dati al riguardo

- Payload: Contiene i primi 8 Byte del data payload del pacchetto problematico


## Ping
Programma semplicissimo, ti permette di inviare un tipo speciale di messaggio ICMP chiamato **Echo Request**
### ICMP Echo Request
Chiede semplicemente alla destinazione "hey ci sei?", se la destinazione è connessa e funzionante manderà un **ICMP Echo Reply**
### ICMP Echo Reply
Risposta alla [[Troubleshooting Networks#ICMP Echo Request|Echo Request]] nel caso il computer sia connesso e funzionante invierà la echo reply al mittente dell'Echo Request

>[!attention]- Ping
>Ping o una sua variante può essere usato come metodo d'attacco Distributed Denial of Service 
### Uso Windows

```
ping -opzioni ipdestinazione
```

## Traceroute
uno strumento (utility) che ti permette di scoprire gli indirizzi dei router fra te e l'indirizzo di destinazione, ovvero il percorso tra 2 nodi.
Ti da informazioni su ogni "Hop" lungo il percorso.

Si occupa di ricavare il percorso seguito dai pacchetti sulle reti informatiche, utilizzando la manipolazione del campo TTL settandolo a partire da 1 e aumentandolo di 1 fino al raggiungimento dell'IP di destinazione

>[!info]+ Simili
>Linux/Mac Os: mtr
>Windows: pathping
>che funzionano come dei "lunghi" traceroute così si può vedere meglio come le cose cambino nel tempo

### Uso Windows
```
tracert ipdestinazione
```

### Uso Mac/Linux
```
traceroute ipdestinazione
```

# Testing Port Connectivity
Utilities per testare il corretto funzionamento delle [[Transport Layer#Porta Port|porte]].

## Linux/MacOS
Viene utilizzato netcat 

```
nc host(hostname o ip) portnumber
```
Esempio:
```
nc google.com 80
```
Se funziona il "cursore" (solitamente ">" o "**|**") del terminale lampeggierà aspettando un input.

Se sei solo curioso dello stato delle porta puoi eseguire il comando con la flag `-z` (zero input-output mode)
Con la flag `-v` (verbose) aggiunge più dati rendendo il risultato del comando più comprensibile

Esempio:

```
nc -z -v google.com 80
```
## Windows Powershell
Viene utilizzato `test-netconnection`
- Flag `-port` per testare la connettività di una porta specifica

# Name Resolution Tools (DNS)

## nslookup
Utilizzo:
```
nslookup hostname
```

### Sessione interattiva
Per avviare la sessione nslookup interattiva inserire solo:
```
nslookup
```

In modalità interattiva se inserisci l'IP di un server DNS con `server ipdelserverdns` tutte le name query saranno provate usando quel server DNS invece che quello di default impostato sul pc in uso
Esempio
```
>nslookup
>8.8.8.8
```

## Flag addizionali
### set type
Puoi inserire `set type = recourcerecordtype` per specificare il tipo di [[Name Resolution#Resource Records Types|resource record type]] che vuoi venga restituito (di default restituirà [[Name Resolution#A Record|A Record]] )
### set debug
Puoi inserire `set debug` , questo permetterà allo strumento di visualizzare i pacchetti di risposta per intero, incluse le richieste intermediarie 
