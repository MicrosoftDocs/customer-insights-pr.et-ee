---
title: Power Apps konnektor
description: Ühendumine Power Appsi ja Power Automate'iga.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 3fa91553fd50a22ab62b5a2b1e3f13b9483776a8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598150"
---
# <a name="microsoft-power-apps-connector-preview"></a>Microsoft Power Apps’i konnektor (eelvaade)

Ühendatud kliendiprofiilide toomine oma isikupärastatud rakendustesse Power Appsi abil.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Power Appsi ja Dynamics 365 Customer Insightsi ühendamine

Customer Insights on üks paljudest [Power Appsis saadaolevatest andmeallikatest](/powerapps/maker/canvas-apps/working-with-data-sources).

Vaadake Power Appsi  dokumentatsiooni, et saada teada, kuidas [lisada rakendusele andmeühendust](/powerapps/maker/canvas-apps/add-data-connection). Soovitame teil ka vaadata üle ka teema [Kuidas Power Apps kasutab delegeerimist lõuendirakendustes suurte andmekogumite käsitlemiseks](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Saadaolevad olemid

Pärast Customer Insightsi andmeühendusena lisamist saate Power Appsis valida järgmised olemid.

- Klient: [ühendatud kliendiprofiili](customer-profiles.md) andmete kasutamine.
- UnifiedActivity: rakenduses [tegevuse ajajoone](activities.md) kuvamiseks.

## <a name="limitations"></a>Piirangud

### <a name="retrievable-entities"></a>Toodavad olemid

Saate tuua ainult olemid **Klient**, **UnifiedActivity** ja **Segmendid** Power Appsi konnektori kaudu. Teised olemid on näidatud, kuna aluseks olevad konnektorid toetavad neid läbi Power Automate’i päästikute.  

### <a name="delegation"></a>Delegeerimine

Delegeerimine töötab ainult olemi Klient ja olemi UnifiedActivity jaoks. 

- Olemi **Klient** delegatsioon: selle olemi korral delegatsiooni kasutamiseks peavad väljad olema indekseeritud [Otsingu- ja filtriregistris](search-filter-index.md).  

- Olemi **UnifiedActivity** delegeerimine: selle olemi delegeerimine töötab ainult väljade **ActivityId** ja **CustomerId** jaoks.  

- Lisateavet delegeerimise kohta leiate teemast [Power Appsi delegeeritavad funktsioonid ja toimingud](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps). 

## <a name="example-gallery-control"></a>Galerii juhtelemendi näide

Näiteks lisate kliendiprofiilid [galerii juhtelementi](/powerapps/maker/canvas-apps/add-gallery).

1. Lisage loodavale rakendusele **Galerii** juhtelement.

> [!div class="mx-imgBorder"]
> ![Galerii elemendi lisamine](media/connector-powerapps9.png "Galerii elemendi lisamine")

1. Valige üksuste andmeallikaks **Klient**.

    > [!div class="mx-imgBorder"]
    > ![Andmeallika valimine](media/choose-datasource-powerapps.png "Andmeallika valimine")

1. Kliendi olemi galerii välja valimiseks saate muuta paremal asuvat andmete paneeli.

1. Kui tahate näidata galeriis valitud kliendi mistahes välja, täitke sildi teksti atribuut:  **{Name_of_the_gallery}.Selected.{property_name}**

    Näide: Gallery1.Selected.address1_city

1. Kliendi ühtse ajajoone näitamiseks lisage galerii element ja üksuste atribuut: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**

    Näide: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)


[!INCLUDE[footer-include](../includes/footer-banner.md)]