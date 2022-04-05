#reti

Concetto che comporta l'iterazione (il ciclo, la ripetizione), su un elenco di elementi (indirizzi IP) uno per uno in modo ordinato.

Usato per bilanciare il traffico di un singolo domain name su indirizzi IP multipli

>[!Example] Esempio
>DNS lookup per www.example.com
>Computer <u>**"Z"**</u> cerca l'[](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Name%20Resolution.md#A%20Record%7CA%20record) nell'[](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Name%20Resolution.md#^a6447k%7CAuthoritative%20server) per il dominio www.example.com 
>	1.  10.1.1.1
>	2. 10.1.1.2
>	3. 10.1.1.3
>	4. 10.1.1.4
>Il computer DNS resolver (Z in questo caso) sa che deve provare la prima posizione 10.1.1.1 , ma conosce tutti e quattro gli indirizzi IP nel caso la connessione all'IP in prima posizione dovesse fallire
>Ora l'IP in prima posizione slitterà in ultima posizione
>
>Computer <u>**"Y"**</u> cerca l'[](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Name%20Resolution.md#A%20Record%7CA%20record) nell'[](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Name%20Resolution.md#^a6447k%7CAuthoritative%20server) per il dominio www.example.com 
>	1.  10.1.1.2
>	2. 10.1.1.3
>	3. 10.1.1.4
>	4. 10.1.1.1
>Il computer DNS resolver (Y in questo caso) sa che deve provare la prima posizione (10.1.1.2)
>e così via facendo...
>
>questo permette di bilanciare il traffico su differenti indirizzi IP

#inserire_immagine 




