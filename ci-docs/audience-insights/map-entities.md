---
title: Andmete ühendamise olemite ja atribuutide vastendamine
description: Valige olemid, atribuudid, peamised võtmed ja semantilised tüübid andmete vastendamiseks ühendatud kliendiprofiiliga.
ms.date: 10/18/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-map
ms.openlocfilehash: 8b84ed1a860e383e4eb3f7499be6d397ba3f1db1
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673258"
---
# <a name="map-entities-and-attributes"></a>Olemite ja atribuutide kaardistamine

**Vastendamine** on sihtrühmaülevaadetes andmete koondamise protsessi esimene etapp. Vastendamine koosneb kolmest etapist.

- *Olemi valik*: tuvastage ühendatavad olemid, mis suunavad andmekogumile, mis sisaldab teie klientide kohta täpsemat teavet.
- *Atribuudi valimine*: määrake iga olemi puhul veerud, mida soovite kombineerida ja sobitada etappides *vastendamine* ja *liitmine*. Neid veerge nimetatakse *atribuutideks*.
- *Primaarvõtme ja semantilise tüübi valik*: tuvastage iga olemi jaoks atribuut, mille soovite määrata selle olemi jaoks primaarvõtmena, ja iga atribuudi jaoks määratlege semantiline tüüp, mis kirjeldab seda atribuuti kõige paremini.

Lisateavet andmete ühendamise üldvoo kohta vt [Ühenda](data-unification.md).

## <a name="select-the-first-entities"></a>Valige esimesed olemid

1. Avage sihtrühmaülevaadetes jaotis **Andmed** > **Koondamine** > **Vastendamine**.

2. Kaardistamise etapi käivitamiseks valige **Vali olemid**.

3. Valige olemid ja atribuudid, mida soovite etappides *vastendamine* ja *ühendamine* kasutada. Saate valida vajalikud atribuudid olemis individuaalselt või lisada olemist kõik atribuudid, valides olemi tasandil märkeruudu **Kaasa kõik väljas**. Andmete ühendamisest kasu saamiseks soovitame valida vähemalt kaks olemit.

   > [!div class="mx-imgBorder"]
   > ![Lisa olemite näide.](media/data-manager-configure-map-add-entities-example.png "Lisa olemite näide")

   Selles näites lisame olemid **eCommerceContacts** ja **loyCustomers**. Nende olemite valimisel saate tuletada ülevaateid, kus veebikliendid on püsikliendiprogrammi liikmed.
   
   Saate otsida atribuutide ja olemite üleselt märksõnu, et valida vajalikud atribuudid, mida soovite vastendada.
   
     > [!div class="mx-imgBorder"]
   > ![Otsinguväljade näide.](media/data-manager-configure-map-search-fields-example.png "Otsinguväljade näide")

4. Oma valikute kinnitamiseks valige suvand **Rakenda**.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Atribuutide primaarvõtme ja semantilise tüübi valimine

Pärast oma olemite valimist loetleb leht **Kaardistamine** läbivaatamiseks valitud olemid. Määratlege olemi primaarvõti ja määratlege olemi atribuudi semantiline tüüp.

- **Primaarvõti**: valige iga olemi primaarvõtmeks üks atribuut. Et atribuut saaks olla sobiv primaarvõti, ei tohi see sisaldada topeltväärtusi, puuduvaid väärtusi ega null-väärtusi. Stringi, täisarvu ja GUID-i andmetüübi atribuute toetatakse primaarvõtmetena ja need kuvatakse väljal, kust saate need valida.

- **Atribuudi semantiline tüüp**: atribuutide kategooriad (nt e-posti aadress või nimi). Selleks et kasutada AI mudeleid semantika nutikaks prognoosiks, säästa aega ja parandada täpsust, määrake suvandi **Intelligentne vastendamine** olekuks **SEES**. Intelligentne vastendamine tõstab esile AI-põhise semantika soovituse väljal **Tüüp**. Kui määrate selle olekuks **VÄLJAS**, näete meie tavalisi vastendamise soovitusi. Saate valida saadaolevate suvandite loendist mis tahes semantilise tüübi ja tühistada soovitatud valiku.

