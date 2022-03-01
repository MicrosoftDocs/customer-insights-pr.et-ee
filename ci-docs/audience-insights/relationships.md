---
title: Seosed olemite ja olemiteede vahel
description: Looge ja hallake mitmest andmeallikast pärit olemite vahelisi seoseid.
ms.date: 06/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: d5b9566ec88096fec31d8e164a51598159ec26d4
ms.sourcegitcommit: ece48f80a7b470fb33cd36e3096b4f1e9190433a
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 06/03/2021
ms.locfileid: "6171159"
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

1. Avage sihtrühmaülevaadetes jaotis **Andmed** > **Seosed**.

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

## <a name="view-relationships"></a>Kuva seosed

Lehel Seosed kuvatakse kõik loodud seosed. Iga rida tähistab suhet, mis sisaldab ka üksikasju lähte-, sihtüksuse ja kardinaalsuse kohta. 

:::image type="content" source="media/relationships-list.png" alt-text="Seoste ja suvandite loend lehe Seosed toiminguribal.":::

Sellel lehel on olemasolevate ja uute seoste suvandid. 
- **Uus seos**: [kohandatud seose loomine](#create-a-custom-relationship).
- **Visualiseerija**: [tutvuge seose visualiseerijaga](#explore-the-relationship-visualizer), et näha olemasolevate seoste võrgudiagrammi ja nende kardiaalsust.
- **Filtreerimisalus**: valige loendis kuvamisseoste tüüp.
- **Otsinguseosed**: kasutage tekstipõhist otsingut seoste atribuutide põhjal.

### <a name="explore-the-relationship-visualizer"></a>Tutvuge seose visualiseerijaga

Seose visualiseerija näitab ühendatud üksuste vaheliste olemasolevate suhete ja nende kardinaalsuse skeemi.

Vaate kohandamiseks saate muuta kastide asukohta, lohistades neid lõuendil.

:::image type="content" source="media/relationship-visualizer.png" alt-text="Kuvatõmmis seose visualiseerija võrgudiagrammist, mis on seotud olemite vaheliste ühendustega.":::

Saadaolevad suvandid: 
- **Ekspordi pildina**: praeguse vaate salvestamine pildifailina.
- **Muuda horisontaal-/vertikaalseks paigutuseks**: muutke olemite ja seoste joondust.
- **Redigeeri**: redigeerige kohandatud seoste atribuute redigeerimispaanil ja salvestage muudatused.

## <a name="manage-existing-relationships"></a>Olemasolevate seoste haldamine 

Lehel Seosed tähistab iga seost rida. 

Valige seos ja üks järgmistest suvanditest: 
 
- **Redigeeri**: redigeerige kohandatud seoste atribuute redigeerimispaanil ja salvestage muudatused.
- **Kustutamine**: kohandatud seoste kustutamine.
- **Kuvamine**: saate vaadata süsteemi loodud ja päritud seoseid. 

## <a name="next-step"></a>Järgmine etapp

Süsteemi ja kohandatud seoseid kasutatakse [segmentide loomiseks](segments.md) vastavalt mitte enam eraldatud mitmele andmeallikale.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
