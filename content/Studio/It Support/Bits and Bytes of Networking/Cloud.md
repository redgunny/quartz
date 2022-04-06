---
title: "Cloud"
tags:
- reti 
entabletoc: true
#reti
---

# Cloud Computing
Nuovo modello nell'informatica dove grandi cluster di macchine ci permetto di usare le risorse dei dispositivi in maniera migliore.

Approccio tecnologico dove le risorse di elaborazione (computing) vengono fornite in un modo condivisibile cosicché un sacco di utenti possano ottenere ciò che vogliono quando lo vogliono.

E' un concetto che si basa su un'idea (un'ideale) che le compagnie forniscano servizi l'una per l'altra

Al cuore del cloud computing c'è una tecnologia conosciuta come Hardware Virtualization

# Hardware Virtualization
Il concetto core (al cuore, al centro) di come funzionano le tecnologie di Cloud Computing.

Permette il concetto di macchina fisica (physical machine/bare metal) e macchina logica (Logical machine/virtual machine?) di essere astratta l'una dall'altra

# Virtualization
Una macchina fisica chiamata host, può eseguire molte istanze virtuali chiamate guest.

Piattaforme di [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Cloud.md#Hardware%20Virtualization%7Cvirtualizzazione%20hardware) fanno uso di un software chiamato **hypervisor**

## Hypervisor
Un software (host) che esegue e gestisce macchine virtuali (VM, Virtual Machines) nel mentre offrendo a questi guest una piattaforma operativa virtuale indistinguibile dal vero hardware (ad esempio un sistema operativo virtualizzato penserà di essere il solo ed al comando e penserà che l'hardware sia vero)
![](https://i.imgur.com/l15lNCz.png)
Grazie ad un hypervisor, su una macchina host possono essere in esecuzione contemporaneamente diverse macchine guest, su ognuna delle quali può girare un sistema operativo diverso che ha il controllo sulle risorse hardware virtualizzate rese disponibili dall'hypervisor

![](https://i.imgur.com/dFXKQOn.jpg)
Inoltre permette di condividere le stesse risorse hardware per tutte le istanze che in base al bisogno è possibile siano allocate dinamicamente
>[!info]-
>Alcuni Hypervisor:
>- Virtualbox
>- VMware ESXi
>- Proxmox
>- QEMU
>- Parallels Desktop 
>- Hyper-V

# Public Cloud
Un largo cluster di macchine gestite da un'altra compagnia/organizzazione

# Private Cloud
usato possibilmente da una grande organizzazione e generalmente fisicamente hostato nei propri locali.

Usato generalmente per conservare le informazioni aziendali più sensibili

# Hybrid Cloud
Termine usato per descrivere situazioni dove le compagnie potrebbero tenere le proprie informazioni più sensibili su un cloud privato e nel mentre affidarsi al public cloud per informazioni meno critiche

# Everything as a Service
![](https://i.imgur.com/ju6W15Z.jpg)

---

![infrastructure-as-a-service-iaas-800x435-1 1](Studio/Materiali/infrastructure-as-a-service-iaas-800x435-1%201.webp)
## Infrastructure as a Service (IaaS)
L'idea è che non devi stare a preoccuparti di costruire la tua rete o costruire il tuo server, paghi invece qualcun altro per farlo

## Platform as a Service (PaaS)
Sottoinsieme del [](Studio/It%20Support/Bits%20and%20Bytes%20of%20Networking/Cloud.md#Cloud%20Computing%7Ccloud%20computing) dove una piattaforma è fornita ai clienti per eseguire i propri servizi. Ciò significa che un execution engine è provvisto per qualunque software a chiunque potrebbe volere eseguire tale software

>[!example]+
>Ad esempio un web dev non ha bisogno di un server intero, ha bisogno solo di un ambiente in cui poter eseguire le proprie app
>Alcune PaaS:
>- Windows Azure

## Software as a Service (SaaS)
Un metodo per concedere la licenza d'uso del software ad altri mentre si tiene lo stesso software hostato e gestito centralmente dall'organizzazione che lo fornisce.

>[!example]-
>Gmail, office 365 outlook, google docs, editor grafici online

## Cloud Storage
Permette di accedere da ovunque ai dati archiviati



