---
title: Olemite ühendamine andmete koondamise ajal
description: Ühendage olemid, et luua koondatud kliendiprofiile.
ms.date: 05/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 24b523786158ff36c314601846ee25ea64cfabbe
ms.sourcegitcommit: 5c9c54ffe045017c19f0042437ada2c101dcaa0f
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 07/22/2021
ms.locfileid: "6650129"
---
# <a name="merge-entities"></a>Olemite liitmine

Liitmine on andmete ühendamise viimane etapp. Selle eesmärk on vastavusse viia vastuolus andmed. Vastuolulisteks andmeteks võivad olla kahes andmebaasis olev kliendi nimi, mida näidatakse veidi erinevalt (võrrelge: „Grant Marshall“ ja „Grant Marshal“) või erinevas vormingus telefoninumber (võrrelge: 617-803-091X ja 617803091X). Nende vastuoluliste andmepunktide liitmine toimub järgmisel alusel: atribuut atribuudi järel.

:::image type="content" source="media/merge-fields-page.png" alt-text="Ühenda leht andmete ühtsustamise protsessiga näidates tabelit koos ühendatud väljadega, mis defineerivad ühendatud kliendiprofiili.":::

Pärast [vastendamisetappi](match-entities.md) algab liitmisetapp, valides lehel **Ühendamine** paani **Liitmine**.

## <a name="review-system-recommendations"></a>Vaadake üle süsteemi soovitused

Funktsioonis **Andmed** > **Unify** > **Sulata** saate valida ja välistada atribuudid, mida soovite oma unified customer profile'i profiili sees sulatada. Ühendatud kliendiprofiil on andmete ühendamise protsessi tulemus. Osa atribuute liidab süsteem ise.

Kui soovite vaadata atribuute, mis on kaasatud ühte teie automaatselt ühendatud atribuudisse, valige see ühendatud atribuut tabeli **Kliendi väljad** vahekaardil. Atribuudid, mis koostavad ühendatud atribuuti kuvatakse kahes uues rollis ühendatud atribuudi all.

## <a name="separate-rename-exclude-and-edit-merged-fields"></a>Eralda, nimeta ümber, välista ja redigeeri ühendatud väljad

Saate muuta, kuidas süsteem töötleb ühendatud atribuute ühtse kliendiprofiili loomiseks. Valige **Kuva veel** ja valige, mida soovite muuta.

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Ühendatud atribuutide haldamiseks rippmenüü Kuva veel valikud.":::

Järgmisest jaotisest leiate lisateavet.

## <a name="separate-merged-fields"></a>Eraldaga ühendatud väljad

Ühendatud väljade eraldamiseks leidke atribuut tabelist. Eraldatud väljad kuvatakse üksikute andmepunktidena ühendatud kliendi profiilil. 

1. Valige ühendatud väli.
  
1. Valige **Kuva veel** ja valige **Eraldi väljad**.
 
1. eralduse kinnitamine.

1. Muudatuste töötlemiseks valige **Salvesta** ja **Käivita** .

## <a name="rename-merged-fields"></a>Ühendatud väljade ümbernimetamine

Muutke ühendatud atribuutide kuvatavat nime. Toodanguolemi nime ei saa muuta.

1. Valige ühendatud väli.
  
1. Valige **Kuva veel** ja valige **Nimeta ümber**.

1. Kinnitage muudetud kuvatav nimi. 

1. Muudatuste töötlemiseks valige **Salvesta** ja **Käivita** .

## <a name="exclude-merged-fields"></a>Jäta ühendatud väljad välja

Atribuudi välistamine ühtsest kliendiprofiilist. Kui seda välja kasutatakse muudes protsessides (nt segmendis), eemaldage see nendest protsessidest, enne selle kliendiprofiililt eemaldamist. 

1. Valige ühendatud väli.
  
1. Valige **Kuva veel** ja valige **Välista**.

1. Kinnitage välistamine.

