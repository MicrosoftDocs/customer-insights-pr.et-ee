---
title: Lehteraruanded
description: Lehteraruannete kasutamine, et mõista, kuidas sihtrühm otsuseid teeb.
ms.reviewer: mhart
ms.author: kamacdon
author: kamacdon
ms.date: 09/21/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: efb10f2664630a5851d9582ff09c378c01777b96
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558915"
---
# <a name="create-and-manage-funnel-reports"></a>Lehterdiagrammi loomine ja haldamine

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Lehtriaruanne kogub teavet veebisaidi või mobiilirakenduse kaudu teie klienditeekonna etappide kohta. See aitab teil mõista, kuidas vaatajaskond protsessi kaudu areneb ja tuvastab ärajäämispunktid. Näiteks saate lehtriaruande abil tuvastada teed, mida kliendid enne ostmist teevad. Lehteraruanne annab andmeid, et kinnitada otsuseid ning tuvastada valdkonnad, mille puhul optimeerimine ja protsessi täiustused on võimalikud.

## <a name="create-a-funnel-report"></a>Lehteraruande loomine

Lehteraruande loomiseks määrake iga etapi jaoks järgmised sammud ja tegevus. Tegevus on [sündmus](glossary.md) mis tähistab kasutaja käitumist. Lehteraruandes kuvatakse määratletud etapiga lõpule jõudnud kasutajate arvu. 

1. Lehteraruande käivitamiseks minge **Lehtrisse** ja valige käsk **Uus lehter**.

1. Valige **Lehterredaktor** jaotises **Sammud** ja valige **Lisa samm.** 

1. Sisestage nimi **Etapi pealkiri**.

   :::image type="content" source="media/new-funnel-report.png" alt-text="Uus lehteraruanne.":::

1. Valige **Tegevus**. Tegevuskirjed, kui kasutaja vaatab lehte (**Kuva** tegevus) või suhtleb sisuga (**Tegevus** tegevus).

1. Kasutage **Etapi kriteeriumi** tegevuse määramiseks. [Hierarhiad](dimensions.md) on atribuudid, mis saavad andmeid kirjeldada, filtreerida või rühmitada.

1. Soovi korral saate konfigureerida mitme tingimusega lehtrietappe. Kui soovite sammus määrata rohkem lisatingimust, valige **Lisa tingimus**. Lisakriteeriumides peab kasutama sama tegevusetüüpi. Saate valida, kas JA- või VÕI-tehtemärk on ühendatud mitme tingimusega.

   :::image type="content" source="media/funnel-add-condition.png" alt-text="Lehtriredaktor, kus on näidatud etapikonfiguratsioon mitmetingimuslike sammudega.":::

1. Valige **Lisa etapp** seni, kuni olete aruandega soovitud etappidega lõpule jõudnud.

1. Valige **Salvesta**, nimetage aruanne ja seejärel **Salvestage** uuesti. 

### <a name="example-fourth-coffee-company-funnel-report"></a>Näide: Fourth Coffee company lehteraruanne

Järgmine stsenaarium kasutab ühte viisi lehtearuande kasutamise jaoks. Analüütik ettevõttega Fourth Coffee soovib mõista hiljutise reklaami mõju kordustellimuste määradele. Analüütik loob lehtriaruande klienditegevuse tuvastamiseks. See algab, kui klient saabub ettevõtte avalehele ja kestab, kuni kasutatakse kordustellimuse reklaamikoodi. Analüütik loob lehteraruande järgmiste toimingutega:

1. etapp: kliendid, kes sadetakse avalehele   
2. etapp: kliendid, kes ostavad   
3. etapp: kliendid, kes kasutavad kampaaniakoodi tellimuse allahindluse toomiseks   
4. etapp: kordustellimuse registreerimine   

:::image type="content" source="media/funnel-report-example.png" alt-text="lehteraruande näide.":::
  
See lehter võimaldab näha kasutajate arvu, kes kasutavad kampaaniakoodi pärast ühe korraga ostmist kordustellimuse programmis registreerumiseks.

### <a name="configure-advanced-settings"></a>Konfigureeri täpsemad sätted 

Lehtriaruannete abil saate määrata ajapiirangu, mis kulub lehtri lõpetamiseks. Näiteks saate lehtri lõpetamiseks määrata ajaks neli päeva. See säte loendab edukaid kordustellimuse registreerumiseid, mis on aset leidnud nelja päeva jooksul pärast avalehe kasutaja külastamist.

1. Minge **Lehtrid**, et avada **Lehtrite arhiiv**.

1. Valige aruande avamiseks soovitud nimi. 

1. Valige paanil **Lehtriredaktor** suvand **Täpsemad sätted**. 

1. Määra suvandi Piira lehterdiagrammi lõpetamise aeg väärtuseks **Sees**.

   :::image type="content" source="media/funnel-limit-time.png" alt-text="Lehtriredaktor, kus on kuvatud täiustatud säte ja võimalused lehtri lõpetamiseks aja piiramiseks.":::

1. Valige rippmenüüst **Määra limiit**, kui lehterdiagramm peab olema lõpule jõudnud.

1. Vajutage nuppu **Salvesta**, et muudatused rakendada.


## <a name="cross-channel-funnel-reports"></a>Kanaliülesed lehterdiagrammi aruanded 

Kaasamisülevaated võivad koguda mobiilirakenduses ka käitumuslikke kliendiandmeid. Kui olete mobiilirakenduse käivitanud kaasamisülevaadete [Android SDK](get-started-android.md) või [iOS SDK](get-started-ios.md), te saate luua kanaliülesed lehterdiagrammi aruanded. 

### <a name="create-a-cross-channel-funnel-report"></a>Looge kanaliülesed lehterdiagrammi aruanded 

