---
title: Power Apps konnektor
description: Ühendumine Power Appsi ja Power Automate'iga.
ms.date: 10/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: e99d7d4f231eb2ade67f27c9e52c61af3a21b99d
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642941"
---
# <a name="microsoft-power-apps-connector-preview"></a>Microsoft Power Apps’i konnektor (eelvaade)

Ühendatud kliendiprofiilide toomine oma isikupärastatud rakendustesse Power Appsi abil.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Power Appsi ja Dynamics 365 Customer Insightsi ühendamine

Customer Insights on üks paljudest [Power Appsis saadaolevatest andmeallikatest](/powerapps/maker/canvas-apps/working-with-data-sources).

Vaadake Power Appsi dokumentatsiooni, et saada teada, kuidas [lisada rakendusele andmeühendust](/powerapps/maker/canvas-apps/add-data-connection). Soovitame teil ka vaadata üle ka teema [Kuidas Power Apps kasutab delegeerimist lõuendirakendustes suurte andmekogumite käsitlemiseks](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Saadaolevad olemid

Pärast Customer Insightsi andmeühendusena lisamist saate Power Appsis valida järgmised olemid.

- **Klient**: andmete kasutamine [ühendatud kliendiprofiililt](customer-profiles.md).
- **UnifiedActivity** : [tegevuse ajaskaala](activities.md) kuvamiseks rakenduses.
- **ContactProfile** : kliendi kontaktide kuvamiseks. See olem on saadaval ainult Customer Insightsi keskkondades ärikontode jaoks.

## <a name="limitations"></a>Piirangud

### <a name="retrievable-entities"></a>Toodavad olemid

Power Apps konnektori kaudu saate tuua olemid **Klient**, **UnifiedActivity**, **Segmendid** ja **ContactProfile**. ContactProfile on saadaval ainult Customer Insightsi eksemplaris ärikontode jaoks. Teised olemid on näidatud, kuna aluseks olevad konnektorid toetavad neid läbi Power Automate’i päästikute.

Saate teha maksimaalselt 100 kõnet 60 sekundi jooksul. API lõpp-punkti saate helistada mitu korda, kasutades parameetrit $skip. [Lugege lisateavet parameetri $skip kohta](/connectors/customerinsights/#get-items-from-an-entity).

### <a name="delegation"></a>Delegeerimine

Delegeerimine töötab ainult olemi **Klient** ja olemi **UnifiedActivity** jaoks. 

- Olemi **Klient** delegatsioon: selle olemi korral delegatsiooni kasutamiseks peavad väljad olema indekseeritud [Otsingu- ja filtriregistris](search-filter-index.md).  
- Olemi **UnifiedActivity** delegeerimine: selle olemi delegeerimine töötab ainult väljade **ActivityId** ja **CustomerId** jaoks.  
- Delegeerimine **ContactProfile** jaoks: Selle üksuse delegeerimine toimib ainult väljade **ContactId** ja **CustomerId** puhul. ContactProfile on saadaval ainult Customer Insightsi keskkondades ärikontode jaoks.

Lisateavet delegatsiooni kohta leiate [Power Apps delegeeritavad funktsioonid ja toimingud](/powerapps/maker/canvas-apps/delegation-overview). 

## <a name="example-gallery-control"></a>Galerii juhtelemendi näide

Kliendiprofiile saate lisada [galerii juhtelemendile](/powerapps/maker/canvas-apps/add-gallery).

1. Lisage loodavale rakendusele **galerii** juhtelement.

    > [!div class="mx-imgBorder"]
    > ![Galerii elemendi lisamine.](media/connector-powerapps9.png "Galerii elemendi lisamine.")

2. Valige üksuste andmeallikaks **Klient**.

    > [!div class="mx-imgBorder"]
    > ![Andmeallika valimine.](media/choose-datasource-powerapps.png "Andmeallika valimine.")

3. Kliendi olemi galerii välja valimiseks saate muuta paremal asuvat andmete paneeli.

4. Kui tahate näidata galeriis valitud kliendi mistahes välja, täitke sildi **Teksti** atribuut kasutades **{Name_of_the_gallery}.Valitud.{property_name}**  
    - Näide: _Gallery1.Selected.address1_city_

5. Kliendi ühtse ajajoone näitamiseks lisage galerii element ja ja lisage **Üksused** atribuut, kasutades **Filter('UnifiedActivity', CustomerId = {Customer_Id})**  
    - Näide: _Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)_


[!INCLUDE [footer-include](includes/footer-banner.md)]
