---
title: Looge Customer Insights keskkondi
description: Sammud litsentsitud kordustellimusega keskkondade loomiseks Dynamics 365 Customer Insights jaoks.
ms.date: 03/28/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: a538237322615f69f0a5cb43d394275bf79af00b
ms.sourcegitcommit: ae02ac950810242e2505d7d371b80210dc8a0777
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 03/29/2022
ms.locfileid: "8491908"
---
# <a name="create-an-environment-in-audience-insights"></a>Looge sihtrühma ülevaates keskkond

Selles artiklis kirjeldatakse, kuidas luua uus keskkond pärast seda, kui su organisatsioon on ostnud Dynamics 365 Customer Insights -itellimuse. 

Organisatsioonid saavad iga Customer Insights litsentsi jaoks luua *kaks* keskkonda. Kui teie organisatsioon ostab rohkem kui ühe litsentsi, siis [pöörduge meie tugimeeskonna poole](https://go.microsoft.com/fwlink/?linkid=2079641), et suurendada vabade keskkondade arvu. Võimsuse ja lisandmooduli võimsuse kohta lisateabe saamiseks laadige alla [Dynamics 365 litsentsimisjuhend](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!NOTE]
> Kui soovite teenust proovida, lugege teemat [Proovikeskkonna seadistamine](../trial-signup.md).

## <a name="create-a-new-environment"></a>Uue keskkonna loomine

Pärast Customer Insightsi tellimuslitsentsi ostmist saab rentniku üldadministraator Microsoft 365 meilisõnumi, mis kutsub neid keskkonda looma. Alustamiseks minge [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start). 

Juhendav kogemus aitab teil koguda uue keskkonna jaoks vajalikku teavet. Keskkondade loomiseks ja haldamiseks on vaja [administraatori õigusi](permissions.md) sihtrühma ülevaadetes.

1. Avage sihtrühma ülevaadetes keskkonnavalija ja valige **+ Uus**.
  
   :::image type="content" source="../engagement-insights/media/environment-picker.png" alt-text="Valige keskkonnavalija.":::

1. Järgige järgmistes jaotistes kirjeldatud juhendatud kogemust.

### <a name="step-1-provide-environment-information"></a>Esimene etapp: Keskkonnateabe esitamine

Valige **Põhiteabe** etapis, kas soovite luua soovitud keskkonda kopeerimiskeskkonnast või [kopeerida andmed muust keskkonnast](manage-environments.md#copy-the-environment-configuration).

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Uue ühenduse loomine rakenduses Customer Insights.":::

Esitage järgmised andmed.
   - **Nimi**: selle keskkonna nimi. Olemasolevast keskkonnast kopeerides on see väli juba täidetud, kuid saate seda muuta.
   - **Valige oma ettevõte**: Valige uue keskkonna jaoks peamine sihtrühm. Võite töötada eraklientidega (B2C) või [ ettevõtetega](work-with-business-accounts.md) (B2B).
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
> - Azure Data Lake Storage kontod, mis on Gen2 ja mille hierarhiline nimeruum *on* lubatud. Azure Data Lake Gen1 salvestuskontosid ei toetata.

Selle Azure Data Lake Storage suvandi puhul saate valida ressursipõhise ja kordustellimusel põhineva autentimise suvandi. Lisateavet leiate teemast [Azure Data Lake Storage kontoga ühenduse loomine Azure'i teenuse subjekti](connect-service-principal.md) abil. **Konteineri** nimi on `customerinsights` ja seda ei saa muuta.

Kui süsteemiprotsessid, nagu andmete allaneelamine, on lõpule jõudnud, loob süsteem teie määratud salvestusruumikontole vastavad kaustad. Andmefailid ja *model.json* failid luuakse ning lisatakse kaustadesse protsessi nime põhjal.

Kui loote Customer Insights'i mitu keskkonda ja salvestate nendest keskkondadest väljundolemid oma salvestuskontole, loob Customer Insights iga keskkonna jaoks eraldi kaustad, mille konteineris on `ci_environmentID`.

### <a name="step-3-connect-to-microsoft-dataverse"></a>Kolmas etapp: Microsoft Dataverse-ga ühenduse loomine
   
**Microsoft Dataverse** etapp lubab teil Customer Insights'i oma Dataverse keskkonnaga ühendada.

Pakkuge oma Microsoft Dataverse keskkonda, et jagada andmeid (profiile ja ülevaateid) ärirakendustega, mis põhinevad rakendusel Dataverse(nt Dynamics 365 Marketing või mudelipõhised rakendused rakenduses )Power Apps. Jätke see väli tühjaks, kui teil pole oma Dataverse keskkonda ja me eraldame selle teile.

Dataverse Keskkonnaga ühenduse loomine võimaldab teil andmevoogude ja lüüside abil [alla neelata Power Platform andmeid ka asutusesisene andmeallikatest](data-sources.md#add-data-from-on-premises-data-sources). Keskkonnaga [ühenduse loomisega saate kasutada](predictions-overview.md?tabs=b2c#out-of-box-models) ka prognoos mudeleid Dataverse.

> [!IMPORTANT]
> 1. Customer Insights ja Dataverse andmete jagamise lubamiseks peab see olema samas piirkonnas.
> 1. Teil peab olema keskkonnas üldadministraatori Dataverse roll. Kontrollige, kas see [Dataverse keskkond on seotud](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) teatud turberühmadega, ja veenduge, et teid lisatakse nendesse turberühmadesse.
> 1. Ükski olemasolev Customer Insightsi keskkond pole selle Dataverse keskkonnaga juba seotud. Siit saate teada, [kuidas olemasolevat ühendust keskkonnaga Dataverse](manage-environments.md#remove-an-existing-connection-to-a-dataverse-environment) eemaldada.

:::image type="content" source="media/dataverse-provisioning.png" alt-text="andmete jagamine Microsoft Dataverse automaatselt lubatud uute netoeksemplari puhul.":::

Lisateavet andmete ühiskasutuse lubamise kohta leiate teemast Ühenduse loomine rakendusega Microsoft Dataverse Azure Data Lake Storage[.Microsoft Dataverse](manage-environments.md#connect-to-microsoft-dataverse)

Customer Insights ei toeta järgmisi andmete jagamise stsenaariume:
- Kui lubate andmete ühiskasutuse Dataverse-ga, ei saa te [olemis luua ennustatud ega puuduvad väärtused](predictions.md).

### <a name="step-4-finalize-the-settings"></a>Neljas etapp: Viige sätted lõpule

Vaadake **Arvustuse** sammus kõiki määratud sätteid. Kui kõik paistab valmis, valige keskkonna häälestamiseks käsk **Loo**. 

Enamikku sätetest saate hiljem ka muuta. Lisateavet leiate teemast [Keskkondade haldamine](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Uue keskkonnaga töötamine

Kliendiülevaadete konfigureerimise alustamiseks vaadake üle järgmised artiklid. 

- [Lisage veel kasutajaid ja määrake õiguseid](permissions.md)i.
- [Tooge sisse oma andmeallikaid](data-sources.md) ja käivitage need [andmete ühendamise protsessis](data-unification.md) , et [saada ühtseid kliendiprofiile](customer-profiles.md).
- [Rikastage ühendatud kliendiprofiile](enrichment-hub.md) või [käivitage ennetavad mudeleid](predictions-overview.md).
- [Looge segmente](segments.md) klientide rühmitamiseks ja [mõõdikuid](measures.md) KPI-de arvustamiseks.
- [Seadistage ühendused](connections.md) ja [eksporte](export-destinations.md) andmete alamhulkade töötlemiseks muudes rakendustes.