1. Järgige [lehterdiagrammi aruande loomine](#create-a-funnel-report) juhiseid.    

1. Selleks, et jälgida, kuidas teie kliendid teie brändi kasutavad, nii oma veebisaidi kui ka mobiilirakenduse või mitme veebisaidi kaudu, kasutage tööruumi vahetajat, et luua lehterdiagrammi etapid muude tööruumide andmetega. Valige **Lehterdiagrammi redigeerija** jaotises **Sammud**, millisest tööruumist teie lehterdiagrammi etapi andmed tuleks luua.

## <a name="manage-funnel-reports"></a>Halda lehteraruandeid

Lehteraruandeid saate vaadata, et analüüsida andmeid, jälgida jõudlust ja koguda ülevaateid.

> [!NOTE]
> - Kaasamisülevaadete lehteraruanded toetavad praegu stsenaariumeid, mille korral kõik lehtri kasutajad on anonüümsed või kõik kasutajad autenditakse. 
> - Lehteraruannete varasemad andmed on saadaval viimased 30 päeva.

### <a name="view-funnel-reports"></a>Kuva lehteraruanne

1. Minge **Lehtrid**, et avada **Lehtrite arhiiv**.
1. Valige aruande avamiseks soovitud nimi.    

### <a name="see-the-data-collected-for-a-report"></a>Aruande kohta kogutud andmete vaatamine   

Faasi kohta teabe kuvamine

- Osutage aruande etapile.

:::image type="content" source="media/funnel-step-data.png" alt-text="lehtraruande andmed.":::

### <a name="change-the-date-range-for-the-funnel-report"></a>Lehteraruande kuupäevavahemiku muutmine

1. Minge **Lehtrid**, et avada **Lehtrite arhiiv**.

1. Valige aruande avamiseks soovitud nimi.

1. Avage **ajavahemik** ja valige loendist ajaperiood või **Fikseeritud kuupäevavahemik** kuupäevavahemiku määramiseks.

## <a name="edit-or-delete-funnel-reports"></a>Lehteraruannete redigeerimine või kustutamine

Lehetraruande nime saate muuta, kustutada või aruande samme muuta.

### <a name="rename-or-delete-a-funnel-report"></a>Lehteraruande ümbernimetamine või kustutamine

1. Minge **Lehtrid**, et avada **Lehtrite arhiiv**. 

1. Valige **Veel** aruande kõrval ja seejärel **Redigeerige nime** või **Kustutage**.

### <a name="edit-a-funnel-step"></a>Leheteraruande etapi redigeerimine  

1. Minge **Lehtrid**, et avada **Lehtrite arhiiv**. 

1. Valige aruande avamiseks soovitud nimi.

1. Valige redigeeritav etapp.

1. Valige **Redigeeri**.

1. Värskendage **Lehteraruande redaktoris** teavet, mida soovite muuta.  

1. Valige **Salvesta**.

### <a name="reorder-a-funnel-step"></a>Leheteraruande etapi muutmine

1. Minge **Lehtrid**, et avada **Lehtrite arhiiv**. 

1. Valige aruande avamiseks soovitud nimi.

1. Valige redigeeritav etapp.

1. Sammu teisaldamiseks valige **Nihuta** ja siis **Üles**, **Alla** **Üles** või **Alla**, etapi liigutamiseks.

### <a name="delete-a-funnel-step"></a>Leheteraruande etapi kustutamine

1. Minge **Lehtrid**, et avada **Lehtrite arhiiv**. 

1. Valige aruande avamiseks soovitud nimi.

1. Valige eemaldatava etapp ja valige seejärel käsk **Eemalda**.

## <a name="funnel-insights"></a>Lehterdiagrammi ülevaated 

Kaasamisülevaated annavad nüüd klientidele lehterdiagrammi ülevaateid. Lehterdiagrammi ülevaadete abil saate koguda klientide käitumise kohta vihjeid lehtriaruande etappide kohta. Uue lehtriaruande loomisel ja salvestamisel luuakse aruande jaoks automaatselt lehtridiagrammi ülevaated. 

:::image type="content" source="media/funnel-insights.png" alt-text="Lehterdiagrammi ülevaated.":::

> [!NOTE]
> Lehtriülevaateid saab luua ainult lehtrietappide jaoks, mis **ei** sisalda kohandatud dimensioone. Lehtri kõigi etappide jaoks lehtriülevaadete loomiseks kasutage lehtrietappide loomiseks valmis kaasamisülevaateid. 

Lehtridiagrammi ülevaateid saate vaadata järgmistest kategooriatest nii põhi- kui ka etapitasemetel. 

 - Teisendusmäär
 -    Teisendusmäär üksuste Siirdu maksma ja Osta vahel on 22%.
 - Üleminekuaeg 
 -    Keskmine üleminekuaeg üksuste Ostukorv ja Siirdu maksma vahel on 23 minutit. 
 - Lõpuleviimise aeg 
 -    Kliendi keskmine lehterdiagrammi lõpule viimiseks kuluv aeg on 47 minutit. 

Kasutage neid ülevaateid, et uurida klientide käitumist ja paremini mõista oma lehtriaruandes salvestatud punkte ja teisendusi. 

Kui soovite võrrelda ülevaateid erinevate etappide vahel, valige **Vaadake etappideks liigendamist** või **Võrrelge teiste sammudega** ülevaadete kaartidest. Nendes diagrammides kuvatakse lehtri iga etapi mõõdikuid võrdlev ribagraafik. 

Lehtridiagrammi ülevaated arvutatakse ümber iga 24 tunni järel või lehtriaruande **salvestamisel**. 

> [!NOTE]
> Lehtridiagrammi ülevaadete vaatamiseks tuleb aruanne salvestada iga kord, kui teete muudatusi. 

