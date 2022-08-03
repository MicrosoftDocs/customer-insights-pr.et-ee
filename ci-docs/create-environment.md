---
title: 'Kuidas: uue keskkonna loomine'
description: Sammud keskkondade loomiseks rakenduses Dynamics 365 Customer Insights.
ms.date: 05/31/2022
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
ms.openlocfilehash: 33c8910b7a4dd8723c0d62f2e28228cd2d8df4b7
ms.sourcegitcommit: 5716025eb4828425ca237377b02a892de8689f4a
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 07/13/2022
ms.locfileid: "9142814"
---
# <a name="how-to-create-a-new-environment"></a>Kuidas: uue keskkonna loomine

Pärast [kordustellimuslitsentsi Dynamics 365 Customer Insights](paid-license.md) ostmist saab rentniku üldadministraator Microsoft 365 meili, mis kutsub teda keskkonda looma. Alustamiseks minge [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start). Selle stsenaariumi korral võite minna otse 1. sammu juurde [: esitage põhiteave](#step-1-provide-basic-information).

Pärast esimese keskkonna loomist saab Microsoft 365 rentniku üldadministraator [lisada kasutajaid oma organisatsiooni administraatoritena](permissions.md). Edasi liikudes saavad need administraatorid hallata kasutajaid ja keskkondi. Kui teie organisatsioon ostab Customer Insightsi jaoks rohkem kui ühe litsentsi, [võtke saadaolevate keskkondade arvu suurendamiseks ühendust meie tugitiimiga](https://go.microsoft.com/fwlink/?linkid=2079641). Võimsuse ja lisavõimsuse kohta lisateabe saamiseks vaadake üle [Dynamics 365-i litsentsimisjuhend](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!TIP]
> Kui soovite teenust proovida, lugege teemat [Proovikeskkonna seadistamine](trial-signup.md).

## <a name="prerequisites"></a>eeltingimused

Keskkondade [loomiseks või haldamiseks vajate](permissions.md) Customer Insightsis administraatoriõigusi.

## <a name="start-the-environment-creation-process"></a>Käivitage keskkonna loomise protsess

1. Avage keskkonnavalija ja valige **+ Uus**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Valige keskkonnavalija.":::

1. Järgige järgmistes jaotistes kirjeldatud juhendatud kogemusi, et anda kogu vajalik teave uue keskkonna jaoks. Kui konfigureerisite keskkonna varem, saate ka [konfiguratsiooni](#copy-the-environment-configuration) kopeerida.

## <a name="step-1-provide-basic-information"></a>1. toiming: andke põhiteavet

Valige **Põhiteabe** etapis, kas soovite luua soovitud keskkonda kopeerimiskeskkonnast või [kopeerida andmed muust keskkonnast](#copy-the-environment-configuration).

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Uue ühenduse loomine rakenduses Customer Insights.":::

Esitage järgmised andmed.

- **Nimi**: selle keskkonna nimi. Olemasolevast keskkonnast kopeerides on see väli juba täidetud, kuid saate seda muuta.
- **Valige oma ettevõte**: Valige uue keskkonna jaoks peamine sihtrühm. Võite töötada eraklientidega (B2C) või [ ettevõtetega](work-with-business-accounts.md) (B2B). Kui teie organisatsioon teeb äri peamiselt üksikisikutega (nt jaemüüja või kohvik), valige üksiktarbijad. Kui teie peamine vaatajaskond on teised ettevõtted, näiteks autotootja või paberifirma, valige ettevõtte kontod.
- **Tüüp**: Valige, kas soovite luua töö- või liivakastikeskkonna. Liivakastikeskkonnad ei luba ajastatud andmeid värskendada ja on mõeldud eelinstallimiseks ja testimiseks. Liivakastikeskkonnad kasutavad põhilist sihtrühma, kes on praegu valitud töökeskkonnas.
- **Piirkond**: piirkond, kus teenus juurutatakse ja majutatakse. Oma [Azure Data Lake Storage konto](own-data-lake-storage.md) kasutamiseks või [olemasoleva Microsoft Dataverse organisatsiooniga](customer-insights-dataverse.md) ühenduse loomiseks peab Customer Insightsi keskkond asuma samas piirkonnas.

## <a name="step-2-configure-data-storage"></a>Teine etapp: Andmemälu konfigureerimine

**Valige etapis Andmesalvestusruum**, kus Soovite Customer Insightsi andmeid talletada.

Saate valida kahe võimaluse vahel:

- **Customer Insightsi salvestusruum**: andmesalvestusruumi haldab Customer Insightsi meeskond. See on vaikevalik ja kui teie enda salvestusruumikontole andmete salvestamiseks pole konkreetseid nõudeid, soovitame seda suvandit kasutada.
- **Azure Data Lake Storage**: Määrake andmete salvestamiseks oma Azure Data Lake Storage konto, et teil oleks täielik kontroll andmete salvestamise üle. Lisateavet vaadake jaotisest [Oma Azure Data Lake Storage konto](own-data-lake-storage.md) kasutamine.

:::image type="content" source="media/data-storage-environment.png" alt-text="Valige oma andmete salvestamiseks eelistatud suvand.":::

## <a name="step-3-connect-to-microsoft-dataverse"></a>Kolmas etapp: Microsoft Dataverse-ga ühenduse loomine

**Microsoft Dataverse** etapp lubab teil Customer Insights'i oma Dataverse keskkonnaga ühendada. Andke andmeid Dataverse ühiskasutusse, et kasutada neid ärirakendustega, mis põhinevad rakendusel Dataverse Dynamics 365 Marketing või mudelipõhised rakendused rakenduses Power Apps.

Jätke see väli tühjaks, kui teil pole oma Dataverse keskkonda, ja me loome selle teile.

Lisateavet leiate teemast [Customer Insightsi andmetega töötamine.Microsoft Dataverse](customer-insights-dataverse.md)

:::image type="content" source="media/dataverse-provisioning.png" alt-text="andmete jagamine Microsoft Dataverse automaatselt lubatud uutes netikeskkondades.":::

### <a name="step-4-finalize-the-settings"></a>Neljas etapp: Viige sätted lõpule

**Läbivaatamise** etapis läbige kõik määratud seaded. Kui kõik paistab valmis, valige keskkonna häälestamiseks käsk **Loo**.

Mõnda seadet saate hiljem muuta. Lisateavet leiate teemast [Keskkondade haldamine](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Uue keskkonnaga töötamine

Kliendiülevaadete konfigureerimise alustamiseks vaadake üle järgmised artiklid.

- [Lisage veel kasutajaid ja määrake õiguseid](permissions.md)i.
- [Tooge sisse oma andmeallikaid](data-sources.md) ja käivitage need [andmete ühendamise protsessis](data-unification.md) , et [saada ühtseid kliendiprofiile](customer-profiles.md).
- [Rikastage ühendatud kliendiprofiile](enrichment-hub.md) või [käivitage ennetavad mudeleid](predictions-overview.md).
- [Looge segmente](segments.md) klientide rühmitamiseks ja [mõõdikuid](measures.md) KPI-de arvustamiseks.
- [Seadistage ühendused](connections.md) ja [eksporte](export-destinations.md) andmete alamhulkade töötlemiseks muudes rakendustes.

## <a name="copy-the-environment-configuration"></a>Kopeerige keskkonna konfiguratsioon

Administraatorina saate uue keskkonna loomisel kopeerida konfiguratsiooni olemasolevast keskkonnast.

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Kuvatõmmis suvandisätetest keskkonnasätetes.":::

Näete teie ettevõtte kõigi saadaolevate keskkondade loendit, kust saate andmeid kopeerida.

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

## <a name="set-up-a-copied-environment"></a>Kopeeritud keskkonna häälestamine

Keskkonna konfiguratsiooni kopeerimisel peate identimisteabe kinnitamiseks läbima mõned lisatoimingud.

- Kliendiprofiilid. Esmalt autentige ja neelake alla andmeallikad ning käivitage kliendiprofiilide taasloomiseks andmete ühendamine.
- Andmeallika identimisteave. Andmeallikate käsitsi autentimiseks ja värskendamiseks peate esitama iga andmeallikas mandaadi.
- Andmeallikad kaustast Common Data Model ja Dataverse. Peate need andmeallikad looma käsitsi sama nimega nagu lähtekeskkonnas.
- Ühenduse saladused, mida kasutatakse ekspordiks ja rikastamiseks. Peate seosed uuesti autentima ning seejärel rikastamise ja ekspordi uuesti aktiveerima.

Kui kopeeritud keskkond on loodud, näete kinnitusteadet. Andmeallikate loendi nägemiseks valige suvand **Ava andmeallikad**.

Kõik andmeallikad kuvavad olekut **Mandaat nõutav**. Redigeerige andmeallikaid ja sisestage nende värskendamiseks identimisteave.

:::image type="content" source="media/data-sources-copied.png" alt-text="Kopeeritud ja autentimist vajav andmeallikate loend.":::

Pärast andmeallikate värskendamist avage jaotis **Andme** > **Ühendamine**. Siit leiate lähtekeskkonna sätted. Redigeerige neid vastavalt vajadusele või valige **Käivita**, et käivitada andmete ühendamise protsess ja luua ühtne kliendi olem.

Kui andmete ühendamine on lõpetatud, avage **Meetmed** ja **Segmendid**, et neid samuti värskendada.

Enne ekspordi ja rikastamise uuesti aktiveerimist minge jaotisse **Administraatori** > **ühendused**, et ühendada ühendused uues keskkonnas uuesti.

[!INCLUDE [footer-include](includes/footer-banner.md)]
