---
title: Andmete rikastamise (eelvaade) ülevaade
description: Kliendiandmete rikastamiseks saate kasutada Microsofti ja muude muude tootjate teenuste võimalusi.
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
ms.openlocfilehash: 6b6daab480db5e37830ff58b71dcdd3bbdbe46da
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9053859"
---
# <a name="data-enrichment-preview-overview"></a>Andmete rikastamise (eelvaade) ülevaade

Kliendiandmete rikastamiseks saate kasutada andmeid allikatest, nagu Microsoft ja teised partnerid. Muude tootjate rikastamised konfigureeritakse kasutades [ühendusi](connections.md), mille administraator koostab volikirjadega ja annab nõusoleku andmete edastamiseks. Administraatorid ja kaasautorid saavad ühendusi kasutada rikastamise konfigureerimiseks.  

## <a name="multiple-enrichments-of-the-same-type"></a>Mitu sama tüüpi rikastust

Rikastatav olem määratakse rikastamise konfiguratsiooni käigus, mis võimaldab teil rikastada ainult osa oma profiilidest. Näiteks saate rikastada andmeid ainult kindla segmendi kohta. Saate konfigureerida mitut sama tüüpi rikastamist ja sama ühendust uuesti kasutada. Mõnel rikastamisel on piiritletud sama tüüpi rikastuste arv, mida saab luua. Piiranguid ja praegust kasutust saab vaadata lehe Rikastamine **vahekaardi** Avasta **igal paanil**.

## <a name="enrich-data-sources-before-unification"></a>Andmeallikate rikastamine enne ühendamist

Saate rikastada oma kliendiandmeid enne andmete ühendamist, et aidata parandada andmete vaste kvaliteeti. Lisateavet vt [teemast andmeallikas enrichment](data-sources-enrichment.md).

## <a name="create-an-enrichment"></a>Rikastamise loomine

Rikastamise loomiseks või redigeerimiseks peavad teil olema kaasautori [või administraatori](permissions.md) õigused.

Avage **Andmed** > **Rikastamine**. Vahekaardil **Avasta** kuvatakse kõik toetatud rikastamissuvandid.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Rikastamisekeskuse leht.":::

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

## <a name="manage-existing-enrichments"></a>Olemasolevate rikastamiste haldamine

Avage **Andmed** > **Rikastamine**. **Vaadake vahekaardil Minu rikastamised** konfigureeritud rikastamist, nende olekut, rikastatud klientide arvu ja viimast kord, kui andmeid värskendati. Rikastamiste loendi saate sortida mis tahes veeru järgi või kasutada otsinguvälja, et leida rikastamine, mida soovite hallata.

Valige rikastamine saadaolevate toimingute vaatamiseks.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Rikastamiste haldamise suvandid rikastamiste loendis.":::

- Rikastamise üksikasjade **Vaade** koos rikastatud kliendiprofiilide arvuga.
- Rikastamise konfiguratsiooni **Redigeerimine**.
- [**Käivitage**](#run-or-refresh-enrichments) rikastamine, et värskendada kliendiprofiile uusimate andmetega. Käivitage mitu rikastamist korraga, valides need loendist.
- **Rikastamise aktiveerimine** või **desaktiveerimine**. Mitteaktiivseid rikastamisi ei värskendata plaanitud värskendamise [ajal](system.md#schedule-tab).
- **Kustuta** rikastamine.

Samuti saate rikastamisest luua [segmente](segments.md) või [mõõte](measures.md).

## <a name="run-or-refresh-enrichments"></a>Rikastamiste käivitamine või värskendamine

Pärast käivitamist saab rikastamist värskendada automaatse ajakava alusel või värskendada käsitsi nõudmisel.

1. Ühe või mitme rikastamise käsitsi värskendamiseks valige need ja valige **Käivita**. [Automaatse värskendamise ajastamiseks](system.md#schedule-tab) minge jaotisse **Administraatorisüsteemi** > **·** > **ajakava**. Töötlemisaeg sõltub teie kliendiandmete mahust.

1. Soovi korral [vaadake rikastamisprotsessi edenemist](#see-the-progress-of-the-enrichment-process).

1. Pärast rikastamisprotsessi lõppu minge jaotisse **Minu rikastamised**, et vaadata üle äsja rikastatud kliendiprofiilide andmed, viimase värskenduse aeg ja rikastatud profiilide arv.

1. Valige rikastamine, et näha [rikastamise tulemusi](#view-enrichment-results).

### <a name="see-the-progress-of-the-enrichment-process"></a>Rikastamisprotsessi edenemise kuvamine

Saate otsida rikastamise töötlemise üksikasju (sh olekut ja võimalikke probleeme värskendamise ajal või pärast värskendamist). Aru saada, millised protsessid on seotud rikastamise värskendamisega ja kui kaua kulus protsesside käivitamiseks. Rikastamise olekut toetatakse Experian, Leadspace-i, HERE-tehnoloogiate, SFTP Impordi ja Azure Mapsi puhul.

1. Avage **Andmed** > **Rikastamine**.
1. **Kõrvalpaani avamiseks valige vahekaardil Minu rikastamise olek**.
1. Paanil **Edenemise üksikasjad** laiendage jaotist **Rikastused**.
1. Valige rikastamise jaotises, kus soovite edenemist näha, suvand **Kuva üksikasjad**.
1. Klõpsake paanil **Toimingu üksikasjad** käsku **Kuva üksikasjad**, et näha protsesse, mis on seotud rikastamise ja nende oleku värskendamisega.

## <a name="view-enrichment-results"></a>Rikastamise tulemuste kuvamine

Pärast lõpetatud rikastamisjooksu vaadake üle rikastamise tulemused.

1. Avage **Andmed** > **Rikastamine**.
1. Valige vahekaardil **Minu rikastamine** soovitud rikastamine.

Kõik rikastamised näitavad põhiteavet, nagu rikastatud profiilide arv ja rikastatud profiilide arv aja jooksul. Paanil **Rikastatud kliendid kuvatakse** loodud rikastamise olemi näidis. Üksikasjaliku vaate vaatamiseks valige **Kuva rohkem** ja valige **vahekaart Andmed**.

:::image type="content" source="media/enrichments-results.png" alt-text="Rikastamise tulemuste leht.":::

Kui see on **saadaval, annab põlluga** rikastatud klientide arv süvitsimise iga rikastatud välja katvusse.

Mõned rikastamised näitavad ka rikastamise tüübile vastavat teavet. Lisateavet leiate seotud dokumentatsioonist.

[!INCLUDE [footer-include](includes/footer-banner.md)]
