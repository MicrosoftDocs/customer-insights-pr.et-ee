---
title: Seosed olemite ja olemiteede vahel
description: Looge ja hallake mitmest andmeallikast pärit olemite vahelisi seoseid.
ms.date: 09/27/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- ci-entities
- ci-relationships
- ci-activities
- ci-activities-wizard
- ci-measures
- ci-segments
- ci-segment-builder
- ci-measure-builder
- ci-measure-template
- ci-permissions
- customerInsights
ms.openlocfilehash: a7b10d985d5cba64b25595a3d7c101d6cb5c62a5
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642871"
---
# <a name="relationships-between-entities"></a>Olemitevaheline seos

Seosed ühendavad olemid ja määratlevad teie andmete graafiku, kui olemitel on ühine identifikaator (võõrvõti). Seda võtit saab viidata ühest olemist teise. Ühendatud olemid võimaldavad määratleda segmente ja mõõte mitmete andmeallikate alusel.

Seoseid on kolme tüüpi: 
- Mitteredigeeritavad süsteemiseosed, mille süsteem on loonud andmete ühendamise protsessi osana
- Mitteredigeeritavad päritud seosed, mis luuakse andmeallikatest automaatselt 
- Redigeeritavad kohandatud seosed, mille on loonud ja konfigureerinud kasutajad

## <a name="non-editable-system-relationships"></a>Mitteredigeeritavad süsteemiseosed

Andmete ühendamisel luuakse süsteemiseosed intelligentse ühendamise põhjal automaatselt. Need seosed aitavad seostada kliendiprofiili kirjeid vastavate kirjetega. Järgmisel diagrammil on esitatud kolm süsteemipõhist seost. Ühtse olemi *Klient* loomiseks sobitatakse kliendiüksus teiste üksustega.

:::image type="content" source="media/relationships-entities-merge.png" alt-text="Diagramm kolme 1-n-seosega kliendiolemi seoseteega;":::

- ***CustomerToContact* seos** loodi *kliendi* olemi ja *kontakti* olemi vahel. *Kliendi* olem saab võtme välja **Contact_contactID**, et olla seotud *kontakti* olemi võtme väljaga **contactID**.
- ***CustomerToAccount* seos** loodi *kliendi* olemi ja *konto* olemi vahel. *Kliendi* olem saab võtme välja **Account_accountID**, et olla seotud *konto* olemi võtme väljaga **accountID**.
- ***CustomerToWebAccount* seos** loodi *kliendi* olemi ja *veebikonto* olemi vahel. *Kliendi* olem saab võtme välja **WebAccount_webaccountID**, et olla seotud *veebikonto* olemi võtme väljaga **webaccountID**.

## <a name="non-editable-inherited-relationships"></a>Mitteredigeeritavad pärilikud suhted

Andmete kogumisprotsessi ajal kontrollib süsteem andmeallikaid olemasolevate seoste suhtes. Kui seost pole olemas, loob süsteem need automaatselt. Neid seoseid kasutatakse ka järgnevas protsessis.

## <a name="create-a-custom-relationship"></a>Kohandatud seose loomine

Seos koosneb *lähteolemist*, mis sisaldab võõrvõtit ja *sihtolemit*, millele lähteolemi võti viitab. 

1. Minge **Andmed** > **Seosed**.

2. Valige **Uus seos**.

3. Sisestage paanil **Uus seos** järgmised andmed.

   :::image type="content" source="media/relationship-add.png" alt-text="Uus tühjade sisestusväljadega seosepoolne paan.":::

   - **Seose nimi**: nimi, mis kajastab seose eesmärki. Näide: CustomerToSupportCase.
   - **Kirjeldus**: seose kirjeldus.
   - **Lähteolem**: olem, mida kasutatakse seoses lähteolemina. Näide: SupportCase.
   - **Sihtolem**: olem, mida kasutatakse seoses sihtolemina. Näide: klient.
   - **Allika kardinaalsus**: lähteallika kardinaalsuse määratlemiseks. Kardiaalsus kirjeldab määratud elemendi võimalike elementide arvu. See on alati seotud sihtkardiaalsusega. Saate valida **ühe** ja **mitme**. Toetatakse vaid mitu-ühele ja üks-ühele seoseid.  
     - Mitu-ühele: mitu lähtekirjet võivad olla seotud ühe sihtkirjega. Näide: üksiku kliendi mitu tugiteenusejuhtumeid.
     - Üks-ühele: üks lähtekirje on seotud ühe sihtkirjega. Näide: üks püsikliendi ID ühele kliendile.

     > [!NOTE]
     > Mitu-mitmele seoseid saab luua kahe mitu-ühele seose ning linkiva olemi abil, mis seob lähte- ja sihtolemi.

   - **Sihtkardinaalsus**: valige sihtolemi kirjete kardinaalsus. 
   - **Lähtevõtme väli**: lähteolemi võõrvõtme väli. Näide: SupportCase võib kasutada CaseID-d võõrvõtme väljana.
   - **Sihtvõtme väli**: sihtolemi võtme väli. Näiteks võib klient kasutada võtmevälja **CustomerID**.

