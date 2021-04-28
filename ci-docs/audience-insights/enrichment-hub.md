---
title: Koondatud kliendiprofiilide rikastamine
description: Kasutage võimalusi kliendiandmete rikastamiseks.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 10c338b89a6f9971912d05986c105cba1221b01b
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896000"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Kliendiprofiilide rikastamine (eelvaade)

Kliendiandmete rikastamiseks saate kasutada andmeid allikatest, nagu Microsoft ja teised partnerid.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Rikastamisekeskuse leht":::

Minge sihtrühmaülevaadetes jaotisse **Andmed** > **Rikastamine**, et töötada rikastamissuvanditega.    
Rikastamiste loomiseks või redigeerimiseks peavad teil olema kaasautori või administraatori õigused. Lisateavet vt teemast [Õigused](permissions.md).

Vahekaardilt **Avastamine** leiate järgmised rikastamised.

- [Brändid](enrichment-microsoft.md), mida pakub Microsoft
- [Omandiõigused](enrichment-microsoft.md), mida pakub Microsoft
- [Ettevõtte andmeid](enrichment-leadspace.md) esitab Leadspace
- [Demograafilisi andmeid](enrichment-experian.md) esitab Experian
- [Asukohaandmeid](enrichment-here.md) esitab HERE Technologies
- [Kohandatud andmed](enrichment-SFTP-custom-import.md) turvalise failiedastuse protokolli (SFTP) kaudu

Saate kuvada oma konfigureeritud rikastamisi ja redigeerida nende atribuute vahekaardil **Minu rikastamised**.

## <a name="manage-existing-enrichments"></a>Olemasolevate rikastamiste haldamine

Avage **Minu rikastamised**, et näha kõiki konfigureeritud rikastamisi. Iga rikastamine on esindatud reana, mis sisaldab täiendavat teavet rikastamise kohta.

Saadaolevate suvandite kuvamiseks valige rikastamine. Valikute nägemiseks võite loendikirjel valida ka ellipsi (...).

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Rikastamiste haldamise suvandid rikastamiste loendis":::

- Rikastamise üksikasjade **Vaade** koos rikastatud kliendiprofiilide arvuga.
- Rikastamise konfiguratsiooni **Redigeerimine**.
- Rikastamise **käivitamine**, et värskendada kliendiprofiile uusimate andmetega.
- Olemasoleva rikastamise **Desaktiveerimine**, et peatada selle automaatne värskendamine iga ajastatud värskendamisega. Viimasest edukast värskendamisest pärinevad andmed jäävad jätkuvalt kättesaadavaks. Passiivse rikastamise **Aktiveerimine**, et taaskäivitada automaatne värskendamine iga ajastatud värskendamisega.
- Rikastamise **kustutamine**.

Saate korraga käivitada või desaktiveerida mitu rikastamist, valides need loendist. Vaatamise ja redigeerimise suvandid ei ole saadaval hulgitoiminguna ja töötavad korraga ainult ühe rikastamisega.

## <a name="enrichments-and-connections"></a>Rikastamine ja Ühendused

Muude tootjate rikastamised konfigureeritakse kasutades [ühendusi](connections.md), mille administraator koostab volikirjadega ja annab nõusoleku andmete edastamiseks. Ühendusi saavad seejärel kasutada rikastamise konfigureerimiseks nii administraatorid kui ka kaastöötajad.  

## <a name="multiple-enrichments-of-the-same-type"></a>Mitu sama tüüpi rikastust

Rikastatav olem määratakse rikastamise konfiguratsiooni käigus, mis võimaldab teil rikastada ainult osa oma profiilidest. Näiteks rikastage andmeid ainult konkreetse segmendi kohta. Saate konfigureerida mitut sama tüüpi rikastamist ja sama ühendust uuesti kasutada. Mõnel rikastamisel on piiritletud sama tüüpi rikastuste arv, mida saab luua. Piiranguid ja praegust kasutamist saab vaadata lehel **Rikastamine**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
