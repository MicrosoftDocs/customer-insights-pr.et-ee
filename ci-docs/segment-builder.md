---
title: Looge segmente segmendikoosturiga
description: Looge klientide segmente, et rühmitada neid vastavalt eri atribuutidele.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segments
- ci-segment-builder
- ci-segment-details
- customerInsights
ms.openlocfilehash: c8e9e4976ade36c1c3c4f688a667b329bfde6e3e
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642760"
---
# <a name="create-segments"></a>Segmentide loomine

Määratlege keerukad filtrid ühendatud kliendiolemi ümber ja sellega seotud olemid. Pärast töötlemist loob iga segment hulga kliendi kirjeid, mille saate eksportida ja nendega toiminguid teha. Segmente saab hallata lehel **Segmendid**. Saate luua [uusi segmente](#create-a-new-segment) kasutades segmendikoosturit või [luua kiirsegmente](#quick-segments) rakenduse muudelt aladelt.

> [!TIP]
> - Kiirsegmente toetatakse ainult **üksikklientide** keskkondades.
> - **Üksikklientidel** põhinevad segmendid sisaldavad automaatselt segmendi liikmete jaoks saadaolevat kontaktteavet. **Ärikontode** keskkondades põhinevad segmendid kontodel (ettevõtetel või tütarettevõtetel). Kontaktteabe kaasamiseks segmenti kasutage segmendi meisterdamisfunktsiooni **Projekti atribuudid**. Veenduge, et kontakti andmeallikad oleks [semantselt vastendatud olemiga ContactProfile](semantic-mappings.md#define-a-contactprofile-semantic-entity-mapping).

## <a name="segment-builder"></a>Segmentide koostamine

Järgmine pilt illustreerib segmendikoosturi erinevaid aspekte. Sellel kuvatakse segment, mille tulemuseks on klientide rühm. Kliendid tellisid kaupa kindla aja jooksul ja kogusid punkte või kulutasid teatud rahasumma.

:::image type="content" source="media/segment-builder-overview.png" alt-text="Segmendi ehitaja elemendid." lightbox="media/segment-builder-overview.png":::

1. Korraldage oma segment reeglite ja alamreeglitega. Iga reegel või alamreegel koosneb tingimustest. Tingimuste ühendamine loogikatehtetega

1. Valige reeglile rakenduvate olemite vaheline [seosetee](relationships.md). Seosetee määratleb, milliseid atribuute saab tingimuses kasutada.

1. Reeglite ja alamreeglite haldamine. Saate muuta reegli positsiooni või selle kustutada.

1. Lisage alamreeglite abil tingimused ja looge õige hargnemine alamreeglite abil.

1. Saate rakendada ühendatud reeglitele salvestatud toiminguid.

1. Kasutage atribuudipaani, et lisada saadaolevaid olemiatribuute või luua atribuutidel põhinevad tingimused. Paanil kuvatakse valitud seoseteel põhinevate olemite ja atribuutide loend, mis on valitud reegli jaoks saadaval.

1. Lisage olemasolevatele reeglitele ja alamreeglitele atribuutidel põhinevad tingimused või lisage see uude reeglisse.

1. Saate segmendi loomise ajal muudatusi tagasi võtta ja uuesti teha.

Ülaltoodud näites on kirjeldatud segmentimisvõimalust. Oleme määratlenud segmenti klientidele, kes koguvad vähemalt $500 veebikaupu *ja* on huvitatud tarkvara arendamisest.

## <a name="create-a-new-segment"></a>Looge uus segment

Uue segmendi loomiseks on mitu võimalust. Selles jaotises kirjeldatakse, kuidas luua oma segmenti tühjalt lehelt. Samuti saate luua olemasolevatel olemitel põhineva *kiirsegmendi* või kasutada Masinõpe mudeleid et saada *soovitatud segmente*. Lisateabe saamiseks minge [Segmentide ülevaade](segments.md).

Segmenti luues saate mustandi salvestada. Mustandetapis salvestatakse segment passiivse segmendina. Kui olete segmendi konfiguratsiooni lõpule viinud, käivitage see segmenti aktiveerimiseks. Võite segmendi ka **Aktiveerida** lehelt **Kõik segmendid**.

1. Minge lehele **Segmendid**.

1. Valige **Uus** > **Ehita enda oma**.

1. Segmendi osade lehel saate määratleda või koostada reegleid. Reegel koosneb ühest või mitmest tingimusest mis määratleb klientide komplekti.

1. **Valige jaotises Reegel1** selle olemi atribuut, mille järgi soovite kliente filtreerida. Atribuutide valimiseks on kaks viisi.
   - Vaadake paanil **Lisa reeglile** saadaolevad olemid ja atribuudid läbi ja valige lisamisatribuudi kõrval soovitud **+** ikoon. Valige, kas soovite lisada atribuudi olemasolevale reeglile või kasutada seda uue reegli loomiseks.
   - Kui soovite näha kattuvate soovituste kuvamist, tippige atribuudi nimi reegli jaotisesse.

1. Valige tingimuse kattuvate väärtuste määramiseks tehtemärgid. Atribuudil võib olla üks neljast andmetüübist: arv, string, kuupäev või tõeväärtus. Sõltuvalt atribuudi andmetüübist on tingimuse määramiseks saadaval erinevad tehtemärgid. Ärikontodega segmentide puhul on saadaval kaks eritehtet, et kaasata allaneetud ettevõtete potentsiaalsed hierarhiad. Kasutage seotud kontode kaasamiseks tehteid *laps* ja *vanem*.

1. Kui soovite reeglile lisada veel tingimusi, valige **Lisa tingimus**. Praeguse reegli alla reegli loomiseks valige käsk **Lisa alamreegel**.

1. Kui reegel kasutab muid olemeid kui olem *Klient*, peate seosetee seadistama. Seosetee peab teavitama süsteemi, millistel suhetel tahate juurdepääsu ühendatud kliendi profiili olemile. Valige valitud olemi vastendamiseks ühendatud kliendiolemiga **Määra seosetee**. Kui on ainult üks võimalik seosetee, valib süsteem selle automaatselt. Erinevad seoseteed võivad anda erinevaid tulemusi. Igal reeglil võib olla oma seosetee.

   :::image type="content" source="media/relationship-path.png" alt-text="Potentsiaalne seosetee ühtse kliendiolemiga vastendatud olemil põhineva reegli loomisel.":::

   Näiteks on kuvatõmmisel oleval olemil *eCommerce_eCommercePurchases* olemiga *Klient* neli võimalust vastendamiseks.
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > Klient
   - eCommerce_eCommercePurchases > Klient
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > Klient
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > Klient Viimase suvandi valimisel võime kaasata reeglitingimustesse kõigi loetletud olemite atribuudid. Tõenäoliselt saame vähem tulemusi, kuna kattuvad kliendikirjed peavad olema kõigi olemite osa. Selles näites peavad nad ostma kaupu e-poe kaudu (*eCommerce_eCommercePurchases*), müügikohas (*POS_posPurchases*) ja osalema meie lojaalsusprogrammis (*loyaltyScheme_loyCustomers*). Teise suvandi valimisel saame valida atribuute ainult olemist *eCommerce_eCommercePurchases* ja *kliendi* olemi atribuute. Selle tulemuseks on tõenäoliselt rohkem saadud kliendiprofiile.

1. Kui reeglis on mitu tingimust, saate valida, milline loogiline tehtemärk neid ühendab.  
   - **JA** tehtemärk: kirje segmenti kaasamiseks peavad olema täidetud kõik tingimused. See valik on kõige kasulikum juhul, kui määratlete eri olemite tingimusi.
   - **VÕI** tehtemärk: kirje segmenti kaasamiseks peab olema täidetud üks tingimustest. See valik on kõige kasulikum juhul, kui määratlete sama olemi mitu tingimusi.

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="Reegel kahe JA tingimustega.":::

   VÕI tehtemärki kasutades peavad kõik tingimused põhinema seoseteel kaasatud olemitel.

   - Kliendikirjete erinevate kogumite loomiseks saate luua mitu reeglit. Saate ühendada rühmad, et kaasata teie ärijuhtumi jaoks nõutavad kliendid. Uue reegli loomiseks valige **Lisa reegel**. Täpsemalt kui te ei saa määratud seosetee tõttu reeglisse lisada ega olemit lisada, peate looma uue reegli, et valida atribuutide vorm.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Lisage segmendile uus reegel ja valige seatud tehtemärk.":::

   - Valige üks tehingukomplekt: **Liit**, **Lõikuv** või **Välja arvatud**.

      - **ühend** ühendab kaks rühma.
      - **Ühisosa** kattub kahe rühmaga. Ühtsesse rühma jäävad ainult need andmed, mis on mõlema rühma jaoks *ühised*.
      - **Välja arvatud** kombineerib kaks rühma. Säilitatakse ainult rühma A andmed, mis *ei ole ühised* rühma B andmetele.

1. Vaikimisi genereerivad segmendid väljundolemi, mis sisaldab kõiki määratletud filtritele vastavaid kliendiprofiilide atribuute. Kui segment põhineb muudel olemitel kui olem *Klient*, saate väljundolendisse lisada rohkem atribuute nendest olemitest. Valige **Projekti tribuudid**, et valida väljundolemile lisatavad atribuudid.

   > [!IMPORTANT]
   > Ärikontodel põhinevate segmentide puhul tuleb iga ettevõtte ühe või mitme kontakti üksikasjad *ContactProfile* olemist kaasata segmenti, et see segment oleks aktiveeritud või eksporditud kaasamiskohaks, mis nõuab kontaktteavet. Olemi *ContactProfile* kohta leiate lisateavet teemast [Semantilised vastendused](semantic-mappings.md).
   > Kontaktide prognoositud atribuutidega ärikontodel põhineva segmendi näidisväljund võiks välja näha järgmine:
   >
   > |ID  |Konto nimi  |Tulu  |Kontaktisiku nimi  | Kontakti roll|
   > |---------|---------|---------|---------|---|
   > |10021     | Contoso | 100K | [Abbie Moss, Ruth Soto]  | [tegevjuht, hankejuht]

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Näide väljundolemile lisatava küljepaanil valitud projitseeritud atribuutidest.":::
  
   Näiteks: Segment põhineb olemil, mis sisaldab *Kliendi* olemiga seotud ostuandmeid. Segmendis otsitakse kõiki Hispaaniast pärit kliente, kes on praeguse aasta jooksul oma kaupa ostnud. Saate lisada atribuute, nagu kaupade hind, või ostukuupäeva kõigile väljundolemi kattuvatele kliendikirjetele. See teave võib olla kasulik, et analüüsida hooajalist korrelatsiooni kogukuludega.

   > [!NOTE]
   > - **Projektiatribuudid** töötavad ainult olemitele, mille seos kliendiolemiga on üks-mitmele. Näiteks võib ühel kliendil olla mitu tellimust.
   > - Kui atribuut, mida soovite projekti jaoks kasutada, on *Kliendi* olemist rohkem kui ühe hüppe kaugusel, nagu see on seoses määratletud, tuleks seda atribuuti kasutada igas teie ettevõttes kasutatava segmendipäringu reeglis.
   > - Kui atribuut, mida soovite projekti jaoks kasutada, on *Kliendi* olemist ühe hüppe kaugusel, siis seda atribuuti ei pea kasutama igas teie ettevõttes kasutatava segmendipäringu reeglis.
   > - **Prognoositud atribuudid** on seatud teguriks kasutades tehete kogumeid.

1. Valige **Redigeeri üksikasju** välja Pealkirjata segment kõrval. Andke oma segmendile nimi ja värskendage segmendile soovitatud **Väljundolemi nime**. Soovi korral lisage segmendile kirjeldus ja [sildid](work-with-tags-columns.md#manage-tags).

   :::image type="content" source="media/segments_edit_details.png" alt-text="Dialoogiboksi Üksikasjade redigeerimine.":::

1. Valige käsk **Käivita**, et salvestada segment, see aktiveerida ja alustada segmendi töötlemist kõigi reeglite ja tingimuste alusel. Vastasel juhul salvestatakse see passiivse segmendina.

1. Valige **Tagasi segmentidesse**, et naasta lehele **Segmendid**.

1. Vaikimisi luuakse segment dünaamilise segmendina. See tähendab, et segmenti värskendatakse süsteemivärskenduste käigus. [Automaatse värskendamise peatamiseks](segments.md#manage-existing-segments) valige segment ja suvand **Muuda staatiliseks**. Staatilisi segmente saab igal ajal [värskendada ainult käsitsi](segments.md#refresh-segments).

> [!TIP]
> - Segmendi tehtemärgid ei soovita tingimuste jaoks tehtemärkide seadmisel olemite kehtivaid väärtusi. Minge **Andmed** > **Olemid** ja laadige alla olemi andmed, et näha, millised väärtused on saadaval.
> - Kuupäevadel põhinevad tingimused võimaldavad teil vahetada fikseeritud kuupäevade ja ujuva kuupäevavahemiku vahel.
> - Kui teil on oma segmendi jaoks mitu reeglit, on redigeeritud reegli kõrval vertikaalne sinine joon.
> - Reegleid ja tingimusi saate segmendi määratluses teisaldada ka muudesse kohtadesse. Valige reegli või tingimuse kõrval väärtus [...] ja valige, kuidas ja kuhu seda teisaldada.
> - Käsuribal juhtelementide **Võta tagasi** ja **Tee uuesti** abil saate muudatusi tagasi võtta.

## <a name="quick-segments"></a>Kiirsegmendid

Kiirsegmendid lasevad teil luua lihtsaid segmente ühe tehtega kiiresti, et saada kiiremaid ülevaateid.

1. Lehel **Segmendid** klõpsake **Uus** > **Loo vorm**.
   - Valige suvand **Profiilid** etehitada segment, mis põhineb *ühendatud kliendi* olemil.
   - Valige suvand **Mõõtmed**, et luua segment juba loodud mõõtmete ümber.
   - Valige suvand **Ärianalüüs**, et luua segment ümber ühe väljundi olemi, mille olete loonud, kasutades kas **Prognooside** või **Kohandatud mudelite** võimalusi.

2. Valige dialoogiboksis **Uus kiirsegment** atribuut ripploendist **Väli**.

3. Süsteem pakub rohkem ülevaateid, mis aitavad teil luua klientidest paremaid segmente.
   - Kategooria väljade puhul näitame 10 peamist kliendi arvu. Valige **Väärtus** ja **Ülevaatamine**.
   - Süsteem näitab numbrilise atribuudi puhul, mis atribuudi väärtus langeb iga kliendi protsendiili alla. Valige **Tehtemärk**, **Väärtus** ja **Ülevaatamine**.

4. Süsteem esitab **hinnangulise segmendi mahu**. Saate valida, kas luua määratletud segment või esmalt vaadata seda uuesti, et hankida muus mahus segment.

   :::image type="content" source="media/quick-segment-name.png" alt-text="Kiirsegmendi nimi ja hinnang.":::

5. **Esitage oma segmendile nimi** ja **väljundolemi nimi**. Soovi korral lisage [sildid](work-with-tags-columns.md#manage-tags).

6. Segmendi loomiseks valige käsk **Salvesta**.

7. Pärast segmendi töötlust saate seda vaadata nagu kõiki teisi loodud segmente.

## <a name="next-steps"></a>Järgmised etapid

[Eksportige segment](export-destinations.md) ja tutvuge [kliendikaardi integratsiooniga](customer-card-add-in.md), et kasutada segmente muudes rakendustes.

[!INCLUDE [footer-include](includes/footer-banner.md)]
