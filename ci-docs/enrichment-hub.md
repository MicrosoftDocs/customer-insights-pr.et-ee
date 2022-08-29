---
title: Andmete rikastamise (eelvaate) ülevaade
description: Kasutage oma kliendiandmete rikastamiseks Microsofti ja muude kolmandate osapoolte teenuste võimalusi.
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
ms.openlocfilehash: fb747f7adc7d87f30f66c5d0ed20bbe238558fde
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304514"
---
# <a name="data-enrichment-preview-overview"></a>Andmete rikastamise (eelvaate) ülevaade

Kliendiandmete rikastamiseks saate kasutada andmeid allikatest, nagu Microsoft ja teised partnerid. Muude tootjate rikastamised konfigureeritakse kasutades [ühendusi](connections.md), mille administraator koostab volikirjadega ja annab nõusoleku andmete edastamiseks. Administraatorid ja kaasautorid saavad ühendusi kasutada rikastamise konfigureerimiseks.  

## <a name="multiple-enrichments-of-the-same-type"></a>Mitu sama tüüpi rikastust

Rikastatav olem määratakse rikastamise konfiguratsiooni käigus, mis võimaldab teil rikastada ainult osa oma profiilidest. Näiteks saate rikastada andmeid ainult kindla segmendi kohta. Saate konfigureerida mitut sama tüüpi rikastamist ja sama ühendust uuesti kasutada. Mõnel rikastamisel on piiritletud sama tüüpi rikastuste arv, mida saab luua. Piiranguid ja praegust kasutust saab näha igal paanil **lehe Rikastamine** vahekaardil **Avasta**.

## <a name="enrich-data-sources-before-unification"></a>Andmeallikate rikastamine enne ühendamist

Saate rikastada oma kliendiandmeid enne andmete ühendamist, et aidata parandada andmete vaste kvaliteeti. Lisateavet leiate teemast [rikastamise andmeallikas](data-sources-enrichment.md).

## <a name="create-an-enrichment"></a>Rikastamise loomine

Rikastuste loomiseks või redigeerimiseks peavad teil olema kaasautori või administraatori [õigused](permissions.md).

Avage **Andmed** > **Rikastamine**. Vahekaardil **Avasta kuvatakse** kõik toetatud rikastamissuvandid.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Rikastamisekeskuse leht.":::

# <a name="individual-consumers-b-to-c"></a>[Üksikud tarbijad (B-st C-ni)](#tab/b2c)

- [AbiliTeci identiteeti](enrichment-liveramp.md) pakub LiveRamp AbiliTec
- [Brändid](enrichment-microsoft.md), mida pakub Microsoft
- [Demograafiline teave](enrichment-experian.md), mida pakub Experian
- [Microsofti pakutavad täiustatud](enrichment-enhanced-addresses.md) aadressid
- [Omandiõigused](enrichment-microsoft.md), mida pakub Microsoft
- [Mapsi pakutavad](enrichment-azure-maps.md) asukohaandmed Microsoft Azure
- [Asukohaandmeid](enrichment-here.md) esitab HERE Technologies
- [SFTP kohandatud andmed](enrichment-SFTP-custom-import.md) turvalise failiedastusprotokolli (SFTP) kaudu

# <a name="business-accounts-b-to-b"></a>[Ettevõtte kontod (B-st B-ni)](#tab/b2b)

- [Microsofti esitatud konto kaasamisandmed](enrichment-office.md)
- [Ettevõtte andmed](enrichment-dnb.md), mille on esitanud Dun ja Bradstreet
- [Ettevõtte andmeid](enrichment-leadspace.md) esitab Leadspace
- [Microsofti pakutavad täiustatud](enrichment-enhanced-addresses.md) aadressid
- [Microsofti pakutavad täiustatud ettevõtteandmed](enrichment-enhanced-company-data.md)
- [Mapsi pakutavad](enrichment-azure-maps.md) asukohaandmed Microsoft Azure
- [Asukohaandmeid](enrichment-here.md) esitab HERE Technologies
- [SFTP kohandatud andmed](enrichment-SFTP-custom-import.md) turvalise failiedastusprotokolli (SFTP) kaudu

---

## <a name="manage-existing-enrichments"></a>Olemasolevate rikastamiste haldamine

