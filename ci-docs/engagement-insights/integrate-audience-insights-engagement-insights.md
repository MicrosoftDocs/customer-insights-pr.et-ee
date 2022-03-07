---
title: Sihtrühma ülevaadete ja kaasamisülevaadete vahelise lingi loomine
description: Looge aktiivne link sihtrühma ülevaadete ja kaasamisstatistika vahel, et võimaldada andmete kahesuunalist jagamist.
ms.date: 09/08/2021
ms.service: customer-insights
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 6aadd6b5018f63362f86c0e3e3ce085e94c47391
ms.sourcegitcommit: 5dd32dc2b18027cf2aa954356dded4bc6aab9801
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 02/12/2022
ms.locfileid: "8116009"
---
# <a name="create-a-link-between-audience-insights-and-engagement-insights"></a>Sihtrühma ülevaadete ja kaasamisülevaadete vahelise lingi loomine

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Kaasamise ja sihtrühma statistika integreerimine ühendab keskkonnad mõlemast võimalusest ja võimaldab andmeid nende vahel kahesuunaliselt jagada.

Kasutage kaasamisülevaadete analüüsimiseks ühendatud profiile ja sihtrühma ülevaadete segmente. Saate eksportida kaasamisülevaadetest kõrge äriväärtusega sündmusi. Kasutage neid sündmusi sihtrühma kaasamise ühendatud profiilide andmete lisamiseks.

## <a name="prerequisites"></a>Eeltingimused

- Vaatajaskonna ülevaateprofiilid tuleb talletada teile kuuluvale Azure Data Lake Storage kontole või hallatavasse [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro)&ndash; andmejärve. 
- Teie sihtrühma ülevaadete keskkond peaks olema seotud Dataverse keskkonnaga. Kui see keskkond kasutab andmemäluks Dataverse keskkonda, kontrollige kindlasti vaatajate ülevaadetes valikut **Andmete ühiskasutuse lubamine**. Lisateavet leiate teemast [Keskkonna loomine ja konfigureerimine publiku ülevaadetes](../audience-insights/create-environment.md).
- Teil on vaja administraatoriõigusi nii kaasamisülevaadete kui ka sihtrühma ülevaadete keskkondade jaoks.
- Lingitud keskkonnad peavad olema samas geograafilises piirkonnas.

> [!NOTE]
> - Kui teie sihtrühma ülevaadete tellimus on prooviversioon, mis kasutab sihtrühma ülevaateid sisemiselt hallatud andmetest, pöörduge abi saamiseks [pirequest@microsoft.com](mailto:pirequest@microsoft.com). 
> - Kui teie sihtrühma ülevaadete keskkond kasutab andmete tallemiseks teie Azure Data Lake Storage kontot, peate lisama oma salvestusruumi kontole kaasamisülevaated Azure'i teenuse subjekti. Lisateavet leiate, kui [loote ühenduse Azure Data Lake Storage kontoga Azure'i teenuse subjektiga, et saada sihtrühma ülevaateid](../audience-insights/connect-service-principal.md). 


## <a name="create-an-environment-link"></a>Keskkonnalingi loomine

Saate luua keskkonnalingi, värskendades **Administreerimine** > **Keskkond** sätteid kaasamisülevaadetes.

**Luua aktiivne seos sihtrühma ülevaadete ja kaasamisstatistika vahel**

1. Valige lehel **Keskkonna administraator** vahekaart **Lingi keskkonnad**.

    :::image type="content" source="media/integrate1.png" alt-text="Keskkonna seadistamine.":::

1. Valige vasakus ülanurgas või ekraani allservas **Häälesta keskkonnad**.

     :::image type="content" source="media/integrate2.png" alt-text="Sihtrühma ülevaadete keskkonna valimine.":::

1. Valige sihtrühma ülevaadete keskkond ja seejärel klõpsake lõpetamiseks **Edasi**. Nüüd saate lingitud keskkondade jaoks valida valikulised funktsioonid.
 
## <a name="enable-audience-insights-unified-profiles-attributes-and-segments"></a>Sihtrühma ülevaadete ühendatud profiilide atribuutide ja segmentide lubamine

Pärast keskkondade linkimist saate lingitud keskkondade jaoks valikulisi funktsioone valida. Need funktsioonid võimaldavad ühtseid profiiliatribuute ja sihtrühma ülevaadete segmente kliendiandmete interaktiivseks analüüsiks.

> [!IMPORTANT]
> Selleks, et sihtrühma ülevaated kuvaksid kaasamisülevaadetes, peate esmalt [käitama kooste- ja järgmised protsessid](../audience-insights/merge-entities.md). Järgmised protsessid on olulised, kuna need loovad ainulaadse tabeli, mis valmistab vaatajaskonna statistika segmendid ette kaasamisstatistikaga jagamiseks. (Süsteemivärskenduse ajasmisel kaasatakse need automaatselt ka järgnevad protsessid.)

**Veebiandmete analüüsimine kaasamisülevaadetes**

1. Lülitage lehel **Keskkonna administraator** sisse **sihtrühma ülevaadete andmete ühiskasutamine kaasamisülevaadete abil** ja seejärel valige **Edasi**.

    :::image type="content" source="media/integrate4.png" alt-text="Funktsioonide valimine.":::

