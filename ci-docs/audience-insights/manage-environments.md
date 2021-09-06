---
title: Keskkondade loomine ja haldamine
description: Siit leiate teavet selle kohta, kuidas teenuse kasutamiseks registreeruda ja kuidas keskkondasid hallata.
ms.date: 07/22/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: e3f99f8f151aea5f120084382babd5e46e109545a4f63aafc51c3ecb1400cc33
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034172"
---
# <a name="manage-environments"></a>Keskkondade haldamine

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

## <a name="switch-environments"></a>Vaheta keskkondasid

Keskkondade vahetamiseks valige juhtelement **Keskkond** lehe paremas ülanurgas.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Juhtelemendi kuvatõmmis keskkondade vahetamiseks.":::

Halduskeskused saavad keskkondi [luua](get-started-paid.md) ja hallata.

## <a name="edit-an-existing-environment"></a>Olemasoleva keskkonna redigeerimine

Saate muuta olemasolevate keskkondade teatud üksikasju.

1.  Valige rakenduse päises valija **Environment** (Keskkond).

2.  Valige ikoon **Edit** (Redigeeri).

3. Väljal **Edit environment** (Redigeeri keskkonda) saate värskendada keskkonna välja **Display name** (Kuva nimi), kuid te ei saa muuta suvandeid **Region** (Regioon) või **Type** (Tüüp).

4. Kui keskkond on konfigureeritud andmeid talletama Azure Data Lake Storage, saate värskendada **Konto võtit**. Kuid te ei saa muuta **Ettevõtte nime** ja **Konteineri** nime.

5. Soovi korral saate konto võtmepõhiselt ühendada ressursipõhise või tellimuspõhise ühendusega. Pärast selle tegemist ei saa te värskenduse järel hakata uuesti kontovõtit kasutama. Lisateavet leiate teemast [Sihtrühmaülevaadete ühendamine Azure Data Lake Storage Gen2 kontoga Azure'i teenusesubjekti kaudu](connect-service-principal.md). Ühenduse värskendamisel ei saa te muuta **konteineri** teavet.

6. Lisaks võite ka luua Microsoft Dataverse keskkonna URL-i jaotises **Andmete jagamise konfigureerimine Microsoft Dataverse ja täiendavate võimaluste lubamine**. Need võimalused hõlmavad andmete jagamist rakendustega ja lahendusi, mis põhinevad Microsoft Dataverse, andmete sisestamist kohapealsetest andmeallikatest või [prognoosimist](predictions.md). Valige suvand **Luba andmete ühiskasutus**, et jagada Customer Insights väljundandmeid Microsoft Dataverse hallatava Data Lake'iga.

   > [!NOTE]
   > - Andmete jagamine rakendusega Microsoft Dataverse Managed Data Lake täna ei toetata, kui salvestate kõik andmed enda andmejärve Azure Data Lake Storage.
   > - [Puuduvate väärtuste prognoos mistahes üksuses](predictions.md) ja PowerBI Embedded aruanded sihtrühma ülevaadetes (kui need on teie keskkonnas lubatud) ei ole hetkel toetatud kui võimaldate andmete ühiskasutuse Microsoft Dataverse -i hakkatud data lake -ga.

   Pärast andmete jagamise lubamist teenusega Microsoft Dataverse, käivitatakse ühekordne täielik andmeallikate ja muude protsesside värskendamine. Kui protsessid praegu töötavad,, ei näe te suvandit andmete Microsoft Dataverse ühiskasutuse lubamiseks. Oodake, kuni need protsessid lõpetavad või tühistada need andmete jagamise lubamiseks. 
   
   :::image type="content" source="media/datasharing-with-DataverseMDL.png" alt-text="Konfigureerimissuvandid andmete jagamise lubamiseks Microsoft Dataverse abil.":::
   
   Protsesside käitamisel, näiteks andmete valmendamisel või segmendi loomisel, luuakse asjaomased kaustad eespool määratud salvestuskontol. Sõltuvalt käitatud protsessist luuakse andmefailid ja model.json-failid ning lisatakse need vastavatelsse alamkaustadesse.

## <a name="copy-the-environment-configuration"></a>Kopeerige keskkonna konfiguratsioon

Uue keskkonna loomisel saate konfiguratsiooni kopeerida olemasolevast keskkonnast. 

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Kuvatõmmis suvandisätetest keskkonnasätetes.":::

Näete teie ettevõtte kõigi saadaolevate keskkondade loendit, kust saate andmeid kopeerida.

Kopeeritakse järgmised konfiguratsioonisätted.

- Valmendatud/imporditud andmeallikad
- Andmete ühtlustamiskonfiguratsioon (kaardistamine, vastendamine, ühendamine)
- Segmendid
- Meetmed
- Seosed
- Tegevused 
- Otsingu ja filtri register
- Ekspordisihtkohad
- Ajastatud värskendamine
- Rikastamised
- Mudeli haldus
- Rolli määramised

Järgnevaid andmeid *ei* kopeerita:

- Kliendiprofiilid.
- Andmeallika identimisteave. Peate sisestama identimisteabe iga andmeallika jaoks ja värskendama andmeallikaid käsitsi.
- Andmeallikad Common Data Model kaustast ja Dataverse hallatavast Data Lake'st. Peate need andmeallikad looma käsitsi sama nimega kui lähtekeskkond.

Keskkonna kopeerimisel näete kinnitusteadet, et loodi uus keskkond. Andmeallikate loendi nägemiseks valige suvand **Ava andmeallikad**.

Kõik andmeallikad kuvavad olekut **Mandaat nõutav**. Redigeerige andmeallikaid ja sisestage nende värskendamiseks identimisteave.

:::image type="content" source="media/data-sources-copied.png" alt-text="Kopeeritud ja autentimist vajav andmeallikate loend.":::

Pärast andmeallikate värskendamist avage jaotis **Andme** > **Ühendamine**. Siit leiate lähtekeskkonna sätted. Redigeerige neid vastavalt vajadusele või valige **Käivita**, et käivitada andmete ühendamise protsess ja luua ühtne kliendi olem.

Kui andmete ühendamine on lõpetatud, avage **Meetmed** ja **Segmendid**, et neid samuti värskendada.

## <a name="reset-an-existing-environment"></a>Olemasoleva keskkonna lähtestamine

Kui soovite kustutada kõik konfiguratsioonid ja eemaldada valmendatud andmed, saate keskkonna lähtestada nii, et see oleks täiesti tühi.

1.  Valige rakenduse päises valija **Environment** (Keskkond). 

2.  Valige keskkond, mille soovite lähtestada, ja valige ellips (**...**). 

3. Valige suvand **Reset** (Lähtesta). 

4.  Kustutamise kinnitamiseks sisestage keskkonna nimi ja valige **Lähtesta**.

## <a name="delete-an-existing-environment"></a>Olemasoleva keskkonna kustutamine

Administraatorina saate kustutada halduskeskkonna.

1.  Valige rakenduse päises valija **Environment** (Keskkond).

2.  Valige keskkond, mille soovite lähtestada, ja valige ellips (**...**). 

3. Valige suvand **Delete** (Kustuta). 

4.  Kustutamise kinnitamiseks sisestage soovitud keskkonna nimi ja valige **Kustuta**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
