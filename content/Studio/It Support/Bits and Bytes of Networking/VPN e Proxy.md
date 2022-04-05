Uno dei modi modi più semplici di tenere una rete sicura è quello di usare varie tecnologie in cosicché solo dispositivi fisicamente connessi alla loro rete locale possano accedere possano accedere a queste risorse sulla LAN

MA non sempre è possibile creare ed estendere fisicamente le reti (gli impiegati non sempre sono in ufficio!)

# VPN (Virtual Private Network)
E' una tecnologia che permette l'estensione di una rete (LAN? o comunque privata), agli host che potrebbero non essere presenti (fisicamente) su quella LAN

Le VPN sono un protocollo di tunneling, significa che forniscono l'accesso a qualcosa di non disponibile localmente 
%%Differenze con una VLAN over Internet?%%
Le VPN usano rigorose procedure di autenticazione (login) in modo da assicurarsi che chi abbia l'accesso sia autorizzato ad usare la VPN

>[!info]2 Factor Authentication
>L'autenticazione a due fattori è una tecnica dove si va a richiedere più che la sola combinazione password/username per essere autenticati.
>Ad es. codici SMS o Token Generator possono essere usati oltre al login

## Site on Site Communication
Le VPN usano crittografia per creare un tunnel sicuro per connettere i dispositivi localmente anche se a distanza.

# Proxy Services
Un server che agisce per conto di un client per accedere un altro servizio, ovvero un server che agisce da intermediario per le richiesta
>[!note]- 
>Un gateway rientra di sicuro nella definizione di cosa è un proxy e come funziona


![[Studio/Materiali/Proxy_concept_en.svg]]

## Web Proxies
Proxy costruiti specificatamente per il traffico web, inoltrano le richieste HTTP che arrivano dal Client come normali richieste HTTP ai server

## Reverse Proxy
Un servizio che potrebbe apparire come singolo server a client esterni ma in realtà rappresenta molti Server dietro esso 
![[Studio/Materiali/Reverse_proxy_h2g2bob.svg]]


## Proxy contro NAT
La maggior parte delle volte con il termine proxy ci si riferisce ad un'applicazione del [[Studio/It Support/Bits and Bytes of Networking/Application Layer|livello 7]] del [[Studio/It Support/Bits and Bytes of Networking/OSI model|Modello OSI]].
Ad ogni modo esistono altri modi di "proxare" uno di questi è attraverso il [[Studio/It Support/Bits and Bytes of Networking/Network Layer|Layer 3]] è conosciuto come [[Studio/It Support/Bits and Bytes of Networking/Basics of NAT#NAT Network Address Translation|NAT]]. Le differenze tra queste due tecnologie di realizzare proxy sono il livello in cui operano e la procedura di configurazione dei client e dei server che adottano.

Nella configurazione del client per il proxy di livello 3 (NAT) è sufficiente configurare il gateway. Per quello di livello 7 invece, la destinazione dei pacchetti che genera il client deve essere sempre il server proxy, che legge ogni pacchetto e trova la destinazione reale.

Il NAT poiché opera a livello 3 richiede meno risorse rispetto al proxy di livello 7, ma è allo stesso tempo meno flessibile.
