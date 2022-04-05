#Reti 
#Flashcards 
# Hub:
#hub #Physical_layer 
Dispositivo del Layer Fisico che permette connessioni da computer multipli.
Ogni dispositivo connesso invierà i dati a **TUTTI** i dispositivi collegati all'hub, di conseguenza crea un sacco di "rumore" (disturbo) sulla rete potenzialmente creando un [[#^3b7c91|Collision Domain]] ^poyi2b

![[Studio/Materiali/D5zH9SyxCKd9GJ4T6rkBdeqZw1coQAaQyCUzUF4FozBvW7qpdB8h8UunzK81AdMrhhfMUEWe3hZRNfTdVriNeGAMFNVZwvBRMfk4q5QkafxJkpb2M19evr3BDVVQQW3yf1ovzS.jpg]]
>[!NOTE] Collision Domain (Dominio di collisione)
>Un segmento di rete dove può solo comunicare un dispositivo alla volta, se sistemi multipli provano a inviare dati allo stesso tempo gli impulsi elettrici possono interferire l'uno con l'altro 
>Tutti i dispositivi sul segmento di rete ricevono TUTTE le comunicazioni che attraversano l'intero segmento. Ciò significa che c'è bisogno di un modo per identificare il nodo per cui la trasmissione è effettivamente pensata
>^3b7c91

---
# Switch:
#switch #Data-Link_Layer 
Dispositivo del layer 2 (Data-Link) che permette di esaminare i dati che gli passano attraverso per reindirizzarli, così riducendo i disturbi e aumentando l'efficienza. 
Utilizza il Mac Address per reindirizzare il traffico.

#inserire_immagine 

---
# [[Studio/It Support/Bits and Bytes of Networking/Routing|Router]]: 
#router #Network_Layer 
Dispositivo del Layer 3 ([[Studio/It Support/Bits and Bytes of Networking/Network Layer]]) che sa reindirizzare i dati tra reti (Networks) indipendenti. Dispositivo di rete che "inoltra" (instrada) il traffico a seconda dell'indirizzo di destinazione
- Ha almeno due interfacce di rete visto che dev'esse connesso ad almeno 2 reti per poter funzionare (ognuna con un indirizzo)

Il router Controlla gli IP per capire dove spedire i dati. Immagazzinano tabelle di routing ("instradamento") per sapere come reindirizzare i dati a reti diverse.

I router domestici o di piccoli uffici generalmente non hanno tabelle d'instradamento (routing) molto dettagliate

#inserire_immagine 

>[!NOTE]+ **Border Gateway Protocol (BGP):**
>Grazie a questo protocollo i router condividono i dati fra loro, ciò gli permette di scegliere il percorso ottimale per instradare il traffico
  
---
# Servers and Clients:
![[Studio/Excalidraw/Client-server-base.excalidraw]]
- Server: un dispositivo che principalmente fornisce dati quando richiestogli tramite il protocollo necessario
- Client: un dispositivo che principalmente richiede l'invio di dati per utilizzare certe applicazioni
![[Studio/It Support/Bits and Bytes of Networking/Modello TCP IP#^9b37b2]]
![[Studio/It Support/Bits and Bytes of Networking/Modello TCP IP#^28682e]]

#inserire_immagine 

# Firewall
Dispositivo che blocca il traffico che soddisfa determinati criteri (allo stesso modo lascia passare il traffico che ne soddisfa altri)

E' il metodo principale per fermare il traffico che non vuoi che entri in una reti

Possono operare su [[Studio/It Support/Bits and Bytes of Networking/Modello TCP IP|layer differenti]] della rete.


# Wireless Access Point
Dispositivo che collega (crea un ponte, bridge) la porzione di rete cablata alla porzione di rete wireless 


# Disp. Vari
>[!note]- Dispositivi vari per la connessione a internet
>Da [[and more)](Studio/It Support/Bits and Bytes of Networking/Broadband Connections (and more|Broadband Connections (and more)]].md)
>![[Studio/It Support/Bits and Bytes of Networking/Broadband Connections (and more]].md#DSLAM%20Digital%20Subscriber%20Line%20Access%20Multiplexer)
>![[Studio/It Support/Bits and Bytes of Networking/Broadband Connections (and more]].md#Cable%20Modem)
>