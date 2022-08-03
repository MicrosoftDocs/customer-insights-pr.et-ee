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
ms.openlocfilehash: e622e5fa0b5738e31db1c668d95312adbc4f7d36
ms.sourcegitcommit: ad74ace653db9a25fce4343adef7db1c9b0d8904
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183549"
---
# <a name="relationships-between-entities-and-entity-paths"></a>Seosed olemite ja olemiteede vahel

Seosed ühendavad olemid ja määratlevad teie andmete graafiku, kui olemitel on ühine identifikaator (võõrvõti). Seda võtit saab viidata ühest olemist teise. Ühendatud olemid võimaldavad määratleda segmente ja mõõte mitmete andmeallikate alusel.

Seoseid on kolme tüüpi: 
- Mitteredigeeritavad süsteemiseosed loob süsteem andmete ühendamise protsessi osana
- Mitteredigeeritavad päritud seosed luuakse andmeallikate allaneelamisest automaatselt
- Redigeeritavaid kohandatud seoseid loovad ja konfigureerivad kasutajad

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
   - **Allika kardinaalsus**: lähteolemi kardinaalsus. Kardiaalsus kirjeldab määratud elemendi võimalike elementide arvu. See on alati seotud sihtkardiaalsusega. Saate valida **ühe** ja **mitme**. Toetatakse vaid mitu-ühele ja üks-ühele seoseid.  
     - Mitu-ühele: mitu lähtekirjet võivad olla seotud ühe sihtkirjega. Näide: üksiku kliendi mitu tugiteenusejuhtumeid.
     - Üks-ühele: üks lähtekirje on seotud ühe sihtkirjega. Näide: üks püsikliendi ID ühele kliendile.

     > [!NOTE]
     > Mitu-mitmele seoseid saab luua kahe mitu-ühele seose ning linkiva olemi abil, mis seob lähte- ja sihtolemi.

   - **Siht-kardinaalsus**: sihtüksuse kirjete kardinaalsus.
   - **Lähtevõtme väli**: võõrvõtme väli lähteolemis. Näide: SupportCase kasutab **võõrvõtmeväljana CaseID-d**.
   - **Sihtvõtmeväli**: sihtüksuse võtmeväli. Näide: klient kasutab **võtmeväljana CustomerID-d**.

4. Kohandatud seose loomiseks valige **Salvesta**.

## <a name="set-up-account-hierarchies"></a>Seadistage konto hierarhiad

Keskkonnad, mis on konfigureeritud kasutama ärikontosid peamise sihtrühmana, saavad konfigureerida seotud ärikontode kontohierarhiaid. Näiteks ettevõte, kus on eraldi äriüksused.

Asutused ja organisatsioonid loovad ettevõttehierarhiaid, et ettevõtteid ja nende suhteid üksteisega paremini hallata. Customer Insights toetab ema-lapse konto hierarhiaid, mis on allaneelatud kliendiandmetes juba olemas. Näiteks ettevõtted rakendusest Dynamics 365 Sales. Neid hierarhiaid saab konfigureerida **lehel Seosed**.

1. Minge **Andmed** > **Seosed**.
1. Valige **Konto hierarhia** vahekaart.
1. Valige **Uus konto hierarhia**.
1. Sisestage **Konto hierarhia** paanil hierarhiale nimi. Süsteem loob väljundolemile nime, kuid saate seda muuta.
1. Valige olem, mis sisaldab teie konto hierarhiat. Tavaliselt on see samas olemis, mis sisaldab kontosid.
1. Valige valitud olemitest **konto UID** ja **emaettevõtte UID**.
1. Kontohierarhia lõpuleviimiseks valige **Salvesta**.

## <a name="manage-existing-relationships"></a>Olemasolevate seoste haldamine

Minge **lehele Seosed**, et vaadata kõiki loodud seoseid, nende lähteolemit, sihtolemit ja kardinaalsust.

:::image type="content" source="media/relationships-list.png" alt-text="Seoste ja suvandite loend lehe Seosed toiminguribal.":::

