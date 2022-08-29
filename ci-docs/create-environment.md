---
title: Uue keskkonna loomine
description: Sammud keskkondade loomiseks rakenduses Dynamics 365 Customer Insights.
ms.date: 08/15/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 0a45e2fd2bdb7b85883a536f8b42ee650e54db7e
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304238"
---
# <a name="create-a-new-environment"></a>Uue keskkonna loomine

Pärast [kordustellimuslitsentsi Dynamics 365 Customer Insights](paid-license.md) ostmist saab rentniku üldadministraator Microsoft 365 meili, mis kutsub teda keskkonda looma. Alustamiseks minge [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start). Selle stsenaariumi korral alustage 1. sammust [: esitage põhiteave](#step-1-provide-basic-information).

Pärast esimese keskkonna loomist saab Microsoft 365 rentniku üldadministraator [lisada administraatoritena kasutajaid oma organisatsioonist](permissions.md). Need administraatorid saavad seejärel hallata kasutajaid ja keskkondi. Kui teie organisatsioon ostab Customer Insightsi jaoks rohkem kui ühe litsentsi, [võtke saadaolevate keskkondade arvu suurendamiseks ühendust meie tugitiimiga](https://go.microsoft.com/fwlink/?linkid=2079641). Võimsuse ja lisavõimsuse kohta lisateabe saamiseks vaadake üle [Dynamics 365-i litsentsimisjuhend](https://go.microsoft.com/fwlink/?LinkId=866544). Kui teil on võimalus luua täiendavaid keskkondi, minge jaotisse [Keskkonna loomise protsessi käivitamine](#start-the-environment-creation-process).

> [!TIP]
> Kui soovite teenust proovida, lugege teemat [Proovikeskkonna seadistamine](trial-signup.md).

## <a name="prerequisites"></a>eeltingimused

[Administraatori õigused](permissions.md) Customer Insightsis

## <a name="start-the-environment-creation-process"></a>Käivitage keskkonna loomise protsess

1. Avage keskkonnavalija ja valige **+ Uus**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Valige keskkonnavalija.":::

1. Järgige järgmistes jaotistes kirjeldatud juhendatud kogemusi, et anda kogu vajalik teave uue keskkonna jaoks.

## <a name="step-1-provide-basic-information"></a>1. toiming: andke põhiteavet

1. Valige, kas soovite luua keskkonna nullist või kopeerida andmeid teisest keskkonnast. [Andmete kopeerimine teisest keskkonnast](#copy-the-environment-configuration) nõuab lisatoiminguid.

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Uue ühenduse loomine rakenduses Customer Insights.":::

1. Esitage järgmised andmed.

   - **Nimi**: selle keskkonna nimi. Olemasolevast keskkonnast kopeerides on see väli juba täidetud, kuid saate seda muuta.
   - **Valige oma ettevõte**: uue keskkonna peamine vaatajaskond: üksiktarbijad (B-kuni-C) või [ettevõtte kontod](work-with-business-accounts.md) (B-B). Kui teie organisatsioon teeb äri peamiselt üksikisikutega (nt jaemüüja või kohvik), valige üksiktarbijad. Kui teie peamine vaatajaskond on teised ettevõtted, näiteks autotootja või paberiettevõte, valige ettevõtte kontod.
   - **Tüüp**: Keskkonna tüüp: tootmine või liivakast. Liivakastikeskkonnad ei luba ajastatud andmeid värskendada ja on mõeldud eelinstallimiseks ja testimiseks. Liivakastikeskkonnad kasutavad põhilist sihtrühma, kes on praegu valitud töökeskkonnas.
   - **Piirkond**: piirkond, kus teenust juurutatakse ja majutatakse. Oma [Azure Data Lake Storage konto](own-data-lake-storage.md) kasutamiseks või [olemasoleva Microsoft Dataverse organisatsiooniga](customer-insights-dataverse.md) ühenduse loomiseks peab Customer Insightsi keskkond asuma samas piirkonnas.

1. Tehke valik **Edasi**.

## <a name="step-2-configure-data-storage"></a>Teine etapp: Andmemälu konfigureerimine

1. Valige, kus Customer Insightsi andmeid talletada.

   - **Customer Insightsi salvestusruum**: andmesalvestusruumi hallatakse automaatselt. See on vaikevalik ja kui teie enda salvestusruumikontole andmete salvestamiseks pole konkreetseid nõudeid, soovitame seda suvandit kasutada.
   - **Azure Data Lake Storage**: teie enda Azure Data Lake Storage konto andmete salvestamiseks, et teil oleks täielik kontroll andmete salvestamise üle. Järgige teemas [Oma Azure Data Lake Storage konto](own-data-lake-storage.md) kasutamine toodud juhiseid.

   :::image type="content" source="media/data-storage-environment.png" alt-text="Valige oma andmete salvestamiseks eelistatud suvand.":::

1. Tehke valik **Edasi**.

## <a name="step-3-connect-to-microsoft-dataverse"></a>Kolmas etapp: Microsoft Dataverse-ga ühenduse loomine

Kui teil on Dataverse keskkond, ühendage Customer Insights. Andke andmeid Dataverse ühiskasutusse, et kasutada neid ärirakendustega, mis põhinevad rakendusel Dataverse Dynamics 365 Marketing või mudelipõhised rakendused rakenduses Power Apps.

1. Järgige juhiseid teemas [Customer Insightsi andmetega töötamine.Microsoft Dataverse](customer-insights-dataverse.md)

   :::image type="content" source="media/dataverse-provisioning.png" alt-text="andmete jagamine Microsoft Dataverse automaatselt lubatud uutes netikeskkondades.":::

1. Tehke valik **Edasi**.

## <a name="step-4-finalize-the-settings"></a>Neljas etapp: Viige sätted lõpule

Vaadake määratud sätted üle. Kui kõik paistab valmis, valige keskkonna häälestamiseks käsk **Loo**.

Mõne sätte hilisemaks muutmiseks vaadake teemat [Keskkondade](manage-environments.md) haldamine.

## <a name="work-with-your-new-environment"></a>Uue keskkonnaga töötamine

Kliendiülevaadete konfigureerimise alustamiseks vaadake üle järgmised artiklid.

- [Lisage veel kasutajaid ja määrake õiguseid](permissions.md)i.
- [Tooge sisse oma andmeallikaid](data-sources.md) ja käivitage need [andmete ühendamise protsessis](data-unification.md) , et [saada ühtseid kliendiprofiile](customer-profiles.md).
- [Rikastage ühendatud kliendiprofiile](enrichment-hub.md) või [käivitage ennetavad mudeleid](predictions-overview.md).
- [Looge segmente](segments.md) klientide rühmitamiseks ja [mõõdikuid](measures.md) KPI-de arvustamiseks.
- [Seadistage ühendused](connections.md) ja [eksporte](export-destinations.md) andmete alamhulkade töötlemiseks muudes rakendustes.

## <a name="copy-the-environment-configuration"></a>Kopeerige keskkonna konfiguratsioon

Kui valisite administraatorina konfiguratsiooni kopeerimise olemasolevast keskkonnast, valige see oma organisatsiooni kõigi saadaolevate keskkondade loendist.

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Kuvatõmmis suvandisätetest keskkonnasätetes.":::

Kopeeritakse järgmised konfiguratsioonisätted.

- Andmeallikad, mis on imporditud Power Query
- Andmete ühendamise konfiguratsioon
- Segmendid
- Näitajad
- Suhtlused
- Tegevused 
- Otsing ja filtri register
- Eksportimised
- Värskendamise ajakava
- Rikastamised
- Prognoos mudelid
- Rolli määramised

### <a name="set-up-a-copied-environment"></a>Kopeeritud keskkonna häälestamine

Keskkonna konfiguratsiooni kopeerimisel kuvatakse kinnitusteade, kui kopeeritud keskkond on loodud. Identimisteabe kinnitamiseks tehke järgmist.

1. Andmeallikate loendi nägemiseks valige suvand **Ava andmeallikad**. Kõigis andmeallikates kuvatakse **identimisteabe olek Nõutav**.

   :::image type="content" source="media/data-sources-copied.png" alt-text="Kopeeritud ja autentimist vajav andmeallikate loend.":::

1. Redigeerige andmeallikaid ja sisestage nende värskendamiseks identimisteave. Andmeallikad kaustast Common Data Model ja Dataverse need tuleb luua käsitsi sama nimega nagu lähtekeskkonnas.

1. Pärast andmeallikate värskendamist avage jaotis **Andme** > **Ühendamine**. Siit leiate lähtekeskkonna sätted. Redigeerige neid vastavalt vajadusele või valige **Ühenda** > **kliendiprofiilid ja sõltuvused**, et alustada andmete ühendamise protsessi ja luua ühtne kliendiolem.

   > [!TIP]
   > Kontode ja kontaktide puhul valige **Ühenda kontod** > **Profiilide ja sõltuvuste** ühendamine.

1. Kui andmete ühendamine on lõpule viidud, avage nende värskendamiseks **jaotis Mõõdud** ja **segmendid**.

1. Minge jaotisse **Administraatori** > **ühendused**, et oma uues keskkonnas ühendusi uuesti autentida.

1. **Avage andmete** > **rikastamine ja** andmete **eksportimine** > **·**, et need uuesti aktiveerida.

[!INCLUDE [footer-include](includes/footer-banner.md)]
