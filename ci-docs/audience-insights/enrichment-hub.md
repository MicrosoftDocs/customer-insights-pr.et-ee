---
title: Koondatud kliendiprofiilide rikastamine
description: Kasutage võimalusi kliendiandmete rikastamiseks.
ms.date: 02/07/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 5c3dda3b9bae828857258025ff79958ee22bdb6f
ms.sourcegitcommit: a399bd17523c8d06afd7d78af4fc711f93c0e8be
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 02/07/2022
ms.locfileid: "8098784"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Kliendiprofiilide rikastamine (eelvaade)

Kliendiandmete rikastamiseks saate kasutada andmeid allikatest, nagu Microsoft ja teised partnerid.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Rikastamisekeskuse leht.":::

Minge sihtrühmaülevaadetes jaotisse **Andmed** > **Rikastamine**, et töötada rikastamissuvanditega.  

Rikastamiste loomiseks või redigeerimiseks peavad teil olema kaasautori või administraatori õigused. Lisateavet vt teemast [Õigused](permissions.md).

Vahekaardil **Avastage** leiate kõik toetatud rikastussuvandid.

# <a name="individual-consumers-b-to-c"></a>[Üksikud tarbijad (B-st C-ni)](#tab/b2c)

- [Brändid](enrichment-microsoft.md), mida pakub Microsoft
- [Omandiõigused](enrichment-microsoft.md), mida pakub Microsoft
- [Microsofti pakutavad täiustatud](enrichment-enhanced-addresses.md) aadressid 
- [Demograafiline teave](enrichment-experian.md), mida pakub Experian
- [Kohandatud andmed](enrichment-SFTP-custom-import.md) turvalise failiedastuse protokolli (SFTP) kaudu 
- Microsofti [Azure Maps](enrichment-azure-maps.md)
- [Asukohaandmeid](enrichment-here.md) esitab HERE Technologies 

# <a name="business-accounts-b-to-b"></a>[Ettevõtte kontod (B-st B-ni)](#tab/b2b)

- [Ettevõtte andmeid](enrichment-leadspace.md) esitab Leadspace
- [Microsofti pakutavad täiustatud](enrichment-enhanced-addresses.md) aadressid 
- [Microsofti esitatud täiustatud ettevõtte andmed](enrichment-enhanced-company-data.md)
- [Asukohaandmeid](enrichment-here.md) esitab HERE Technologies 
- [Kohandatud andmed](enrichment-SFTP-custom-import.md) turvalise failiedastuse protokolli (SFTP) kaudu 
- Microsofti [Azure Maps](enrichment-azure-maps.md)
- [Microsofti esitatud konto kaasamise andmed](enrichment-office.md)

---

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

Muude tootjate rikastamised konfigureeritakse kasutades [ühendusi](connections.md), mille administraator koostab volikirjadega ja annab nõusoleku andmete edastamiseks. Administraatorid ja kaasautorid saavad ühendusi kasutada rikastamise konfigureerimiseks.  

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