1. Muudatuste töötlemiseks valige **Salvesta** ja **Käivita** . 

Lehel **Ühenda** valige **Välistatud väljad** et näha välistatud väljade loendit. Selle paani abil saate väljad tagasi lisada.

## <a name="manually-combine-fields"></a>Kombineeri välju käsitsi

Määrake ühendatud atribuut käsitsi. 

1. Lehel **Ühenda** valige **Ühenda väljad**.

1. Sisestage **Nimi** ja **Väljundvälja nimi**.

1. Valige väli lisamiseks. Valige **Lisa välju** et ühendada rohkem välju.

1. Kinnitage välistamine.

1. Muudatuste töötlemiseks valige **Salvesta** ja **Käivita** . 

## <a name="change-the-order-of-fields"></a>Väljade järjekorra muutmine

Mõned olemid sisaldavad rohkem üksikasju kui teised. Kui olem sisaldab välja kohta värskeid andmeid, saate väärtusi ühendades prioriseerida selle teiste olemite suhtes.

1. Valige ühendatud väli.
  
1. Valige **Kuva veel** ja valige **Redigeeri**.

1. Valige paanil **Väljade ühendamine** suvand **Nihutage üles/alla** et paika panna järjekord või nihutada ja asetada need soovitud kohale.

1. Kinnitage muudatus.

1. Muudatuste töötlemiseks valige **Salvesta** ja **Käivita** .

## <a name="run-your-merge"></a>Käivitage kooste

Olenemata sellest, kas liidate atribuute ise või lasete seda teha süsteemil, saate alati käivitada kooste. Toimingu käivitamiseks valige lehel **Liitmine** valik **Käivita**.

> [!div class="mx-imgBorder"]
> ![Andmete liitmine „Salvesta ja Käivita“.](media/configure-data-merge-save-run.png "Andmete liitmine „Salvesta ja Käivita“")

Valige **Käivita ainult ühendamine** juhul, kui soovite näha ainult väljundit ühtses kliendiolemis kajastatuna. Järgnevad protsessid värskendatakse [vastavalt värskendusplaanile](system.md#schedule-tab).

Vaige **Käivita Ühenda ja järgnevad protsessid** et värskendada süsteemi sinu muudatustega. Kõik protsessid, sh rikastamine, segmendid ja mõõtkavad, käivituvad automaatselt. Kui kõik järgnevad protsessid on lõpule jõudnud, kajastavad kliendiprofiilid teie tehtud muudatusi.

Kui soovite teha rohkem muudatusi ja etapi uuesti käivitada, saate tühistada poolelioleva ühendamise. Valige **Värskendamine ...** ja valige nähtavale ilmuva külgpaani suvand **Tühista töö**.

> [!TIP]
> Pärast liitmise protsessi käivitamist valige protsessi olek, et avada **Toimingu üksikasjade** paan. See annab ülevaate töötlemisajast, viimasest töötlemiskuupäevast ja kõigist toiminguga seostatud tõrgetest ja hoiatustest. Valige **Üksikasjade** kuvamine, et näha, millised olemid osalevad vastendusprotsessis, kas konfliktilahendused õnnestusid ja kas värskendused on avaldatud.  
> Ülesannete/protsesside jaoks on [kuus tüüpi olekuid](system.md#status-types). Lisaks sõltuvad enamikud protsessid [muudest järgnevatest protsessidest](system.md#refresh-policies).  
> :::image type="content" source="media/process-detail-path.png" alt-text="Süvitsimineku tee et saada protsessi üksikasjad ülesande oleku lingilt.":::

## <a name="next-step"></a>Järgmine etapp

Klientide kohta täiendavate ülevaadete saamiseks seadistage [toiminguid](activities.md), [rikastamist](enrichment-hub.md) või [seosed](relationships.md).

Kui olete tegevused, rikastamine või segmendid juba konfigureerinud, töödeldakse neid automaatselt, et kasutada uusimaid kliendiandmeid.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
