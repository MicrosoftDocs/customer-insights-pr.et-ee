---
title: Koondatud kliendiprofiilide rikastamine
description: Kasutage võimalusi kliendiandmete rikastamiseks.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-enrichments
- ci-enrichment-details
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 3bbe8b829a6698da55d84709dbab6c36aa76792a
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 06/13/2022
ms.locfileid: "8954036"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Kliendiprofiilide rikastamine (eelvaade)

Kliendiandmete rikastamiseks saate kasutada andmeid allikatest, nagu Microsoft ja teised partnerid.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Rikastamisekeskuse leht.":::

Rikastamisvalikutega töötamiseks minge jaotisse **Andmete** > **rikastamine**.  

Rikastamiste loomiseks või redigeerimiseks peavad teil olema kaasautori või administraatori õigused. Lisateavet vt teemast [Õigused](permissions.md).

Vahekaardil **Avastage** leiate kõik toetatud rikastussuvandid.

# <a name="individual-consumers-b-to-c"></a>[Üksikud tarbijad (B-st C-ni)](#tab/b2c)

- [AbiliTec Identity](enrichment-liveramp.md), mida pakub LiveRamp AbiliTec
- [Brändid](enrichment-microsoft.md), mida pakub Microsoft
- [Demograafiline teave](enrichment-experian.md), mida pakub Experian
- [Microsofti pakutavad täiustatud](enrichment-enhanced-addresses.md) aadressid
- [Omandiõigused](enrichment-microsoft.md), mida pakub Microsoft
- [Mapsi esitatud](enrichment-azure-maps.md) asukohaandmed Microsoft Azure
- [Asukohaandmeid](enrichment-here.md) esitab HERE Technologies
- [SFTP kohandatud andmed](enrichment-SFTP-custom-import.md) turvalise failiedastusprotokolli (SFTP) kaudu

# <a name="business-accounts-b-to-b"></a>[Ettevõtte kontod (B-st B-ni)](#tab/b2b)

- [Microsofti esitatud konto kaasamise andmed](enrichment-office.md)
- [Dun & Bradstreet'i esitatud ettevõtte andmed](enrichment-dnb.md)
- [Ettevõtte andmeid](enrichment-leadspace.md) esitab Leadspace
- [Microsofti pakutavad täiustatud](enrichment-enhanced-addresses.md) aadressid
- [Microsofti täiustatud ettevõtte andmed](enrichment-enhanced-company-data.md)
- [Mapsi esitatud](enrichment-azure-maps.md) asukohaandmed Microsoft Azure
- [Asukohaandmeid](enrichment-here.md) esitab HERE Technologies
- [SFTP kohandatud andmed](enrichment-SFTP-custom-import.md) turvalise failiedastusprotokolli (SFTP) kaudu

---

Saate kuvada oma konfigureeritud rikastamisi ja redigeerida nende atribuute vahekaardil **Minu rikastamised**. Samuti saate rikastamisest luua [segmente](segments.md) või [mõõte](measures.md).

## <a name="manage-existing-enrichments"></a>Olemasolevate rikastamiste haldamine

Minge vahekaardile **Minu rikastused**, et näha kõiki konfigureeritud rikastusi. Iga rikastamine on esindatud reana, mis sisaldab täiendavat teavet rikastamise kohta.

Valige rikastus, et näha saadaolevaid suvandeid. Suvandite nägemiseks saate loendiüksusel valida ka vertikaalse kolmikpunkti (&vellip;). Kui konfigureerite mitu rikastustegurit, saate selle kiiresti leidmiseks kasutada otsinguvälja.

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

Rikastatav olem määratakse rikastamise konfiguratsiooni käigus, mis võimaldab teil rikastada ainult osa oma profiilidest. Näiteks saate rikastada andmeid ainult kindla segmendi kohta. Saate konfigureerida mitut sama tüüpi rikastamist ja sama ühendust uuesti kasutada. Mõnel rikastamisel on piiritletud sama tüüpi rikastuste arv, mida saab luua. Piiranguid ja praegust kasutust saab vaadata lehe Rikastamine **vahekaardi** Avasta **igal paanil**.

## <a name="enrich-data-sources-before-unification"></a>Andmeallikate rikastamine enne ühendamist

Saate rikastada oma kliendiandmeid enne andmete ühendamist, et aidata parandada andmete vaste kvaliteeti. Lisateavet vt [teemast andmeallikas enrichment](data-sources-enrichment.md).

## <a name="run-or-refresh-enrichments"></a>Rikastamiste käivitamine või värskendamine

1. Rikastamisprotsessi alustamiseks valige **Käivita**. Või laske süsteemil plaanitud värskenduse osana [rikastamist automaatselt käivitada](system.md#schedule-tab). Töötlemisaeg sõltub teie kliendiandmete mahust.

1. Soovi korral [vaadake rikastamisprotsessi edenemist](#see-the-progress-of-the-enrichment-process).

1. Pärast rikastamisprotsessi lõppu minge jaotisse **Minu rikastamised**, et vaadata üle äsja rikastatud kliendiprofiilide andmed, viimase värskenduse aeg ja rikastatud profiilide arv.

1. Valige rikastamine, et näha [rikastamise tulemusi](#enrichment-results).

### <a name="see-the-progress-of-the-enrichment-process"></a>Rikastamisprotsessi edenemise kuvamine

Saate otsida rikastamise töötlemise üksikasju (sh olekut ja võimalikke probleeme värskendamise ajal või pärast värskendamist). Aru saada, millised protsessid on seotud rikastamise värskendamisega ja kui kaua kulus protsesside käivitamiseks. Rikastamise olekut toetatakse Experian, Leadspace-i, HERE-tehnoloogiate, SFTP Impordi ja Azure Mapsi puhul.

1. Avage **Andmed** > **Rikastamine**.
1. **Kõrvalpaani avamiseks valige vahekaardil Minu rikastamise olek**.
1. Paanil **Edenemise üksikasjad** laiendage jaotist **Rikastused**.
1. Valige rikastamise jaotises, kus soovite edenemist näha, suvand **Kuva üksikasjad**.
1. Klõpsake paanil **Toimingu üksikasjad** käsku **Kuva üksikasjad**, et näha protsesse, mis on seotud rikastamise ja nende oleku värskendamisega.

## <a name="enrichment-results"></a>Rikastamise tulemused

Pärast lõpetatud rikastamisjooksu vaadake üle rikastamise tulemused.

1. Avage **Andmed** > **Rikastamine**.
1. Valige vahekaardil **Minu rikastamine** rikastamine rikastamine, mille kohta soovite teavet saada.

Kõik rikastamised näitavad põhiteavet, nagu rikastatud profiilide arv ja rikastatud profiilide arv aja jooksul. Paanil **Rikastatud kliendid kuvatakse** loodud rikastamise olemi näidis. Üksikasjaliku vaate vaatamiseks valige **Kuva rohkem** ja valige **vahekaart Andmed**.

:::image type="content" source="media/enrichments-results.png" alt-text="Rikastamise tulemuste leht.":::

Kui see on **saadaval, annab põlluga** rikastatud klientide arv süvitsimise iga rikastatud välja katvusse.

Mõned rikastamised näitavad ka rikastamise tüübile vastavat teavet. Lisateavet leiate seotud dokumentatsioonist.

[!INCLUDE [footer-include](includes/footer-banner.md)]