> [!div class="mx-imgBorder"]
> ![Atribuudi tüüp ja semantiline prognoos.](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Atribuudi tüüp ja semantiline prognoos")

Samuti on võimalik lisada enda loodud semantiline tüüp. Valige atribuudi tüübi väärtus ja sisestage enda muudetud semantilise tüübi nimi. Nii saate muuta ka süsteemi tuvastatud atribuudi tüüpe.

Kõik atribuudid, mille semantiline tüüp tuvastatakse automaatselt, on rühmitatud jaotises **Vastendatud väljade läbivaatamine**. Vaadake need atribuudid ja nende semantilised tüübid läbi, kuna neid kasutatakse teie olemite kombineerimiseks andmete ühendamise ühendamise etapis.

Atribuudid, mida semantilise tüübiga automaatselt ei vastendata, on rühmitatud jaotises **Vastendamata väljade andmete määratlemine**. Valige vastendamata atribuutide jaoks välja semantiline tüüp või sisestage kohandatud atribuudi tüübi nimi.

> [!div class="mx-imgBorder"]
> ![Primaarvõti ja atribuudi tüüp.](media/data-manager-configure-map-add-attributes.png "Primaarvõti ja atribuudi tüüp")

> [!NOTE]
> Üks väli peaks olema vastendatud semantilise tüübiga Person.FullName, et lisada kliendi kaardile kliendi nimi. Vastasel juhul kuvatakse kliendikaardid ilma nimeta. 

## <a name="add-and-remove-attributes-and-entities"></a>Atribuutide ja olemite lisamine ja eemaldamine

1. Suvandis **Ühendamine** > **Kaardistamine** valige **Redigeeri välju**.

2. Lisage või eemaldage atribuute ja olemeid paanil **Redigeeri välju**. Kasutage otsingut või kerige, et leida ja valida teile huvi pakkuvad atribuudid ja olemid. Atribuuti või olemit ei saa eemaldada, kui need on juba vastendatud.

   > [!div class="mx-imgBorder"]
   > ![Atribuutide lisamine või eemaldamine.](media/configure-data-map-edit.png "Atribuutide lisamine või eemaldamine")

3. Valige suvand **Rakenda**.

## <a name="add-images-to-profiles"></a>Profiilidele pildi lisamine

Kui olem sisaldab avalikult saadaolevate profiilipiltidele või logode URL-e, saate need ühendatud kliendiprofiilile lisada.

Valige olem ja otsige üles väli, mis sisaldab profiilipildi URL-i. Sisestage sisendiväljale **Tüüp** käsitsi järgmine väärtus. 
- Isiku korral: Person.ProfileImage
- Organisatsiooni korral: Organization.LogoImage

Jätkake ühendamise sammudega ja veenduge, et pildi URL-i sisaldav atribuut lisatakse samuti etapis [Ühendamine](merge-entities.md).

## <a name="set-attributes-for-organizations"></a>Atribuutide määramine ettevõtetele

Organisatsiooni (eelversioon) atribuudi tüüp tuleks vastendada järgmiselt: „organisatsioon.nimi“
> [!div class="mx-imgBorder"]
> ![Primaarvõti ja atribuuditüüp B2B.](media/configure-data-map-edit-b2b.png "Primaarvõti ja atribuuditüüp B2B")

## <a name="next-step"></a>Järgmine etapp

Andmete ühendamisel minge lehele **Vastenda**. Külastage lehte [**Vastendamine**](match-entities.md), et saada rohkem teavet selle etapi kohta.

> [!TIP]
> Vaadake seda videot: [Alustamine: kliendi koondprofiili loomine](https://youtu.be/oBfGEhucAxs).


[!INCLUDE[footer-include](../includes/footer-banner.md)]