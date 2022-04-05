# Wireless Networking
un modo per creare una rete senza fili

I dispositivi comunicano fra di loro usando [[Physical Layer|onde radio]]

## Frequency Band (frequenza di banda)
Una certa sezione dello spettro radio (radio spectrum) che è stato concordato per essere utilizzato da certe comunicazioni.

![[frequency%20band.jpg]]

>[!examples]- esempio
>FM broadcast band
>AM broadcast band
>WiFi 2,4 GHz
>WiFi 5 GHz

### Canali (Channels)
Sezioni individuali e più piccole della [[Wireless Technologies#Frequency Band frequenza di banda|frequency band]] usata da una rete wireless usare canali diversi per non interferire con altri segnali aiuta ad evitare un [[Alcuni Dispositivi di Rete#^3b7c91|collision domain]]
![[channel%20overlap.jpg]]


## Protocolli
802.11 definiscono come si opera sia nel layer fisico che [[Data-Link Layer#WI-FI Frame|layer data-link]] 

>[!note]- versioni protocollo 802.11
>Ci sono molte versioni del protocollo 802.11
>802.11b
>802.11a
>802.11g
>802.11n
>802.11ac

## Wireless Network Configuration
### Ad-Hoc Networks
La più semplice configurazione, in una rete ad-hoc non c'è davvero nessuna infrastruttura di supporto. Ogni dispositivo incluso nella rete comunica con ogni altro dispositivo e tutti i nodi aiutano a inoltrare i dati.
![[ad%20hoc%20network.jpg]]
### Wireless LAN (WLAN)
Consiste in uno o più access point che fungono da collegamento (bridge) tra la rete cablata e la rete wireless
![[wireless%20LAN.jpg]]
### Mesh Networking
Un Ibrido con le due precedenti
![[mesh%20network.jpg]]

## Wireless Security
### WEP (Wired Equivalent Privacy)
- Encryption Key = 64bit

Tecnologia di crittazione (encryption) che garantisce una basso livello di privacy e sicurezza

### WPA (WiFi Protected Access)
- Encryption Key = 128bit
### WPA 2 (WiFi Protected Access 2)
Encryption Key = 256 bit
Tecnologia di crittazione (encryption) che garantisce un alto livello di sicurezza

### Mac Filtering
Configurazione dell'access point per permettere connessione solo ai mac address inseriti in una lista impostata


## Cellular Networking (Mobile Networking)
Opera sulle onde radio, possono viaggiare molto più a lungo (lontano). Usano il concetto di celle, celle vicine sono impostare [[Wireless Technologies#Frequency Band frequenza di banda|bande]] che non si sovrappongano
![[cellular%20networks.jpg]]
>[!info]- Metered Connection
>Solitamente le reti cellulari sono metered connection ovvero misurano quanta connessione è stata usata (Download/Upload)




