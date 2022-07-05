---
title: Kliendiprofiilide rikastamine (eelvaade) pärinevate Microsoft Office 365 andmetega
description: Kasutage varalisi andmeid Microsoft Office, et rikastada oma kliendiprofiile töövõtuandmetega.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahl
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 75762afb70814c8a81c1574ee7ea1553a2048737
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9055669"
---
# <a name="enrich-customer-profiles-with-data-from-microsoft-office-365-preview"></a>Kliendiprofiilide rikastamine (eelvaade) pärinevate Microsoft Office 365 andmetega

Kasutage andmeid alates Microsoft Office 365, et rikastada oma kliendikonto profiile rakenduste kaudu Office 365 seotud töövõttude kohta. Töövõtuandmed koosnevad e-posti ja koosolekutegevusest, mis liidetakse konto tasemel. Näiteks ärikontolt saadetud e-kirjade arv või kontoga seotud kohtumiste arv. Andmeid üksikute kasutajate kohta ei tehta kättesaadavaks.

## <a name="supported-countries-or-regions"></a>Toetatud riikides või regioonides

Praegu toetame järgmisi piirkondi: Ühendkuningriik, Euroopa, Põhja-Ameerika.

## <a name="prerequisites"></a>eeltingimused

- Aktiivne Office 365 pilvelitsents.
- [Ühtsed kliendiprofiilid](customer-profiles.md), mis põhinevad [ärikontodel](work-with-business-accounts.md).
- Teie [Microsoft Dataverse Customer Insightsi keskkonnas manustatud](create-environment.md#step-3-connect-to-microsoft-dataverse) organisatsioon.
- [Administraatori](permissions.md#admin) õigused.
- Rentnikuadministraatori Office 365 nõusolek kasutada Office 365 andmeid organisatsiooni **kohta ülevaate andmiseks** Dynamics 365 rakendustes.

## <a name="configure-the-enrichment"></a>Rikastamise konfigureerimine

1. Avage suvandid **Andmed** > **Rikastamine** ja valige vahekaart **Avasta**.

1. Valige **Konto kaasamise** paanil **suvand Rikasta minu andmeid**.

   :::image type="content" source="media/enrichment-office-tile.png" alt-text="Konto kaasamise paan.":::

1. Vaadake ülevaade üle ja seejärel valige **Edasi**.

1. Sisestage oma asutuse meiliaadressid, mille jaoks Office'i andmed koondatakse. Asjakohaseks suhtluseks töödeldakse ainult loetletud e-posti aadresside andmeid. Parim tava on kasutada e-posti rühmi, näiteks *USA müügimeeskonda*, mida saate rakenduses hallata Office 365 rakenduses. Rühmade e-posti aadresside arv lahendatakse ja kuvatakse. E-posti aadresside koguarv peab olema vähemalt 2 ja see ei tohi ületada 2500.

   :::image type="content" source="media/enrichment-office-email-addresses.png" alt-text="Konto kaasamise meiliaadressid.":::

1. Vaadake üle ja esitage oma nõusolek rentniku administraatori nõusolekuks [Office 365](#office-365-tenant-administrator-consent), valides **nõustun**.

1. Tehke valik **Edasi**.

1. **Valige kontaktiandmestik** ja valige profiil, mida soovite rikastada. Tehke valik **Edasi**.

1. Vastendage kontakti meiliaadressi väli ja valige **Edasi**.

1. **Sisestage rikastamise ja** olemi **Väljund nimi**.

1. Valige **Salvesta rikastamine** pärast valikute läbivaatamist.

1. Lehele Rikastamised naasmiseks valige **Sule** **.**

### <a name="office-365-tenant-administrator-consent"></a>Office 365 rentniku administraatori nõusolek

Rikastamise aktiveerimiseks Office 365 on vaja rentnikuadministraatori nõusolekut. Rikastamise salvestamisel saadetakse Office 365 rentnikuadministraatoritele meilisõnum, milles palutakse neil üle vaadata ja nõustuda sellega, et Dynamics 365 rakendused saavad kasutada teie ettevõtte Office 365 andmeid organisatsiooni **kohta ülevaate andmiseks**. Rentnikuadministraator Office 365 saab nõusoleku anda ka otse oma Office 365 halduskonsoolis, valides **organisatsiooni** jaoks ülevaated.

## <a name="running-the-enrichment-for-the-first-time"></a>Rikastamise käivitamine esimest korda

Kui rikastamist alustatakse esimest korda, algab pärast rentnikuadministraatori Office 365 nõusoleku andmist andmete allalaadimine algusest Office 365. See protsess võtab aega. Esimene rikastamine toimub kuuetunnise viivitusega. Päevade arvu, mida andmed hõlmavad, näete konto kaasamise ülevaate lehel pärast rikastamise lõppu. Suure andmemahuga käivitage rikastamine mõne päeva pärast uuesti. See tagab, et andmed on täielikud kogu aja jooksul, mis on üks aasta.

Sõltuvalt Office'i andmete suurusest võib rikastamise lõpuleviimiseks kuluda mitu tundi.

Rikastamise käivitamisel töötleb Microsoft nõuetele vastavuse piiril olevaid andmeid Office 365, et luua koondülevaateid, mis lisatakse seejärel teie Customer Insightsi keskkonda. Customer Insightsi kasutajatele ei pääse andmeid individuaalsel tasandil (nt mis tahes meilisõnumi või kalendrikutse keha).

Rikastamisprotsessi alustamiseks valige **Käivita**.

[!INCLUDE [progress-details-pane](includes/progress-details-pane.md)]

## <a name="view-enrichment-results"></a>Rikastamise tulemuste kuvamine

[!INCLUDE [enrichment-results](includes/enrichment-results.md)] See on *Office'i* olem. Office_UserEntity *sisaldab* Rikastamise konfiguratsiooni käigus valitud meiliaadresside Active Directory ID-sid.

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

## <a name="see-enrichment-data-on-the-customer-card"></a>Kliendi kaardi rikastamise andmete vaatamine

Konto kaasamist saab vaadata ka üksikutel kliendikaartidel. Avage **Kliendid** ja valige kliendiprofiil. Kliendikaardilt leiate konto kaasamisskoori, e-kirjade koguarvu ja viimase aasta jooksul koondatud koosolekute koguarvu. Samuti leiate diagramme, mis näitavad meili- ja koosolekuajalugu.

:::image type="content" source="media/enrichment-office-customer-card.png" alt-text="Kliendi kaart rikastatud andmetega.":::

## <a name="next-steps"></a>Järgmised toimingud

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]
Näiteks segment, mis sisaldab kõiki kliente, kelle väärtus on üle 60 *päeva pärast viimast meili* ja *päevi pärast viimast koosolekut*. See segment sisaldab aegunud kontosid, mida saate proovida uuesti aktiveerida.

[!INCLUDE [footer-include](includes/footer-banner.md)]
