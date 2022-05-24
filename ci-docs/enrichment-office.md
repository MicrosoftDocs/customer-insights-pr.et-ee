---
title: Kliendiprofiilide rikastamine andmetega Microsoft Office 365
description: Kasutage varalisi andmeid Microsoft Office, et rikastada oma kliendiprofiile töövõtuandmetega.
ms.date: 12/03/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahl
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 782042ff643bd0cc70ac53e5680bfd0c68944d84
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642715"
---
# <a name="enrich-customer-profiles-with-engagement-data-preview"></a>Kliendiprofiilide rikastamine kaasamisandmetega (eelvaade)

Kasutage andmeid alates Microsoft Office 365, et rikastada oma kliendikonto profiile rakenduste kaudu Office 365 seotud töövõttude kohta. Töövõtuandmed koosnevad e-posti ja koosolekutegevusest, mis liidetakse konto tasemel. Näiteks ärikontolt saadetud e-kirjade arv või kontoga seotud kohtumiste arv. Andmeid üksikute kasutajate kohta ei tehta kättesaadavaks. 

See rikastamine on saadaval järgmistes piirkondades: Ühendkuningriigis, Euroopas, Põhja-Ameerikas.

## <a name="prerequisites"></a>eeltingimused

Rikastamise konfigureerimiseks peavad olema täidetud järgmised eeltingimused.