4. Kohandatud seose loomiseks valige **Salvesta**.

## <a name="set-up-account-hierarchies"></a>Seadistage konto hierarhiad

Keskkondades, mis on konfigureeritud kasutama ärikontosid peamise sihtrühmana, saavad konfigureerida seostuvate ärikontode hierarhiaid. Näiteks ettevõte, kus on eraldi äriüksused. 

Asutused ja organisatsioonid loovad ettevõttehierarhiaid, et ettevõtteid ja nende suhteid üksteisega paremini hallata. Customer Insights toetab ema-tütarkonto hierarhiaid, mis on allaneelatud kliendiandmetes juba olemas. Näiteks ettevõtted rakendusest Dynamics 365 Sales. Neid hierarhiaid saab konfigureerida lehel **Seosed**.

1. Minge **Andmed** > **Seosed**.
1. Valige **Konto hierarhia** vahekaart.
1. Valige **Uus konto hierarhia**. 
1. Sisestage **Konto hierarhia** paanil hierarhiale nimi. Süsteem loob väljundolemile nime. Saate muuta väljundi nime olemit.
1. Valige olem, mis sisaldab teie konto hierarhiat. Tavaliselt on see samas olemis, mis sisaldab kontosid.
1. Valige valitud olemist **Konto ID** ja **Konto peamine ID** 
1. Sätete rakendamiseks ja kontohierarhia lõplikuks muutmiseks valige käsk **Salvesta**.

## <a name="view-relationships"></a>Kuva seosed

Lehel Seosed kuvatakse kõik loodud seosed. Iga rida tähistab suhet, mis sisaldab ka üksikasju lähte-, sihtüksuse ja kardinaalsuse kohta. 

:::image type="content" source="media/relationships-list.png" alt-text="Seoste ja suvandite loend lehe Seosed toiminguribal.":::

