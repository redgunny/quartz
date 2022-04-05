#reti

Concetto che comporta l'iterazione (il ciclo, la ripetizione), su un elenco di elementi (indirizzi IP) uno per uno in modo ordinato.

Usato per bilanciare il traffico di un singolo domain name su indirizzi IP multipli

>[!Example] Esempio
>DNS lookup per www.example.com
>Computer <u>**"Z"**</u> cerca l'[[Name Resolution#A Record|A record]] nell'[[Name Resolution#^a6447k|Authoritative server]] per il dominio www.example.com 
>	1.  10.1.1.1
>	2. 10.1.1.2
>	3. 10.1.1.3
>	4. 10.1.1.4
>Il computer DNS resolver (Z in questo caso) sa che deve provare la prima posizione 10.1.1.1 , ma conosce tutti e quattro gli indirizzi IP nel caso la connessione all'IP in prima posizione dovesse fallire
>Ora l'IP in prima posizione slitterà in ultima posizione
>
>Computer <u>**"Y"**</u> cerca l'[[Name Resolution#A Record|A record]] nell'[[Name Resolution#^a6447k|Authoritative server]] per il dominio www.example.com 
>	1.  10.1.1.2
>	2. 10.1.1.3
>	3. 10.1.1.4
>	4. 10.1.1.1
>Il computer DNS resolver (Y in questo caso) sa che deve provare la prima posizione (10.1.1.2)
>e così via facendo...
>
>questo permette di bilanciare il traffico su differenti indirizzi IP

#inserire_immagine 




