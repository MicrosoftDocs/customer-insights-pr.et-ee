---
title: Looge Customer Insights keskkondi
description: Sammud litsentsitud kordustellimusega keskkondade loomiseks Dynamics 365 Customer Insights jaoks.
ms.date: 10/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 95afd1fedb98a451e4978ee66be2ea98ad7a4a76
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645680"
---
# <a name="create-an-environment-in-audience-insights"></a>Looge sihtrühma ülevaates keskkond

Selles artiklis kirjeldatakse, kuidas luua uus keskkond pärast seda, kui su organisatsioon on ostnud Dynamics 365 Customer Insights -itellimuse. 

Organisatsioonid saavad iga Customer Insights litsentsi jaoks luua *kaks* keskkonda. Kui teie organisatsioon ostab rohkem kui ühe litsentsi, siis [pöörduge meie tugimeeskonna poole](https://go.microsoft.com/fwlink/?linkid=2079641), et suurendada vabade keskkondade arvu. Võimsuse ja lisandmooduli võimsuse kohta lisateabe saamiseks laadige alla [Dynamics 365 litsentsimisjuhend](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!NOTE]
> Kui soovite teenust proovida, lugege teemat [Proovikeskkonna seadistamine](../trial-signup.md).

## <a name="create-a-new-environment"></a>Uue keskkonna loomine

Pärast Customer Insights -i tellimuse litsentsi ostmist saab Microsoft 365 rentniku globaaladministraator meili, mis kutsub neid keskkonda looma. Alustamiseks minge [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start). 

Juhendav kogemus aitab teil koguda uue keskkonna jaoks vajalikku teavet. Keskkondade loomiseks ja haldamiseks on vaja [administraatori õigusi](permissions.md) sihtrühma ülevaadetes.

1. Avage sihtrühma ülevaadetes keskkonnavalija ja valige **+ Uus**.
  
   :::image type="content" source="../engagement-insights/media/environment-picker.png" alt-text="Valige keskkonnavalija.":::

1. Järgige järgmistes jaotistes kirjeldatud juhendatud kogemust.

### <a name="step-1-provide-environment-information"></a>Esimene etapp: Keskkonnateabe esitamine

Valige **Põhiteabe** etapis, kas soovite luua soovitud keskkonda kopeerimiskeskkonnast või [kopeerida andmed muust keskkonnast](manage-environments.md#copy-the-environment-configuration).

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Uue ühenduse loomine rakenduses Customer Insights.":::

Esitage järgmised andmed.
   - **Nimi**: selle keskkonna nimi. Olemasolevast keskkonnast kopeerides on see väli juba täidetud, kuid saate seda muuta.
   - **Valige oma ettevõte**: Valige uue keskkonna jaoks peamine sihtrühm. Saate töötada klientidega (B2C) või [ärikontodega](work-with-business-accounts.md) (B2B).
   - **Tüüp**: Valige, kas soovite luua töö- või liivakastikeskkonna. Liivakastikeskkonnad ei luba ajastatud andmeid värskendada ja on mõeldud eelinstallimiseks ja testimiseks. Liivakastikeskkonnad kasutavad põhilist sihtrühma, kes on praegu valitud töökeskkonnas.
   - **Piirkond**: piirkond, kus teenus juurutatakse ja majutatakse.

### <a name="step-2-configure-data-storage"></a>Teine etapp: Andmemälu konfigureerimine

Valige **Andmemälu** sammus, kus saab sihtrühma ülevaadetest salvestatud andmeid talletada.

Teil on kaks võimalust: **Customer Insightsi salvestusruum** (Azure Data Lake, mida haldab Customer Insights meeskond) ja **Azure Data Lake Storage** (teie enda Azure Data Lake Storage). Vaikimisi on valitud Customer Insightsi salvestusruumi suvand.

:::image type="content" source="media/data-storage-environment.png" alt-text="Valige, Azure Data Lake Storage kus soovite oma sihtrühma ülevaadete andmeid talletada.":::

Salvestades andmed Azure Data Lake Storage-sse, nõustute, et andmed kantakse üle ja salvestatakse selle Azure'i salvestuskonto jaoks sobivasse geograafilisse asukohta. See asukoht võib erineda andmete talletamiskohtadest rakenduses Dynamics 365 Customer Insights. Lisateavet leiate [Microsofti usalduskeskusest](https://www.microsoft.com/trust-center).

> [!NOTE]
> Customer Insights toetab praegu järgmist:
> - Allaneelatud olemid Power BI andmevoogudest, mis on talletatud Microsoft Dataverse hallatavasse Data Lake'i.  
> - Azure Data Lake Storage kontod samast Azure'i piirkonnast, mille valisite keskkonna loomisel.
> - Azure Data Lake Storage kontod, millel on *hierarhiline nimeruum* lubatud.

Selle Azure Data Lake Storage suvandi puhul saate valida ressursipõhise ja kordustellimusel põhineva autentimise suvandi. Lisateavet leiate teemast [Sihtrühmaülevaadete ühendamine Azure Data Lake Storage Gen2 kontoga Azure'i teenusesubjekti kaudu](connect-service-principal.md). **Konteineri** nimi on `customerinsights` ja seda ei saa muuta.

Kui süsteemiprotsessid, nagu andmete allaneelamine, on lõpule jõudnud, loob süsteem teie määratud salvestusruumikontole vastavad kaustad. Andmefailid ja *model.json* failid luuakse ning lisatakse kaustadesse protsessi nime põhjal.

Kui loote Customer Insights'i mitu keskkonda ja salvestate nendest keskkondadest väljundolemid oma salvestuskontole, loob Customer Insights iga keskkonna jaoks eraldi kaustad, mille konteineris on `ci_environmentID`.

### <a name="step-3-connect-to-microsoft-dataverse"></a>Kolmas etapp: Microsoft Dataverse-ga ühenduse loomine
   
**Microsoft Dataverse** etapp lubab teil Customer Insights'i oma Dataverse keskkonnaga ühendada.

Kui soovite kasutada [karbist välja ennustamise mudeleid](predictions-overview.md#out-of-box-models), siis konfigureerige andmete ühiskasutus rakendusega Dataverse. Võite ka lubada asutusesisestest allikatest pärinevad andmed, pakkudes teie Microsoft Dataverse organisatsiooni hallatava keskkonna URL-i. Valige suvand **Enable data sharing** (Luba andmete ühiskasutus), et jagada Customer Insightsi väljundandmeid Dataverse Managed Data Lake hallatava andmejärvega.

:::image type="content" source="media/dataverse-data-sharing.png" alt-text="Konfigureerimissuvandid andmete jagamise lubamiseks Microsoft Dataverse abil.":::

> [!NOTE]
> Customer Insights ei toeta järgmisi andmete jagamise stsenaariume:
> - Kui salvestate kõik andmed enda Azure Data Lake Storage abil, siis ei saa te lubada andmete jagamist Microsoft Dataverse hallatava Data Lake-iga.
> - Kui lubate andmete ühiskasutuse Microsoft Dataverse hallatava Data Lake-iga, ei saa te [olemis luua ennustatud ega puuduvad väärtused](predictions.md).

### <a name="step-4-finalize-the-settings"></a>Neljas etapp: Viige sätted lõpule

Vaadake **Arvustuse** sammus kõiki määratud sätteid. Kui kõik paistab valmis, valige keskkonna häälestamiseks käsk **Loo**. 

Enamikku sätetest saate hiljem ka muuta. Lisateavet leiate teemast [Keskkondade haldamine](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Uue keskkonnaga töötamine

Vaadake läbi järgmised artiklid, mis aitavad teil Customer Insights -i konfigureerimisega algust teha. 

- [Lisage veel kasutajaid ja määrake õiguseid](permissions.md)i.
- [Tooge sisse oma andmeallikaid](data-sources.md) ja käivitage need [andmete ühendamise protsessis](data-unification.md) , et [saada ühtseid kliendiprofiile](customer-profiles.md).
- [Rikastage ühendatud kliendiprofiile](enrichment-hub.md) või [käivitage ennetavad mudeleid](predictions-overview.md).
- [Looge segmente](segments.md) klientide rühmitamiseks ja [mõõdikuid](measures.md) KPI-de ülevaatamiseks.
- [Seadistage ühendused](connections.md) ja [eksporte](export-destinations.md) andmete alamhulkade töötlemiseks muudes rakendustes.
