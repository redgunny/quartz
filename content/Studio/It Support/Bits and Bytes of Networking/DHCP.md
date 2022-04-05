>[!info]-
Per funzionare su una rete con [[Modello TCP IP]] moderna un computer ha bisogno che siano configurate 4 cose:
> 1. Indirizzo IP
> 2. [[Subnetting#Subnet Mask|subnet mask]] della rete locale
> 3. [[Subnetting#^afaac9|Gateway]] (primario)
> 4. [[Name Resolution#Tipi di server DNS|DSN name server]]
> #inserire_immagine 
> 
> Con gli ultimi tre che sono principalmente uguali per ogni nodo nella rete locale e con l'indirizzo IP che invece cambia per ogni nodo

# Dynamic Host Configuration Protocol (DHCP)
Un protocollo dell'[[Application Layer]] che automatizza il processo di configurazione degli host su una rete, utile specialmente se in una rete sono presenti un gran numero di dispositivi.

>[!note]-
>Per un gateway router o per un server il DHCP potrebbe essere meno utile, meglio un IP statico impostato a mano


#inserire_immagine 
## DHCP Dynamic Allocation
Metodo più comune per un protocollo DHCP di impostare gli IP. Un intervallo di indirizzi IP è messo da parte per i client, che possono richiedere che venga assegnato loro un IP, che verrà selezionato da questo intervallo.

Un IP dello stesso dispositivo sotto questo tipo di DHCP potrebbe essere diverso ogni volta che si connette a questa rete

## DHCP Automatic Allocation
Simile alla [[DHCP#DHCP Dynamic Allocation|Dynamic Allocation]] un intervallo di indirizzi IP è messo da parte allo scopo di essere assegnati.
La differenza sta che al server DHCP è chiesto di tenere traccia di quale IP è stato assegnato a un certo dispositivo in passato

Un IP dello stesso dispositivo sotto questo di DHCP dovrebbe essere uguale ogni volta che si connette

## DHCP Fixed Allocation
Richiede di inserire manualmente una lista specifica di Mac address e il loro IP corrispondente.

Può essere utile come misura di sicurezza, ai mac address non elencati non sarà assegnato automaticamente un IP 

>[!note] NTP Server (Network Time Protocol)
>Usato per tenere l'orario di tutti i computer di una rete sincronizzato


## DHCP Discovery
Processo tramite il quale un client configurato per usare il DHCP prova a ottenere informazioni sulla configurazione di rete

### DHCP discover address
![[DHCP%20discover.jpg]]
### DHCP Offer
![[DHCP%20offer.jpg]]
### DHCP Request
![[DHCP%20request.jpg]]
### DHCP ACK
![[dhcpack.jpg]]
### DHCP Lease
Per quanto dura il "prestito" dell'indirizzo IP assegnato dal DHCP, dopo il quale il cliente dovrà ricominciare tutto il [[DHCP#DHCP Discovery|processo]] di nuovo 