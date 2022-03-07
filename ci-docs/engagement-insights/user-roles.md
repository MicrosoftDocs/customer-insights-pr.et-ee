---
title: Rollid ja õigused
description: Tööruumi liikmete saadaolevate rollide ja õiguste ülevaade.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 68e28caf1c14c23acd506da5f7b441f1e3b72e8b
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645532"
---
# <a name="roles-and-permissions"></a>Rollid ja õigused

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Tööruum on ruum sündmuste ja aruannete talletamiseks ning haldamiseks. Lisateavet leiate teemast [Tööruumi loomine ja liikmete lisamine](create-workspace.md). 

Tööruum võib sisaldada järgmisi rolle ja õigusi:

- *Liikmed* on kasutajad, kes pääsevad tööruumi juurde. Liikmeid saate määrata oma tööruumi ning määratleda nende rolle ja õigusi. 
- *Administraatorid* haldavad tööruume ja keskkondi teiste kasutajate kaasamise ülevaadete konfigureerimiseks. 
- *Toetajad* on suunatud analüütikute poole, kes ei pea kaasamisülevaateid konfigureerima, kuid soovivad luua oma aruandeid, lehte või segmente.

## <a name="permissions"></a>Õigused
  
Järgmine tabel tuvastab iga rolli õigused. 

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
