---
title: Kliendiprofiilide rikastamine Microsoft Office 365
description: Kasutage varalisi Microsoft Office andmeid, et rikastada oma kliendiprofiile kaasamisandmetega.
ms.date: 12/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahl
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: a30e09b5ed491c8d36019b5f0d35e0a2f7a0199c
ms.sourcegitcommit: 48d799535fad84e8b63c80aef48b5c5e87628f58
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 12/03/2021
ms.locfileid: "7889773"
---
# <a name="enrich-customer-profiles-with-engagement-data-preview"></a>Kliendiprofiilide rikastamine kaasamisandmetega (eelvaade)

Kasutage Microsoft Office 365 andmeid, et rikastada oma kliendikonto profiile rakenduste kaudu seotud töövõttude Office 365 kohta. Töövõtuandmed koosnevad e-posti ja koosolekutegevusest, mis koondatakse konto tasandile. Näiteks ettevõttekontolt saadetud e-kirjade arv või kontoga kohtumiste arv. Üksikute kasutajate kohta andmeid ei tehta kättesaadavaks. 

See rikastamine on saadaval järgmistes piirkondades: Ühendkuningriik, Euroopa, Põhja-Ameerika.

## <a name="prerequisites"></a>eeltingimused

Rikastamise konfigureerimiseks peavad olema täidetud järgmised eeltingimused.