Sellel lehel on olemasolevate ja uute seoste suvandid. 
- **Uus seos**: [kohandatud seose loomine](#create-a-custom-relationship).
- **Visualiseerija**: [tutvuge seose visualiseerijaga](#explore-the-relationship-visualizer), et näha olemasolevate seoste võrgudiagrammi ja nende kardiaalsust.
- **Filtreerimisalus**: valige loendis kuvamisseoste tüüp.
- **Otsinguseosed**: kasutage tekstipõhist otsingut seoste atribuutide põhjal.

### <a name="explore-the-relationship-visualizer"></a>Tutvuge seose visualiseerijaga

Seose visualiseerija näitab ühendatud üksuste vaheliste olemasolevate suhete ja nende kardinaalsuse skeemi. Selles visualiseeritakse ka seoseteed.

Vaate kohandamiseks saate muuta kastide asukohta, lohistades neid lõuendil.

:::image type="content" source="media/relationship-visualizer.png" alt-text="Kuvatõmmis seose visualiseerija võrgudiagrammist, mis on seotud olemite vaheliste ühendustega.":::

Saadaolevad suvandid: 
- **Ekspordi pildina**: praeguse vaate salvestamine pildifailina.
- **Muuda horisontaal-/vertikaalseks paigutuseks**: muutke olemite ja seoste joondust.
- **Redigeeri**: redigeerige kohandatud seoste atribuute redigeerimispaanil ja salvestage muudatused.

## <a name="relationship-paths"></a>Seose teed

Seose tee kirjeldab olemeid, mis on seotud lähteolemi ja sihtolemi vaheliste seostega. Seda kasutatakse segmendi või meetme loomisel, mis hõlmab muid üksusi peale ühendatud profiili olemi ja ühendatud profiili olemini jõudmiseks on mitu võimalust. 

Seosetee annab süsteemile teada, millistele seostele ühendatud profiiliolemis juurde pääseda. Erinevad seoseteed võivad anda erinevaid tulemusi.

Olemil *eCommerce_eCommercePurchases* on olemiga *Klient* järgmised seosed.

- eCommerce_eCommercePurchases > Klient
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > Klient
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > Klient 

Seosetee määratleb, milliseid olemeid saate kasutada mõõtmise reeglite loomiseks või segmentidena. Pikima seoseteega valiku tegemine annab tõenäoliselt vähem tulemusi, kuna vastavad kirjed peavad olema osa kõigist olemitest. Selles näites peab klient ostma kaupu e-poe kaudu (eCommerce_eCommercePurchases), müügikohas (POS_posPurchases) ja osalema meie lojaalsusprogrammis (loyaltyScheme_loyCustomers). Kui valite esimese võimaluse, saate tõenäoliselt rohkem tulemusi, sest kliendid peavad eksisteerima vaid ühes lisaolemis.

### <a name="direct-relationship"></a>Otsene seos

Seos liigitatakse **otsese seosena** kui allika olem suhestub sihtolemiga vaid ühe seosega.

Näiteks kui tegevuseost nimega *eCommerce_eCommercePurchases* loob ühenduse sihtolemiga *eeCommerce_eCommerceContacts*  *Contactld* kaudu, on see otsene seos.

:::image type="content" source="media/direct_Relationship.png" alt-text="Lähteolem loob ühenduse otse sihtolemiga.":::

#### <a name="multi-path-relationship"></a>Mitme teega seos

**Mitme teega seos** on eri tüüpi otsene seos, mis ühendab lähteolemi mitme sihtolemiga.

Näiteks kui tegevusolem nimega *eCommerce_eCommercePurchases* on seotud kahe sihtolemiga mõlemad nii *eCommerce_eCommerceContacts* kui ka *loyaltyScheme_loyCustomers* on see mitme tee seos.

:::image type="content" source="media/multi-path_relationship.png" alt-text="Lähteolem loob mitme hüppega seose kaudu otse ühenduse rohkem kui ühe sihtolemiga.":::

### <a name="indirect-relationship"></a>Kaudne seos

Seos liigitatakse **kaudse seosena** kui allika olem suhestub ühe või rohkema lisaolemiga enne sihtolemiga seostumist.

#### <a name="multi-hop-relationship"></a>Mitme hüppega seos

*Mitme hüppega seos* on *kaudne seos* , mis lubab sul ühenduda allikaolemi sihtolemiga ühe või rohkema vahendava olemi kaudu.

Näiteks kui tegevusolem nimega *eCommerce_eCommercePurchasesWest* loob ühenduse vahendava olemiga nimega *eCommerce_eCommercePurchasesEast* ja siis ühendub sihtolemiga nimega *eCommerce_eCommerceContacts*, on see mitme hüppega seos.

:::image type="content" source="media/multi-hop_relationship.png" alt-text="Lähteolem loob ühenduse otse sihtolemiga koos vahendava olemiga.":::

### <a name="multi-hop-multi-path-relationship"></a>Mitme hüppe ja teega seos

Mitmehüppega ja mitme teega seoseid saab kasutada koos mitme **mitme hüppega mitme teega seoste** loomiseks. See eritüüp koondab **mitme hüppega** ja **mitme teega** seoste funktsioonid. See võimaldab luua ühenduse rohkem kui ühe sihtolemiga, kasutades subjektiksolemeid.

Näiteks kui tegevusolem nimega *eCommerce_eCommercePurchasesWest* loob ühenduse vahendava olemiga nimega *eCommerce_eCommercePurchasesEast* ja siis ühendub kahe sihtolemiga nimega *eCommerce_eCommerceContacts* ja *loyaltyScheme_loyCustomers* on see mitme hüppega seos.

:::image type="content" source="media/multi-hop_multi-path_relationship.png" alt-text="Lähteolem loob ühenduse otse ühe sihtolemiga ja loob ühenduse mõne muu sihtolemiga vahendava olemi kaudu.":::

## <a name="manage-existing-relationships"></a>Olemasolevate seoste haldamine 

Lehel Seosed tähistab iga seost rida. 

Valige seos ja üks järgmistest suvanditest: 
 
- **Redigeeri**: redigeerige kohandatud seoste atribuute redigeerimispaanil ja salvestage muudatused.
- **Kustutamine**: kohandatud seoste kustutamine.
- **Kuvamine**: saate vaadata süsteemi loodud ja päritud seoseid. 

## <a name="next-step"></a>Järgmine etapp

Süsteemi- ja kohandatud seoseid kasutatakse mitme andmeallika põhjal [segmentide](segments.md) ja [mõõdikute](measures.md) loomiseks, mida enam ei kasutata.

[!INCLUDE [footer-include](includes/footer-banner.md)]