1. Valige ühtsete profiilide atribuudid, millest saavad kaasamisstatistika mõõtmed. (Kõik atribuudid pole kasulikud mõõtmed. Näiteks pole võimalik, et peate veebisaidisündmuste analüüsimiseks lisama atribuute **eesnimi** või **perekonnanimi**.)

    :::image type="content" source="media/integrate5.png" alt-text="Dimensioonide kureerimine.":::

   >[!NOTE]
   > Kõik sihtrühma ülevaadete profiiliatribuudid, mis esindavad identifikaatoreid (nt **ID** ja **alternatiivne ID**), filtreeritakse saadaolevaid atribuute välja ja muutuvad kaasamisülevaadetes profiile.

1. Kui olete atribuutide valimise lõpetanud, valige **Edasi**.
1. Saate lisada kasutajaid, kes saavad kaasamisülevaadetes vaadata sihtrühma ülevaadete profiile ja segmente.

    :::image type="content" source="media/integrate6.png" alt-text="Kliendiandmetele juurdepääsu haldamine.":::

   > [!IMPORTANT]
   > Kui te selles etapis sõnaselgelt kasutajaid ei lisa, peidetakse andmed kaasamise statistika kasutajate eest.
   > Selleks, et sihtrühma ülevaated kuvaksid kaasamisülevaadetes, peate esmalt [käitama kooste- ja järgmised protsessid](../audience-insights/merge-entities.md). Järgmised protsessid on olulised, kuna need loovad ainulaadse tabeli, mis valmistab vaatajaskonna statistika segmendid ette kaasamisstatistikaga jagamiseks. (Süsteemivärskenduse ajasmisel kaasatakse need automaatselt ka järgnevad protsessid.)

1. Vaadake oma valik läbi ja seejärel valige **Valmis**.

    :::image type="content" source="media/integrate7.png" alt-text="Kliendiandmete sätete läbivaatamine.":::

## <a name="export-refined-events-to-audience-insights"></a>Ekspordi täpsustatud sündmused sihtrühma ülevaadetesse

Pärast keskkondadevahelise lingi loomist saate eksportida kaasamisülevaadetest sündmuseid sihtrühma ülevaadetele ja neid uue allikana andmeallikasse lisada. 

Lisateavet leiate teemast [Veebiandmete integreerimine kaasamisülevaadetest ja sihtrühma ülevaadetest](../audience-insights/integrate-engagement-insights.md).

<!--
## Share engagement insights refined events with audience insights

After you create a link between environments, a new option becomes available for you to share [refined events](refined-events.md) with audience insights.

Consider the following when creating refined events for audience insights: 

- Provide a meaningful name for the refined event. It will be used as an activity name in audience insights.
- Select at least the following properties to create an activity in audience insights: 
    - Signal.Action.Name indicates the activity details.
    - Signal.User.Id maps with the customer ID.
    - Signal.View.Uri is a web address as a basis for segments or measures.
    - Signal.Export.Id is a primary key for events.
    - Signal.Timestamp determines the date and time for the activity.

To share refined events:

1. From the engagement insights menu, select **Data** and then select the **Events** tab.
2. On the **Action** menu, select **Share as activity**.

    :::image type="content" source="media/integrate8.png" alt-text="Data shared events settings.":::

3. You can view and stop actively shared events on the **Export and Sharing** tab.
4. -- per Michael K, we need a mock here (Mukesh needs to update to reflect what happens in AUI once a user shares a refined event (i.e. no longer AUI, data wrangler needs to go discover data in the storage, the shared event is available as a DS and entity, correct?)

### Attach refined events shared as activities to unified profiles in audience insights

You can bring customer web activity data from engagement insights into audience insights. In addition to transactional, demographic, or behavioral data, you can view activities on the web in unified customer profiles. You can then use these profiles to get insights such as segments, measures, and predictions for audience activation.

Follow the steps in [data unification](../audience-insights/data-unification.md) to map, match, and merge website authentication information to unified profiles in audience insights.

You can also share refined events that are now available in audience insights, identified as data sources and entities. 

Next, you can relate event data from engagement insights as unified activities in customer profiles.

### Relate refined event data as an activity of a customer profile

After unifying the data, you can configure the activity for the customer profile. For more information, go to [Customer activities](../audience-insights/activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Activities page with expanded Edit activity pane.":::

Next, configure the new activity by using mapping elements: 

- **Primary Key**: Signal.Export.Id, a unique ID that is available for every event record in engagement insights. This property is automatically generated.

- **Timestamp**: Signal.Timestamp in the event property.

- **Event**: Signal.Name, the event name that you want to track.

- **Web address**: Signal.View.Uri that refers to the URI of the page that created the event.

- **Details**: Signal.Action.Name to represent the information to associate with the event. The selected property in this case indicates that the event is for email promotion.

- **Activity type**: In this example, we choose the existing activity type WebLog. This selection is a useful filter option to run prediction models or create segments based on this activity type.

- **Set up relationship**: This important setting ties the activity to existing customer profiles. **Signal.User.Id** is the identifier configured in the SDK to be collected. It relates to the user ID in other data sources that are configured in audience insights. 

This example configures the relationship between Signal.User.Id and RetailCustomers:CustomerRetailId, which is the primary key that was identified in the map step of the data unification process.

After processing the activities, you can review customer records and open a customer card to see activities from engagement insights in the timeline. 

> [!TIP]
> To find a customer ID that has an engagement insights activity, go to **Entities** and preview the data for the UnifiedActivity entity. **ActivityTypeDisplay = WebLog** contains the engagement insights activity configured in the preceding example. Copy the customer ID for one of those records and search<!--note from editor: Edit okay? I couldn't quite follow this.-- > for that ID on the **Customers** page.

--> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
