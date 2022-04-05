#reti #routing #router #Network_Layer 
![[Studio/It Support/Bits and Bytes of Networking/Alcuni Dispositivi di Rete#Routing Router]]

## Basic Routing
Detto semplicemente:
1. router "A" riceve un [[Studio/It Support/Bits and Bytes of Networking/Data-Link Layer#^8meg81|pacchetto dati]]
2. Esamina i pacchetti dei layer inferiori, de-capsulandoli fino a raggiungere il  datagramma IP ([[Studio/It Support/Bits and Bytes of Networking/Network Layer]])  
3. Esamina l'IP di di destinazione
4. Cerca IP nella sua routing table (tabella routing)
5. Il router inoltra il traffico verso la destinazione tramite l'interfaccia più vicina alla destinazione, incapsulando il datagramma in un nuovo Frame Data-Link e inviandolo sul [[Studio/It Support/Bits and Bytes of Networking/Physical Layer]]
#inserire_immagine 

## Tabella di Routing
La più basica delle tabelle di routing avrà minimo 4 colonne:

| Network di destinazione                                                                                                                                                                                            | Next Hop (Gateway)                                                                                                                                                                     | Total Hops                                                 | Interfaccia (interface)                                              |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------- | -------------------------------------------------------------------- |
| Una riga per ogni rete di cui è a conoscenza in cui saranno inclusi IP e maschera di rete. Ogni tabella avrà generalmente un termine "Catchall" che corrisponde a qualsiasi IP non presente nel suo elenco di reti | Indirizzo IP del prossimo router che deve ricevere i dati per raggiungere la rete di destinazione. Altrimenti dice se questo router è collegato direttamente alla rete di destinazione | Tiene traccia di quanto è lontana la destinazione corrente | Il Router deve sapere a quale interfaccia deve inoltrare il traffico |
| 101.25.67.0/24                                                                                                                                                                                                     | 10.0.0.2                                                                                                                                                                               | 1                                                          | eht3                                                                 |
| default                                                                                                                                                                                                            | 0.0.0.0/0                                                                                                                                                                              | 0                                                          | eth0                                                                 |
| 192.25.67.0/24                                                                                                                                                                                                     | 10.0.0.3                                                                                                                                                                               | 6                                                         | eth5                                                                     |
|                                                                                                                                                                                                                    |                                                                                                                                                                                        |                                                            |                                                                      |
![[Studio/Materiali/routingtable_entry-1.drawio.svg]]![[Studio/Materiali/routingtable_entry2.drawio.svg]]![[Studio/Materiali/routingtable_entry3.drawio.svg]]

---


## Routing Protocols
Modo per i router di imparare cosa gli circonda, protocolli speciali che i router usano per comunicare fra di loro condividendo informazioni, si possono dividere in 2 principali categorie:

### Interior Gateway Protocol
Usato dai router per condividere informazioni all'interno di un [[Studio/It Support/Bits and Bytes of Networking/Autonomous System|Sistema Autonomo]] (autonomous system) condiviso dai routers.
##### Protocolli usati:
- Link-State protocol: Ogni router del  [[Studio/It Support/Bits and Bytes of Networking/Autonomous System|Sistema Autonomo]] pubblicizza lo stato delle sue interfacce tramite algoritmo
  #inserire_immagine 
- Distance Vector protocol: Vecchio standard. Il router condivide la propria [[Studio/It Support/Bits and Bytes of Networking/Routing#Tabella di Routing|routing table]] con i router a cui è collegato. Così facendo condivide informazioni solo con i suoi vicini
- #inserire_immagine 

### Exterior Gateway Protocol
Usato dai router per comunicare dati tra router ai [[Studio/It Support/Bits and Bytes of Networking/Demarcation Point|bordi]] dei [[Studio/It Support/Bits and Bytes of Networking/Autonomous System|Sistemi Autonomi]]


## 
>[!note]+  Iana e ASN
>Lo IANA (Internet Assigned Numbers Authority) oltre che a gestire gli indirizzi IP si occupa anche di assegnare gli ASN (Autonomous System Number). Gli ASN sono numeri assegnati ai vari [[Studio/It Support/Bits and Bytes of Networking/Autonomous System|Sistemi Autonomi]] individuali.
>Formati da 32bit gli ASN vengono rappresentati con un intero numero decimale preceduto dalla sigla "AS".
> - **Ad esempio** AS19604 è assegnato a IBM.
>
>

## Non Routable Address Space
Intervalli di indirizzi IP messi da parte e usabili da chiunque. Nessun gateway router proverà a inoltrare traffico a questo tipo di rete. I nodi però sulla stessa rete di questo tipo saranno comunque liberi di comunicare fra loro.
Questo perché non ogni computer connesso ad internet ha bisogno (o dovrebbe) di comunicare con ogni altro computer.

Potrebbe sembrare limitante ma poi con il 
#### NAT (Network Address translation)
Risolve il limite degli indirizzi non instradabili, permettendo a dispositivi con [[Studio/It Support/Bits and Bytes of Networking/Routing#Non Routable Address Space|non routable address]] di comunicare con gli altri dispositivi su internet 

L'[[Studio/It Support/Bits and Bytes of Networking/Routing#^7f7kkr|RFC]] 1918 definì un numero di reti come non-routable (non instradabili):
>[!note]- RFC (Request For Comment)
>L'RFC è un modo per mettere d'accordo i responsabili di mantenere internet tramite requisiti standard
>
> ^7f7kkr

Questi indirizzi potranno essere instradati solo da protocolli [[Studio/It Support/Bits and Bytes of Networking/Routing#Interior Gateway Protocol|gateway interni]]
| [[Studio/It Support/Bits and Bytes of Networking/Routing#Non Routable Address Space\|non routable address spaces]] |     |
| ------------------------------------------------------------------- | --- |
| 10.0.0.0/8                                                          | Interior Gateway Protocol    | 
| 172.16.0.0/12                                                       |   Interior Gateway Protocol  |
| 198.168.0.0/16                                                      | Interior Gateway Protocol    |