- Teil on aktiivne Office 365 pilvelitsents.
- Teil on [ettevõtte kontodel põhinevad ühtsed kliendiprofiilid.](customer-profiles.md)[...](work-with-business-accounts.md)
- Teie Customer Insightsi keskkonnaga peab olema [Microsoft Dataverse seotud organisatsioon](create-environment.md#step-3-connect-to-microsoft-dataverse).
- Teil on [administraatori](permissions.md#administrator) õigused.
- Teil on või saate Office 365 rentnikuadministraatorilt nõusoleku kasutada Office 365 andmeid organisatsiooni **statistika pakkumiseks Dynamics** 365 rakendustes.

## <a name="configure-the-enrichment"></a>Rikastamise konfigureerimine

1. Avage sihtrühmaülevaadetes jaotis **Andmed** > **Rikastamine**.

1. Avage **vahekaart Avasta** ja **valige** **paanil Konto kaasamine suvand Rikasta minu** andmeid.

   :::image type="content" source="media/enrichment-office-tile.png" alt-text="Konto kaasamise paan.":::
   
1. Valige **·** **juhises Ülevaade suvand Edasi** ja sisestage oma asutuse meiliaadressid, mille jaoks Office'i andmed koondatakse. Asjakohase suhtluse jaoks töödeldakse ainult loetletud e-posti aadresside andmeid. Hea tava on kasutada meiligruppe, näiteks *USA* müügimeeskonda, mida on rakenduses lihtne Office 365 hallata. Rühmade e-posti aadresside arv lahendatakse ja kuvatakse. E-posti aadresside koguarv peab olema vähemalt 2 ja ei tohi ületada 2500.

   :::image type="content" source="media/enrichment-office-email-addresses.png" alt-text="Konto kaasamise e-posti aadressid.":::

1. Vaadake nõusolekuavaldus üle, märkige **ruut Nõustun ja valige Edasi** **·**.

1. Valige kliendi andmekogum ja valige **Edasi**.

1. Vastendage välja kontakt meiliaadress ja valige **Edasi**.

1. Vaadake üle rikastamiskonfiguratsioon, andke rikastamisele nimi ja valige **rikastamise** salvestamiseks Salvesta rikastamine.

## <a name="office-365-tenant-administrator-consent"></a>Office 365 rentnikuadministraatori nõusolek

Office 365 Rikastamise aktiveerimiseks on vaja rentnikuadministraatori nõusolekut. Rikastumise salvestamisel saadetakse Office 365 rentnikuadministraatoritele meilisõnum, milles palutakse neil üle vaadata ja nõustuda sellega, et Lubada Dynamics 365 rakendustel kasutada teie ettevõtte Office 365 andmeid organisatsiooni statistika **pakkumiseks**. Office 365 Rentnikuadministraator saab nõusoleku anda ka otse oma Office 365 halduskonsoolis, valides **organisatsiooni ülevaated**.

## <a name="running-the-enrichment-for-the-first-time"></a>Rikastamise esmakordne käitamine

Kui rikastamist alustatakse esimest korda pärast seda, kui Office 365 rentniku administraator on andnud nõusoleku, algavad andmete Office 365 allalaadimine. See protsess võtab aega. Esimene rikastamisjooks peaks toimuma kuuetunnise viivitusega. Päevade arvu, mida andmed katavad, näete konto kaasamise ülevaate lehel pärast rikastamise lõppu. Suure andmemahuga käivitage rikastamine mõne päeva pärast uuesti. See tagab, et andmed on täielikud kogu aja jooksul, mis on üks aasta.

Protsessi alustamiseks valige **lehel** Konto kaasamise konfiguratsioon Käivita. Lisaks saate lasta süsteemil rikastamist plaanitud värskendamise osana automaatselt [käivitada](system.md#schedule-tab). Vaikimisi kestab rikastamine üks kord nädalas.

Olenevalt Teie Office'i andmete suurusest võib rikastamise lõpuleviimiseks kuluda mitu tundi.

Rikastamise käivitamisel töötleb Microsoft Office 365 nõuetele vastavuse piiril täitvaid andmeid, et luua koondatud ülevaateid, mis seejärel lisatakse teie Customer Insightsi keskkonda. Customer Insightsi kasutajatele ei muutu kättesaadavaks üksikul tasemel (nt mis tahes meili- või kalendrikutsete kogum). 

[!INCLUDE [progress-details-pane](../includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Rikastamise tulemused

Pärast rikastamisprotsessi käivitamist minge **rikastamistulemuste** ülevaatamiseks minu rikastamise juurde. Leiad rikastatud klientide koguarvu ja ülevaate rikastamise tulemustest. See hõlmab töödeldud e-kirjade ja koosolekute arvu, päevade arvu, mille jooksul andmed on koondatud, ja palju muud.

Samuti leiate diagrammi rikastatud klientide arvuga aja jooksul ja rikastamisandmete eelvaate.  

:::image type="content" source="media/enrichment-office-results-overview.png" alt-text="Tulemuste eelvaade pärast rikastamise protsessi käitamist.":::

Kõik andmed koondatakse kuni konto tasemeni. Süsteem arvutab kaasamisskoori, mis on vahemikus 0 kuni 100, iga konto kohta. Kaasamise skoor annab koondnäitaja konto kaasamise kohta e-kirjades ja kohtumistes võrreldes teie teiste kontodega. Järgmine loend sisaldab koondandmeid, mida konto kaasamise rikastamine pakub.



| Andmed                                                                              | Veeru nimi                              |
| :-------------------------------------------------------------------------------- |:---------------------------------------- |
| Kaasamise skoor                                                                  |  EngagementScore                         |
| Kontole saadetud meilisõnumite arv                                                       |  NoOfEmails_ToAccount                    |
| Kontolt saadetud e-kirjade arv                                                     |  NoOfEmails_FromAccount                  | 
| Kontoga algatatud koosolekute arv                                           |  NoOfMeetings_FromAccount                | 
| Teie organisatsiooni algatatud koosolekute arv                                 |  NoOfMeetings_ToAccount                  | 
| Teie asutuse liikmete arv kontoga koosolekutel                  |  NoOfContactsInvolved_Meetings           | 
| Teie asutuse inimeste arv kontoga meilivestlustes       |  NoOfContactsInvolved_Emails             | 
| Kontolt teie organisatsiooniga kohtumistel inimeste arv                  |  NoOfAccountContactsInvolved_Meetings    | 
| Kontolt teie asutusega peetud meilivestlustes inimeste arv       |  NoOfAccountContactsInvolved_Emails      | 
| Kaasamise alguskuupäev (andmete esimene e-post või koosolek)                        |  EngagementStartDate                     | 
| Päevad pärast viimast e-posti                                                             |  DaysSinceLastemail                      | 
| Päevad pärast viimast koosolekut                                                           |  DaysSinceLastMeeting                    | 
| Koosolekute keskmine kestus                                                      |  AverageDuration_Of_Meetings             | 
| Kontolt saadud meilisõnumite vastuste keskmine kestus                                    |  AverageDuration_Of_AccountEmailReplies  | 
| Koondamise alguskuupäev                                                            |  AgregationStartDate                    | 
| Koondamise tase (aasta, kuu või nädal)                                          |  KoondamineLevel                        | 


Vaadake rikastatud andmed üle, valides **jaotises Eelvaate suvandi Vaata** lähemalt. See avab *olemi* Office. Samuti leiate üksuse Rikastamine **jaotises** **·** > **Andmeolemid**. Samuti leiate Office_UserEntity *, mis* sisaldab rikastamise konfigureerimise ajal valitud meiliaadresside Active Directory ID-sid 

## <a name="see-enrichment-data-on-the-customer-card"></a>Kliendi kaardi rikastamise andmete vaatamine

Konto kaasamist saab vaadata ka üksikutel kliendikaartidel. Avage **Kliendid** ja valige kliendiprofiil. Kliendikaardilt leiate konto kaasamisskoori, e-kirjade koguarvu ja viimase aasta jooksul koondatud koosolekute koguarvu. Samuti leiate diagramme, mis näitavad meili- ja koosolekuajalugu.

:::image type="content" source="media/enrichment-office-customer-card.png" alt-text="Kliendi kaart rikastatud andmetega.":::

## <a name="create-segments-and-measures-based-on-the-enriched-data"></a>Rikastatud andmetel põhinevate segmentide ja mõõtude loomine

Rikastatud andmeid saab kasutada segmentide ja mõõtude loomiseks, nagu allpool kirjeldatud. Näiteks segment, mis sisaldab kõiki kliente, mille väärtus on üle 60 *päeva pärast viimast e-posti* ja päevi pärast viimast *koosolekut*. See segment sisaldab aegunud kontosid, mida saate uuesti aktiveerida. 

## <a name="next-steps"></a>Järgmised toimingud

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]


[!INCLUDE[footer-include](../includes/footer-banner.md)]
