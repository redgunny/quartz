
---
title: "Basic Binary Math"
tags:
- math
- matematica
- sistemaBinario
#math #matematica #sistemaBinario
entabletoc :true
---
# Matematica Binaria
elevando 2 alla potenza del numero di bit presenti otteniamo il numero decimale massimo che si può rappresentare

>[!example]-
>8 bit = 2<sup>8</sup> = 256; da 0 a 255
>4 bit = 2<sup>4</sup> = 16; da 0 a 15
>16bit = 2<sup>16</sup> = 65536; da 0 a 65536
## Contare in Binario:

|                                         |                                 |
| --------------------------------------- | ------------------------------- |
| ![left-wrap\|300](binary%2520count.jpg%5C) | ![300](binary%2520addition.jpg%5C) |

L'addizione è conosciuta come uno degli operatori (operators) gli altri due importanti operatori sono:
## Operatore AND
Se entrambi i valori  sono veri(1) allora il risultato sarà vero(1) altrimenti saranno falsi(0)

| bit | operatore | bit | risultato |
| --- | --------- | --- | --------- |
| 1   | AND       | 1   | 1 (true)  |
| 0   | AND       | 0   | 0 (false) |
| 1   | AND       | 0   | 0 (false) |
| 0   | AND       | 1   | 0 (false)          |

## Operatore OR
$$X or Y = Z $$
Se "X" o "Y" sono veri allora "Z" sarà vero, altrimenti sarà falso
Se uno dei due valori è vero(1) allora il risultato sarà vero(1) altrimenti saranno falsi(0)

| bit | operatore | bit | risultato |
| --- | --------- | --- | --------- |
| 1   | OR        | 1   | 1 (true)  |
| 0   | OR        | 0   | 0 (false) |
| 1   | OR        | 0   | 1 (true)  |
| 0   | OR        | 1   | 1 (true)  |

## Calcolo subnet Mask
![Calcolo Subnet Mask 15.40.10.excalidraw](Studio/Excalidraw/Calcolo%20Subnet%20Mask%2015.40.10.excalidraw.md)
