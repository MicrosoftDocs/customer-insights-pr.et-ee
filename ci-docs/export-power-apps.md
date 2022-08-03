---
title: Power Apps’i konnektor (eelvaade)
description: Ühendumine Power Appsi ja Power Automate'iga.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 8807e82e65ea20d1a7f7dc07552229f377927eed
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196895"
---
# <a name="power-apps-connector-preview"></a>Power Apps’i konnektor (eelvaade)

Ühendatud kliendiprofiilide toomine oma isikupärastatud rakendustesse Microsoft Power Appsi abil.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Power Appsi ja Dynamics 365 Customer Insightsi ühendamine

Customer Insights on üks paljudest [Power Appsis saadaolevatest andmeallikatest](/powerapps/maker/canvas-apps/working-with-data-sources).

Vaadake Power Appsi dokumentatsiooni, et saada teada, kuidas [lisada rakendusele andmeühendust](/powerapps/maker/canvas-apps/add-data-connection). Soovitame teil ka vaadata üle ka teema [Kuidas Power Apps kasutab delegeerimist lõuendirakendustes suurte andmekogumite käsitlemiseks](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Saadaolevad olemid

Pärast Customer Insightsi lisamist andmeühendusena valige jaotises järgmised olemid Power Apps:

- **Klient**: andmete kasutamine [ühendatud kliendiprofiililt](customer-profiles.md).
- **UnifiedActivity** : [tegevuse ajaskaala](activities.md) kuvamiseks rakenduses.
- **ContactProfile** : kliendi kontaktide kuvamiseks. See olem on saadaval ainult Customer Insightsi keskkondades ärikontode jaoks.

## <a name="limitations"></a>Piirangud

### <a name="retrievable-entities"></a>Toodavad olemid

Power Apps konnektori kaudu saate tuua olemid **Klient**, **UnifiedActivity**, **Segmendid** ja **ContactProfile**. ContactProfile on saadaval ainult Customer Insightsi keskkondades ärikontode jaoks. Teised olemid on näidatud, kuna aluseks olevad konnektorid toetavad neid läbi Power Automate’i päästikute.

Saate teha maksimaalselt 100 kõnet 60 sekundi jooksul. SAATE API lõpp-punktile helistada mitu korda, kasutades parameetrit $skip. [Lisateave parameetri $skip kohta](/connectors/customerinsights/#get-items-from-an-entity).

### <a name="delegation"></a>Delegeerimine

Delegeerimine töötab ainult olemi **Klient** ja olemi **UnifiedActivity** jaoks.

- Delegeerimine kliendi **olemi jaoks**: delegeerimise kasutamiseks selles olemis tuleb väljad otsingu- ja filtriregistris [indekseerida](search-filter-index.md).  
- Olemi **UnifiedActivity** delegeerimine: selle olemi delegeerimine töötab ainult väljade **ActivityId** ja **CustomerId** jaoks.  
- Delegeerimine **ContactProfile** jaoks: Selle üksuse delegeerimine toimib ainult väljade **ContactId** ja **CustomerId** puhul. ContactProfile on saadaval ainult Customer Insightsi keskkondades ärikontode jaoks.

Lisateavet delegatsiooni kohta leiate [Power Apps delegeeritavad funktsioonid ja toimingud](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="example-gallery-control"></a>Galerii juhtelemendi näide

Soovi korral saate galerii juhtelemendile [lisada kliendiprofiile](/powerapps/maker/canvas-apps/add-gallery).

1. Lisage loodavale rakendusele **galerii** juhtelement.
  
   :::image type="content" source="media/connector-powerapps9.png" alt-text="Galerii elemendi lisamine.":::

1. Valige üksuste andmeallikaks **Klient**.

   :::image type="content" source="media/choose-datasource-powerapps.png" alt-text="Andmeallika valimine.":::

1. Muutke paremal asuvat andmepaneeli, et valida, millist välja kliendi olem galeriis kuvada.

1. Kui tahate näidata galeriis valitud kliendi mistahes välja, täitke sildi **Teksti** atribuut kasutades **{Name_of_the_gallery}.Valitud.{property_name}**  
    - Näide: _Gallery1.Selected.address1_city_

1. Kliendi ühtse ajajoone näitamiseks lisage galerii element ja ja lisage **Üksused** atribuut, kasutades **Filter('UnifiedActivity', CustomerId = {Customer_Id})**  
    - Näide: _Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)_

[!INCLUDE [footer-include](includes/footer-banner.md)]