**Kasutage konkreetse seose leidmiseks suvandeid** Filtreerimisalus **või** Otsi seoseid. Olemasolevate seoste ja nende kardinaalsuse võrguskeemi nägemiseks valige [**Visualizer**](#explore-the-relationship-visualizer).

Valige seos saadaolevate toimingute vaatamiseks.
- **Redigeeri**: redigeerige kohandatud seoste atribuute redigeerimispaanil ja salvestage muudatused.
- **Kustutamine**: kohandatud seoste kustutamine.
- **Kuvamine**: saate vaadata süsteemi loodud ja päritud seoseid.

### <a name="explore-the-relationship-visualizer"></a>Tutvuge seose visualiseerijaga

Seose visualiseerija näitab ühendatud üksuste vaheliste olemasolevate suhete ja nende kardinaalsuse skeemi. Selles visualiseeritakse ka seoseteed.

:::image type="content" source="media/relationship-visualizer.png" alt-text="Kuvatõmmis seose visualiseerija võrgudiagrammist, mis on seotud olemite vaheliste ühendustega.":::

Vaate kohandamiseks saate muuta kastide asukohta, lohistades neid lõuendil. Muud valikud hõlmavad järgmist: 
- **Ekspordi pildina**: praeguse vaate salvestamine pildifailina.
- **Muuda horisontaal-/vertikaalseks paigutuseks**: muutke olemite ja seoste joondust.
- **Redigeeri**: redigeerige kohandatud seoste atribuute redigeerimispaanil ja salvestage muudatused.

## <a name="relationship-paths"></a>Seose teed

Seose tee kirjeldab olemeid, mis on seotud lähteolemi ja sihtolemi vaheliste seostega. Seda kasutatakse segmendi või mõõdu loomisel, mis sisaldab muid olemeid kui ühtse profiili olem, ja ühtse profiili olemini jõudmiseks on mitu võimalust. Erinevad seoseteed võivad anda erinevaid tulemusi.

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

**Mitme hüppega seos** on *kaudne seos* , mis lubab sul ühenduda allikaolemi sihtolemiga ühe või rohkema vahendava olemi kaudu.

Näiteks kui tegevusolem nimega *eCommerce_eCommercePurchasesWest* loob ühenduse vahendava olemiga nimega *eCommerce_eCommercePurchasesEast* ja siis ühendub sihtolemiga nimega *eCommerce_eCommerceContacts*, on see mitme hüppega seos.

:::image type="content" source="media/multi-hop_relationship.png" alt-text="Lähteolem loob ühenduse otse sihtolemiga koos vahendava olemiga.":::

### <a name="multi-hop-multi-path-relationship"></a>Mitme hüppe ja teega seos

Mitmehüppega ja mitme teega seoseid saab kasutada koos mitme **mitme hüppega mitme teega seoste** loomiseks. See eritüüp koondab **mitme hüppega** ja **mitme teega** seoste funktsioonid. See võimaldab luua ühenduse rohkem kui ühe sihtolemiga, kasutades subjektiksolemeid.

Näiteks kui tegevusolem nimega *eCommerce_eCommercePurchasesWest* loob ühenduse vahendava olemiga nimega *eCommerce_eCommercePurchasesEast* ja siis ühendub kahe sihtolemiga nimega *eCommerce_eCommerceContacts* ja *loyaltyScheme_loyCustomers* on see mitme hüppega seos.

:::image type="content" source="media/multi-hop_multi-path_relationship.png" alt-text="Lähteolem loob ühenduse otse ühe sihtolemiga ja loob ühenduse mõne muu sihtolemiga vahendava olemi kaudu.":::

## <a name="next-step"></a>Järgmine etapp

Süsteemi- ja kohandatud seoseid kasutatakse mitme andmeallika põhjal [segmentide](segments.md) ja [mõõdikute](measures.md) loomiseks, mida enam ei kasutata.

[!INCLUDE [footer-include](includes/footer-banner.md)]
