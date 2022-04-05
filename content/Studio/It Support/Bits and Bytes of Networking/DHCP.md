>[!info]-
Per funzionare su una rete con [Modello TCP IP](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Modello%20TCP%20IP.md) moderna un computer ha bisogno che siano configurate 4 cose:
> 1. Indirizzo IP
> 2. [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Subnetting.md#Subnet%20Mask%7Csubnet%20mask) della rete locale
> 3. [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Subnetting.md#^afaac9%7CGateway) (primario)
> 4. [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Name%20Resolution.md#Tipi%20di%20server%20DNS%7CDSN%20name%20server)
> #inserire_immagine 
> 
> Con gli ultimi tre che sono principalmente uguali per ogni nodo nella rete locale e con l'indirizzo IP che invece cambia per ogni nodo

# Dynamic Host Configuration Protocol (DHCP)
Un protocollo dell'[Application Layer](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Application%20Layer.md) che automatizza il processo di configurazione degli host su una rete, utile specialmente se in una rete sono presenti un gran numero di dispositivi.

>[!note]-
>Per un gateway router o per un server il DHCP potrebbe essere meno utile, meglio un IP statico impostato a mano


#inserire_immagine 
## DHCP Dynamic Allocation
Metodo più comune per un protocollo DHCP di impostare gli IP. Un intervallo di indirizzi IP è messo da parte per i client, che possono richiedere che venga assegnato loro un IP, che verrà selezionato da questo intervallo.

Un IP dello stesso dispositivo sotto questo tipo di DHCP potrebbe essere diverso ogni volta che si connette a questa rete

## DHCP Automatic Allocation
Simile alla [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/DHCP.md#DHCP%20Dynamic%20Allocation%7CDynamic%20Allocation) un intervallo di indirizzi IP è messo da parte allo scopo di essere assegnati.
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
![DHCP%20discover.jpg](Studio/It%20Support/WebPages/Week%204%20Google%20IT%20Support%20Professional%20Certificate%2011%20%20Course%202%20WEEK%204%20Networking%20Services%20%E2%80%94%20Steemit/DHCP%20discover.jpg)
### DHCP Offer
![DHCP%20offer.jpg](Studio/It%20Support/WebPages/Week%204%20Google%20IT%20Support%20Professional%20Certificate%2011%20%20Course%202%20WEEK%204%20Networking%20Services%20%E2%80%94%20Steemit/DHCP%20offer.jpg)
### DHCP Request
![DHCP%20request.jpg](Studio/It%20Support/WebPages/Week%204%20Google%20IT%20Support%20Professional%20Certificate%2011%20%20Course%202%20WEEK%204%20Networking%20Services%20%E2%80%94%20Steemit/DHCP%20request.jpg)
### DHCP ACK
![dhcpack](Studio/It%20Support/WebPages/Week%204%20Google%20IT%20Support%20Professional%20Certificate%2011%20%20Course%202%20WEEK%204%20Networking%20Services%20%E2%80%94%20Steemit/dhcpack.jpg)
### DHCP Lease
Per quanto dura il "prestito" dell'indirizzo IP assegnato dal DHCP, dopo il quale il cliente dovrà ricominciare tutto il [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/DHCP.md#DHCP%20Discovery%7Cprocesso) di nuovo 