- Teil on aktiivne Office 365 pilvelitsents.
- Teil on [ühtsed kliendiprofiilid](customer-profiles.md), mis põhinevad [ärikontodel](work-with-business-accounts.md).
- Teie Customer Insightsi keskkonnas peab olema [Microsoft Dataverse seostatud](create-environment.md#step-3-connect-to-microsoft-dataverse) organisatsioon.
- Teil on [administraatori](permissions.md#admin) õigused.
- Teil on või saate oma rentnikuadministraatorilt Office 365 nõusoleku kasutada Office 365 andmeid organisatsiooni kohta ülevaate **andmiseks** Dynamics 365 rakendustes.

## <a name="configure-the-enrichment"></a>Rikastamise konfigureerimine

1. Avage **Andmed** > **Rikastamine**.

1. **Avage vahekaart Avasta** ja valige paanil **Konto kaasamine** käsk **Rikasta minu andmeid**.

   :::image type="content" source="media/enrichment-office-tile.png" alt-text="Konto kaasamise paan.":::
   
1. Valige **etapis Ülevaade** edasi **ja** sisestage oma asutuse meiliaadressid, mille jaoks Office'i andmed koondatakse. Asjakohaseks suhtluseks töödeldakse ainult loetletud e-posti aadresside andmeid. Parim tava on kasutada e-posti rühmi, näiteks *USA müügimeeskonda*, mida on lihtne hallata Office 365 rakenduses. Rühmade e-posti aadresside arv lahendatakse ja kuvatakse. E-posti aadresside koguarv peab olema vähemalt 2 ja see ei tohi ületada 2500.

   :::image type="content" source="media/enrichment-office-email-addresses.png" alt-text="Konto kaasamise meiliaadressid.":::

1. Vaadake nõusoleku avaldus üle, märkige **ruut Nõustun** ja valige **Edasi**.

1. Valige kliendi andmestik ja valige **Edasi**.

1. Vastendage kontakti meiliaadressi väli ja valige **Edasi**.

1. Vaadake rikastamise konfiguratsioon üle, andke rikastamisele nimi ja valige Rikastamise salvestamiseks Salvesta **rikastamine**.

## <a name="office-365-tenant-administrator-consent"></a>Office 365 rentniku administraatori nõusolek

Rikastamise aktiveerimiseks Office 365 on vaja rentnikuadministraatori nõusolekut. Rikastamise salvestamisel saadetakse Office 365 rentnikuadministraatoritele meilisõnum, milles palutakse neil üle vaadata ja nõustuda sellega, et Dynamics 365 rakendused saavad kasutada teie ettevõtte Office 365 andmeid organisatsiooni **kohta ülevaate andmiseks**. Rentnikuadministraator Office 365 saab nõusoleku anda ka otse oma Office 365 halduskonsoolis, valides **organisatsiooni** jaoks ülevaated.

## <a name="running-the-enrichment-for-the-first-time"></a>Rikastamise käivitamine esimest korda

Kui rikastamist alustatakse esimest korda, algab pärast rentnikuadministraatori Office 365 nõusoleku andmist andmete allalaadimine algusest Office 365. See protsess võtab aega. Esimene rikastamine toimub kuuetunnise viivitusega. Päevade arvu, mida andmed hõlmavad, näete konto kaasamise ülevaate lehel pärast rikastamise lõppu. Suure andmemahuga käivitage rikastamine mõne päeva pärast uuesti. See tagab, et andmed on täielikud kogu aja jooksul, mis on üks aasta.

Protsessi alustamiseks valige **konto kaasamise konfiguratsioon lehel Käivita**. Lisaks saate lasta süsteemil plaanitud värskenduse osana [rikastamist automaatselt käivitada](system.md#schedule-tab). Vaikimisi toimub rikastamine üks kord nädalas.

Sõltuvalt Office'i andmete suurusest võib rikastamise lõpuleviimiseks kuluda mitu tundi.

Rikastamise käivitamisel töötleb Microsoft nõuetele vastavuse piiril olevaid andmeid Office 365, et luua koondülevaateid, mis lisatakse seejärel teie Customer Insightsi keskkonda. Customer Insightsi kasutajatele ei pääse andmeid individuaalsel tasandil (nt mis tahes meilisõnumi või kalendrikutse keha). 

[!INCLUDE [progress-details-pane](includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Rikastamise tulemused

Pärast rikastamisprotsessi käivitamist minge minu rikastamise **juurde**, et vaadata üle rikastamise tulemused. Leiad rikastatud klientide koguarvu ja ülevaate rikastamise tulemustest. See hõlmab töödeldud e-kirjade ja koosolekute arvu, päevade arvu, mille jooksul andmed on koondatud, ja palju muud.

Samuti leiate diagrammi rikastatud klientide arvuga aja jooksul ja rikastamisandmete eelvaate.  

:::image type="content" source="media/enrichment-office-results-overview.png" alt-text="Tulemuste eelvaade pärast rikastamise protsessi käitamist.":::

Kõik andmed koondatakse konto tasemele. Süsteem arvutab iga konto kohta töövõtu skoori, mis jääb vahemikku 0 kuni 100. Töövõtu skoor annab konto kaasamise koondmõõdu e-kirjades ja koosolekutel võrreldes teie teiste kontodega. Järgmine loend sisaldab koondandmeid, mida konto töövõtu rikastamine pakub.



| Andmed                                                                              | Veeru nimi                              |
| :-------------------------------------------------------------------------------- |:---------------------------------------- |
| Kaasamise skoor                                                                  |  EngagementScore                         |
| E-kirjade arv kontole                                                       |  NoOfEmails_ToAccount                    |
| Meilide arv kontolt                                                     |  NoOfEmails_FromAccount                  | 
| Konto alusel algatatud koosolekute arv                                           |  NoOfMeetings_FromAccount                | 
| Teie organisatsiooni algatatud koosolekute arv                                 |  NoOfMeetings_ToAccount                  | 
| Teie asutuse töötajate arv kontoga koosolekutel                  |  NoOfContactsInvolved_Meetings           | 
| Teie asutusest pärit inimeste arv meilivestlustes kontoga       |  NoOfContactsInvolved_Emails             | 
| Teie asutusega kohtumistel kontolt pärit inimeste arv                  |  NoOfAccountContactsInvolved_Meetings    | 
| Teie asutusega meilivestlustes kontolt pärit inimeste arv       |  NoOfAccountContactsInvolved_Emails      | 
| Kaasamise alguskuupäev (andmete esimene meilisõnum või koosolek)                        |  EngagementStartDate                     | 
| Päevad viimasest e-kirjast                                                             |  DaysSinceLastEmail                      | 
| Päevad pärast viimast koosolekut                                                           |  DaysSinceLastMeeting                    | 
| Koosolekute keskmine kestus                                                      |  AverageDuration_Of_Meetings             | 
| Kontolt saadud meilivastuste keskmine kestus                                    |  AverageDuration_Of_AccountEmailReplies  | 
| Liitmise alguskuupäev                                                            |  AggregationStartDate                    | 
| Liitmise tase (aasta, kuu või nädal)                                          |  LiitmineLevel                        | 


Vaadake rikastatud andmed üle, valides **jaotises Eelvaade suvandi Vaata lähemalt**. See avab *olemi Office*. Olemi **leiate ka jaotisest Rikastamine** **jaotisest DataEntities** > **·**. Samuti leiate *Office_UserEntity*, mis sisaldab rikastamise konfiguratsiooni käigus valitud meiliaadresside Active Directory ID-sid. 

## <a name="see-enrichment-data-on-the-customer-card"></a>Kliendi kaardi rikastamise andmete vaatamine

Konto kaasamist saab vaadata ka üksikutel kliendikaartidel. Avage **Kliendid** ja valige kliendiprofiil. Kliendikaardilt leiate konto kaasamisskoori, e-kirjade koguarvu ja viimase aasta jooksul koondatud koosolekute koguarvu. Samuti leiate diagramme, mis näitavad meili- ja koosolekuajalugu.

:::image type="content" source="media/enrichment-office-customer-card.png" alt-text="Kliendi kaart rikastatud andmetega.":::

## <a name="create-segments-and-measures-based-on-the-enriched-data"></a>Segmentide ja mõõtude loomine rikastatud andmete põhjal

Rikastatud andmeid saab kasutada segmentide ja meetmete loomiseks, nagu allpool kirjeldatud. Näiteks segment, mis sisaldab kõiki kliente, kelle väärtus on üle 60 *päeva pärast viimast meili* ja *päevi pärast viimast koosolekut*. See segment sisaldab aegunud kontosid, mida saate proovida uuesti aktiveerida. 

## <a name="next-steps"></a>Järgmised toimingud

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]