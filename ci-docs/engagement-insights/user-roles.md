---
title: Rollid ja õigused
description: Tööruumi liikmete saadaolevate rollide ja õiguste ülevaade.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 07/06/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 6d7f4db4a130fc15a69b380c892538db5492d96d8e13f3c070c6a6b9bd098371
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036688"
---
# <a name="roles-and-permissions"></a>Rollid ja õigused

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Tööruumis saate talletada ja hallata sündmusi ja aruandeid. Liige on kasutaja, kes pääseb tööruumi juurde. Liikmeid saate määrata oma tööruumi ning määratleda nende rolle ja õigusi. Administraatorirollid haldavad tööruume ja keskkondi teiste kasutajate kaasamisülevaadete konfigureerimiseks. Toetajad on suunatud analüütikute poole, kes ei pea kaasamisülevaateid konfigureerima, kuid soovivad luua oma aruandeid, lehtreid või segmente.

## <a name="permissions"></a>Õigused
  
Järgmine diagramm tuvastab iga rolli õiguseid. 

| Õigus | Keskkonna administraator | Tööruumi administraator | Keskkonna kaasautor | Tööruumi kaasautor | 
|--|--|--|--|--|
| Keskkondade loomine (loojast saab automaatselt keskkonnaadministraator) | X* | X* | X* | X* |  
| Konfigureeri keskkond (keskkonnaliikmed, kustuta keskkond) | X |  |  |  |  
| Tööruumide loomine | X |  |  |  |  
| Tööruumide konfigureerimine (tööruumi liikmed, tööruumi kustutamine) | X | X |  |  |  
| Sündmuste ja kalendrisündmuste konfigureerimine | X | X | |  |  
| Tööruumi sündmuste ja nende sündmuste vaatamiseks | X | X | |  |  
| Tööruumi ressursside (aruannete, segmentide ja mõõdiku) kuvamine| X | X | X | X |  
| Kohandatud aruannete ja lehtrite loomine | X | X | X | X |  
| Baasmõõdikute ja dimensioonide loomine| X | X |  |  |  
| Segmentide loomine| X | X | X | X |  

*Saab luua proovikeskkondi ainult eelvaatena. 

## <a name="add-members"></a>Lisa liikmeid

Liikmeid saate tööruumidest ja keskkondadest lisada ning neid sealt eemaldada. Lisateabe saamiseks vaata [Keskkond ja tööruumid](manage-environments-workspaces.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
