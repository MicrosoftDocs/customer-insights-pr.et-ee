---
title: Koondatud kliendiprofiilide rikastamine
description: Kasutage võimalusi kliendiandmete rikastamiseks.
ms.date: 08/31/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 992c45e30e2dff00f5207290940b56b2fe1c08ad
ms.sourcegitcommit: b9a81c2acd42d774669d2db3d0430c7d81de991c
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 09/02/2021
ms.locfileid: "7469961"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Kliendiprofiilide rikastamine (eelvaade)

Kliendiandmete rikastamiseks saate kasutada andmeid allikatest, nagu Microsoft ja teised partnerid.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Rikastamisekeskuse leht.":::

Minge sihtrühmaülevaadetes jaotisse **Andmed** > **Rikastamine**, et töötada rikastamissuvanditega.  

Rikastamiste loomiseks või redigeerimiseks peavad teil olema kaasautori või administraatori õigused. Lisateavet vt teemast [Õigused](permissions.md).

Vahekaardilt **Avastamine** leiate järgmised rikastamised.

- Microsofti [Azure Maps](enrichment-azure-maps.md)
- [Brändid](enrichment-microsoft.md), mida pakub Microsoft
- [Omandiõigused](enrichment-microsoft.md), mida pakub Microsoft
- [Microsofti pakutavad täiustatud](enrichment-enhanced-addresses.md) aadressid
- [Ettevõtte andmeid](enrichment-leadspace.md) esitab Leadspace
- [Demograafiline teave](enrichment-experian.md), mida pakub Experian
- [Asukohaandmeid](enrichment-here.md) esitab HERE Technologies
- [Kohandatud andmed](enrichment-SFTP-custom-import.md) turvalise failiedastuse protokolli (SFTP) kaudu

Saate kuvada oma konfigureeritud rikastamisi ja redigeerida nende atribuute vahekaardil **Minu rikastamised**.

## <a name="manage-existing-enrichments"></a>Olemasolevate rikastamiste haldamine

Minge vahekaardile **Minu rikastused**, et näha kõiki konfigureeritud rikastusi. Iga rikastamine on esindatud reana, mis sisaldab täiendavat teavet rikastamise kohta.

Valige rikastus, et näha saadaolevaid suvandeid. Valikute nägemiseks võite loendikirjel valida ka ellipsi (...). Kui konfigureerite mitu rikastustegurit, saate selle kiiresti leidmiseks kasutada otsinguvälja.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Rikastamiste haldamise suvandid rikastamiste loendis.":::

- Rikastamise üksikasjade **Vaade** koos rikastatud kliendiprofiilide arvuga.
- Rikastamise konfiguratsiooni **Redigeerimine**.
- Rikastamise **käivitamine**, et värskendada kliendiprofiile uusimate andmetega.
- Olemasoleva rikastamise **Desaktiveerimine**, et peatada selle automaatne värskendamine iga ajastatud värskendamisega. Viimasest edukast värskendamisest pärinevad andmed jäävad jätkuvalt kättesaadavaks. Passiivse rikastamise **Aktiveerimine**, et taaskäivitada automaatne värskendamine iga ajastatud värskendamisega.
- **Kustuta** rikastamine.

Käivitage või desaktiveerige mitu rikastumist korraga, valides need loendist. Kuvamis- ja redigeerimissuvandid pole hulgi toiminguna saadaval. Need töötavad korraga ainult ühes rikastuses.

## <a name="enrichments-and-connections"></a>Rikastamine ja Ühendused

Muude tootjate rikastamised konfigureeritakse kasutades [ühendusi](connections.md), mille administraator koostab volikirjadega ja annab nõusoleku andmete edastamiseks. Ühendusi saavad seejärel kasutada rikastamise konfigureerimiseks nii administraatorid kui ka kaastöötajad.  

## <a name="multiple-enrichments-of-the-same-type"></a>Mitu sama tüüpi rikastust

Rikastatav olem määratakse rikastamise konfiguratsiooni käigus, mis võimaldab teil rikastada ainult osa oma profiilidest. Näiteks saate rikastada andmeid ainult kindla segmendi kohta. Saate konfigureerida mitut sama tüüpi rikastamist ja sama ühendust uuesti kasutada. Mõnel rikastamisel on piiritletud sama tüüpi rikastuste arv, mida saab luua. Piiranguid ja praegust kasutamist saab vaadata lehel **Rikastamine**.

## <a name="see-the-progress-of-the-enrichment-process"></a>Rikastamisprotsessi edenemise kuvamine

Saate otsida rikastamise töötlemise üksikasju (sh olekut ja võimalikke probleeme värskendamise ajal või pärast värskendamist). Aru saada, millised protsessid on seotud rikastamise värskendamisega ja kui kaua kulus protsesside käivitamiseks. Rikastamise olekut toetatakse Experian, Leadspace-i, HERE-tehnoloogiate, SFTP Impordi ja Azure Mapsi puhul.

Rikastamise oleku kuvamine

1. Avage **Andmed** > **Rikastamine**. 
1. Valige vahekaardil **Minu rikastamised** rikastamise olek, et avada külgpaan. 
1. Paanil **Edenemise üksikasjad** laiendage jaotist **Rikastused**. 
1. Valige rikastamise jaotises, kus soovite edenemist näha, suvand **Kuva üksikasjad**. 
1. Klõpsake paanil **Toimingu üksikasjad** käsku **Kuva üksikasjad**, et näha protsesse, mis on seotud rikastamise ja nende oleku värskendamisega. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