Avage **Andmed** > **Rikastamine**. **Vahekaardil Minu rikastamised** saate vaadata konfigureeritud rikastamisi, nende olekut, rikastatud klientide arvu ja viimast korda, kui andmeid värskendati. Rikastamiste loendit saate sortida mis tahes veeru järgi või kasutada otsingukasti, et leida rikastus, mida soovite hallata.

Valige rikastus, et vaadata saadaolevaid toiminguid.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Rikastamiste haldamise suvandid rikastamiste loendis.":::

- Rikastamise üksikasjade **Vaade** koos rikastatud kliendiprofiilide arvuga.
- Rikastamise konfiguratsiooni **Redigeerimine**.
- [**Käivitage**](#run-or-refresh-enrichments) rikastamine, et värskendada kliendiprofiile uusimate andmetega. Käivitage mitu rikastamist korraga, valides need loendist.
- **Rikastamise aktiveerimine** või **inaktiveerimine**. Passiivseid rikastamisi ei värskendata ajastatud värskendamise [ajal](schedule-refresh.md).
- **Kustuta** rikastamine.

Rikastamisest saate luua [ka segmente](segments.md) või [mõõtühikuid](measures.md).

## <a name="run-or-refresh-enrichments"></a>Joosta või värskendada rikastamist

Pärast käivitamist saab rikastamisi värskendada automaatse ajakava alusel või soovi korral käsitsi värskendada.

1. Ühe või mitme rikastamise käsitsi värskendamiseks valige need ja valige **Käivita**. Automaatse värskendamise ajastamiseks [minge jaotisse](schedule-refresh.md) Haldussüsteemi **·** > **ajakava** > **.** Töötlemisaeg sõltub teie kliendiandmete mahust.

1. [Soovi korral vaadake rikastamisprotsessi](#see-the-progress-of-the-enrichment-process) edenemist.

1. Kui rikastamisprotsess on lõpule jõudnud, minge jaotisse **Minu rikastamised**, et vaadata üle äsja rikastatud kliendiprofiilide andmed, viimase värskenduse aeg ja rikastatud profiilide arv.

1. Valige rikastamise tulemuste [nägemiseks](#view-enrichment-results) rikastamine.

### <a name="see-the-progress-of-the-enrichment-process"></a>Rikastamisprotsessi edenemise kuvamine

Siit leiate üksikasjalikku teavet rikastamise töötlemise kohta, sh selle oleku ja võimalike probleemide kohta värskendamise ajal või pärast värskendamise lõppu. Aru saada, millised protsessid on seotud rikastamise värskendamisega ja kui kaua kulus protsesside käivitamiseks. Rikastamise olekut toetatakse Experian, Leadspace-i, HERE-tehnoloogiate, SFTP Impordi ja Azure Mapsi puhul.

1. Avage **Andmed** > **Rikastamine**.
1. **Valige vahekaardil Minu rikastused** külgpaani avamiseks rikastumise olek.
1. Paanil **Edenemise üksikasjad** laiendage jaotist **Rikastused**.
1. Valige rikastamise jaotises, kus soovite edenemist näha, suvand **Kuva üksikasjad**.
1. Klõpsake paanil **Toimingu üksikasjad** käsku **Kuva üksikasjad**, et näha protsesse, mis on seotud rikastamise ja nende oleku värskendamisega.

[!INCLUDE [progress-details-pane](includes/progress-details-pane.md)]

## <a name="view-enrichment-results"></a>Rikastumistulemuste vaatamine

Pärast lõpetatud rikastamistsüklit vaadake rikastamise tulemused üle.

1. Avage **Andmed** > **Rikastamine**.
1. **Valige vahekaardil Minu rikastused** rikastumine, mida soovite vaadata.

Kõik rikastamised näitavad põhiteavet, nagu rikastatud profiilide arv ja rikastatud profiilide arv aja jooksul. **Paanil Rikastatud klientide eelvaates** kuvatakse loodud rikastusolemi näidis. Üksikasjaliku vaate kuvamiseks valige **Kuva rohkem** ja valige **vahekaart Andmed**.

:::image type="content" source="media/enrichments-results.png" alt-text="Rikastamise tulemuste leht.":::

Võimaluse korral **annab väljaga** rikastatud klientide arv iga rikastatud välja katvuse süvitsimineku.

Mõned rikastamised näitavad ka rikastamise tüübile omast teavet. Lisateabe saamiseks vaadake seotud dokumentatsiooni.

[!INCLUDE [footer-include](includes/footer-banner.md)]
