---
title: Customer Insights -i tasulise litsentsi loomine ja konfigureerimine
description: Juhised selle litsentsitud tellimuse toomiseks Dynamics 365 Customer Insights -i ja konfigureerimiseks.
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: b5f76f4c468b88aaf7037dbd2ee3bed449fbeaa5f645d52278eee05b36b4e328
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034447"
---
# <a name="get-started-with-a-paid-subscription"></a>Makstud tellimusega alustamine

Selles artiklis kirjeldatakse, kuidas luua uus keskkond pärast seda, kui su organisatsioon on ostnud Dynamics 365 Customer Insights -itellimuse. Kui soovite osta Customer Insights -i, on meie kontaktisuvandid loetletud [Dynamics 365 Customer Insights veebisaidil](https://dynamics.microsoft.com/ai/customer-insights/). 

Kui soovite teenust ja funktsioone proovida, lugege teemat [Proovikeskkonna seadistamine](get-started-trial.md).

## <a name="create-an-environment-in-an-existing-organization"></a>Keskkonna loomine olemasolevasse organisatsiooni

Pärast Customer Insights -i tellimuse litsentsi ostmist saab Microsoft 365 rentniku globaaladministraator meili, mis kutsub neid keskkonda looma. Alustamiseks minge [https://home.ci.dynamics.com/start](https://home.ci.dynamics.com/start). 

Customer Insights pole kasutaja jaoks litsentsitud, seega ei näidata seda alas Litsentsid. Kui otsite litsentsi Microsoft 365 administreerimiskeskuses, minge **Oma toodete** veebisaidile. 

> [!NOTE]
> Organisatsioonid saavad iga Customer Insights litsentsi jaoks luua *kaks* keskkonda. Kui teie organisatsioon ostab rohkem kui ühe litsentsi, palun [pöörduge meie tugimeeskonna](https://go.microsoft.com/fwlink/?linkid=2079641) poole, et suurendada vabade keskkondade arvu. Võimsuse ja lisandmooduli võimsuse kohta lisateabe saamiseks laadige alla [Dynamics 365 litsentsimisjuhend](https://go.microsoft.com/fwlink/?LinkId=866544).

Uue keskkonna loomine.

1. Valige **Keskkonna loomine** dialoog, valige **Uus keskkond**.

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Uue ühenduse loomine rakenduses Customer Insights.":::

   Soovitame alustada töökeskkonna seadistamist nullist. Kui aga olete proovikeskkonna administraator või liige, võite [andmed kopeerida muust keskkonnast](manage-environments.md#copy-the-environment-configuration), valides **Kopeeri olemasolevast keskkonnast**. Näete teie ettevõtte kõigi saadaolevate keskkondade loendit, kust saate andmeid kopeerida.

1. Esitage järgmised andmed.
   - **Nimi**: selle keskkonna nimi. Olemasolevast keskkonnast kopeerides on see väli juba täidetud, kuid saate seda muuta.
   - **Piirkond**: piirkond, kus teenus juurutatakse ja majutatakse.
   - **Tüüp**: Valige, kas soovite luua töö- või liivakastikeskkonna. Liivakastikeskkonnad ei luba ajastatud andmeid värskendada ja on mõeldud eelinstallimiseks ja testimiseks.
   
1. Soovi korral saate valida ka suvandi **Täpsemad sätted**.

   - **Salvesta kõik andmed**: määrab, kuhu soovite Customer Insightsist loodud väljundandmed talletada. Teil on kaks võimalust: **Customer Insightsi salvestusruum** (Azure Data Lake, mida haldab Customer Insights meeskond) ja **Azure Data Lake Storage** (teie enda Azure Data Lake Storage). Vaikimisi on valitud Customer Insightsi salvestusruumi suvand.

     > [!NOTE]
     > Andmete salvestamisel teenusesse Azure Data Lake Storage nõustute, et andmed edastatakse ja talletatakse selle Azure'i salvestusruumi konto asjakohases geograafilises asukohas, mis võib erineda rakendusse Dynamics 365 Customer Insights talletatud andmete salvestuskohast. [Lisateavet leiate Microsofti usalduskeskusest.](https://www.microsoft.com/trust-center)
     >
     > Praegu salvestatakse edastatud olemid Power BI andmevoost alati Microsoft Dataverse-hallatavasse Data Lake'i. 
     > 
     > Toetame ainult Azure Data Lake Storage kontosid, mis on pärit samast Azure'i piirkonnast, mille olete keskkonna loomisel valinud. 
     > 
     > Toetame ainult Azure Data Lake Storage kontosid, mille nimeruum on hierarhiline.


   - Selle Azure Data Lake Storage suvandi puhul saate valida ressursipõhise ja kordustellimusel põhineva autentimise suvandi. Lisateavet leiate teemast [Sihtrühmaülevaadete ühendamine Azure Data Lake Storage Gen2 kontoga Azure'i teenusesubjekti kaudu](connect-service-principal.md). **Konteineri** nime ei saa muuta ja see on `customerinsights`.
   
   - Kui soovite kasutada [kasutuselt väljas mudeleid](predictions-overview.md#out-of-box-models), konfigureerida andmete ühiskasutust funktsiooniga Microsoft Dataversevõi võimaldada andmete asutusesisest sissetoomist, sisestage Microsoft Dataverse keskkonnas URL jaotises **Konfigureeri andmete ühiskasutus Microsoft Dataverse -iga ja lubage täiendavad võimalused**. Valige suvand **Enable data sharing** (Luba andmete ühiskasutus), et jagada Customer Insightsi väljundandmeid Microsoft Dataverse Managed Data Lake hallatava andmejärvega.

     > [!NOTE]
     > - Andmete jagamine rakendusega Microsoft Dataverse Managed Data Lake täna ei toetata, kui salvestate kõik andmed enda andmejärve Azure Data Lake Storage.
     > - [Prognoosimine puuduvate väärtuste puhul olemis](predictions.md) pole praegu toetatud, kui lubate andmete ühiskasutuse Microsoft Dataverse hallatava Data Lake'iga.

     :::image type="content" source="media/Datasharing-with-DataverseMDL.png" alt-text="Konfigureerimissuvandid andmete jagamise lubamiseks Microsoft Dataverse abil.":::

   Kui süsteemiprotsessid, nagu andmete sissetoomised on lõpule jõudnud, loob süsteem teie määratud salvestusruumikontole vastavad kaustad. Andmefailid ja model.json-failid luuakse ning lisatakse kaustadesse protsessi nime põhjal.

   Kui loote mitu Customer Insightsi keskkonda ja soovite salvestada väljundolemid nendest keskkondadest oma salvestuskontole, luuakse eraldi kaustad iga keskkonna jaoks, mille konteineris on ci_<environmentid>.

1. Keskkonna seadistamiseks valige **Loo**. 

## <a name="configure-an-environment"></a>Keskkonna konfigureerimine

Vaadake läbi järgmised artiklid, mis aitavad teil Customer Insights -i konfigureerimisega algust teha. 

- [Lisage veel kasutajaid ja määrake õiguseid](permissions.md)i.
- [Tooge sisse oma andmeallikaid](data-sources.md) ja käivitage need [andmete ühendamise protsessis](data-unification.md) , et [saada ühtseid kliendiprofiile](customer-profiles.md).
- [Rikastage ühendatud kliendiprofiile](enrichment-hub.md) või [käivitage ennetavad mudeleid](predictions-overview.md).
- Looge [segmente](segments.md) klientide rühmitamiseks ja [mõõdikuid](measures.md) KPI-de ülevaatamiseks.
- Seadistage [ühendused](connections.md) ja [eksport](export-destinations.md) andmete alamhulkade töötlemiseks muudes rakendustes.
