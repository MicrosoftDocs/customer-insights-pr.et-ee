---
title: Keskkondade loomine ja haldamine
description: Siit leiate teavet selle kohta, kuidas teenuse kasutamiseks registreeruda ja kuidas keskkondasid hallata.
ms.date: 06/15/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 904ce68336cba4b7a4d5a37692b72d091400559d
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304875"
---
# <a name="manage-environments"></a>Keskkondade haldamine

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Selles artiklis kirjeldatakse, kuidas luua uut organisatsiooni ja kuidas keskkonda ette valmistada.

## <a name="sign-up-and-create-an-organization"></a>Registreerumine ja organisatsiooni loomine

1. Minge veebisaidile [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/).

2. Seejärel valige suvand **Alustamine**.

3. Valige eelistatud registreerimisstsenaarium ja vastav link.

4. Nõustuge tingimustega ja valige suvand **Edasi**, et alustada organisatsiooni loomisega.

5. Kui keskkond on loodud, suunatakse teid lehele [Customer Insights](https://home.ci.ai.dynamics.com).

6. Saate kasutada demokeskkonda rakendusega tutvumiseks või luua uue keskkonna järgmises jaotises kirjeldatud juhiste järgi.

7. Pärast keskkonna sätete määratlemist valige **Loo**.

8. Teid logitakse sisse pärast seda, kui keskkonna loomine õnnestus.

## <a name="create-an-environment-in-an-existing-organization"></a>Keskkonna loomine olemasolevasse organisatsiooni

Uue keskkonna loomiseks on kaks võimalust. Saate määrata kas täiesti uue konfiguratsiooni või kopeerida teatud konfiguratsioonisätteid olemasolevast keskkonnast.

> [!NOTE]
> Organisatsioonid saavad iga Customer Insights litsentsi jaoks luua *kaks* keskkonda. Kui teie organisatsioon ostab rohkem kui ühe litsentsi, palun [pöörduge meie tugimeeskonna](https://go.microsoft.com/fwlink/?linkid=2079641) poole, et suurendada vabade keskkondade arvu. Võimsuse ja lisandmooduli võimsuse kohta lisateabe saamiseks laadige alla [Dynamics 365 litsentsimisjuhend](https://go.microsoft.com/fwlink/?LinkId=866544).

Uue keskkonna loomine.

1. Valige rakenduse päises valija **Environment** (Keskkond).

1. Tehke valik **Uus**.

   > [!div class="mx-imgBorder"]
   > ![Keskkonnasätted.](media/environment-settings-dialog.png)

1. Valige **Keskkonna loomine** dialoog, valige **Uus keskkond**.

   Kui soovite [praegusest keskkonnast andmeid kopeerida](#considerations-for-copy-configuration-preview), valige suvand **Kopeeri olemasolevast keskkonnast**. Näete teie ettevõtte kõigi saadaolevate keskkondade loendit, kust saate andmeid kopeerida.

1. Esitage järgmised andmed.
   - **Nimi**: selle keskkonna nimi. Olemasolevast keskkonnast kopeerides on see väli juba täidetud, kuid saate seda muuta.
   - **Tüüp**: valige, kas soovite luua töö- või liivakastikeskkonna.
   - **Piirkond**: piirkond, kus teenus juurutatakse ja majutatakse.
   
1. Soovi korral saate valida ka suvandi **Täpsemad sätted**.

   - **Salvesta kõik andmed**: määrab, kuhu soovite Customer Insightsist loodud väljundandmed talletada. Teil on kaks võimalust: **Customer Insightsi salvestusruum** (Azure Data Lake, mida haldab Customer Insights meeskond) ja **Azure Data Lake Storage** (teie enda Azure Data Lake Storage). Vaikimisi on valitud Customer Insightsi salvestusruumi suvand.

     > [!NOTE]
     > Andmete salvestamisel teenusesse Azure Data Lake Storage nõustute, et andmed edastatakse ja talletatakse selle Azure'i salvestusruumi konto asjakohases geograafilises asukohas, mis võib erineda rakendusse Dynamics 365 Customer Insights talletatud andmete salvestuskohast. [Lisateavet leiate Microsofti usalduskeskusest.](https://www.microsoft.com/trust-center)
     >
     > Praegu salvestatakse edastatud olemid alati Customer Insights hallatavasse Data Lake'i. 
     > 
     > Toetame ainult Azure Data Lake Storage kontosid, mis on pärit samast Azure'i piirkonnast, mille olete keskkonna loomisel valinud. 
     > 
     > Toetame ainult Azure Data Lake Storage kontosid, mille nimeruum on hierarhiline.


   - Selle Azure Data Lake Storage suvandi puhul saate valida ressursipõhise ja kordustellimusel põhineva autentimise suvandi. Lisateavet leiate teemast [Sihtrühmaülevaadete ühendamine Azure Data Lake Storage Gen2 kontoga Azure'i teenusesubjekti kaudu](connect-service-principal.md). **Konteineri** nime ei saa muuta ja see on `customerinsights`.
   
   - Kui soovite kasutada [prognoosimise funktsiooni](predictions.md), konfigureerida andmete jagamist, mida pakub Microsoft Dataverse või lubada asutusesisestest andmeallikatest pärinevaid andmetel luua Microsoft Dataverse keskkonna URL-i, **konfigureerige Microsoft Dataverse andmete jagamine ja lubage täiendavad võimalused**. Valige suvand **Enable data sharing** (Luba andmete ühiskasutus), et jagada Customer Insightsi väljundandmeid Microsoft Dataverse Managed Data Lake hallatava andmejärvega.

     > [!NOTE]
     > - Andmete jagamine rakendusega Microsoft Dataverse Managed Data Lake täna ei toetata, kui salvestate kõik andmed enda andmejärve Azure Data Lake Storage.
     > - [Puuduvate väärtuste ennustust olemis](predictions.md) ei toetata praegu, kui lubate andmete ühiskasutust rakendusega Microsoft Dataverse Managed Data Lake.

     > [!div class="mx-imgBorder"]
     > ![Konfigureerimissuvandid andmete jagamise lubamiseks Microsoft Dataverse abil.](media/datasharing-with-DataverseMDL.png)

   Protsesside käitamisel, näiteks andmete valmendamisel või segmendi loomisel, luuakse asjaomased kaustad eespool määratud salvestuskontol. Sõltuvalt käitatud protsessist luuakse andmefailid ja model.json-failid ning lisatakse kaustadele sõltuvalt protsessi nimest.

   Kui loote mitu Customer Insightsi keskkonda ja soovite salvestada väljundolemid nendest keskkondadest oma salvestuskontole, luuakse eraldi kaustad iga keskkonna jaoks, mille konteineris on ci_<environmentid>.

### <a name="considerations-for-copy-configuration-preview"></a>Kopeerimise konfiguratsiooni kaalutlused (eelversioon)

Kopeeritakse järgmised konfiguratsioonisätted.

- Funktsiooni konfiguratsioonid
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

Järgmisi sätteid *ei* kopeerita.

- Kliendiprofiilid.
- Andmeallika identimisteave. Peate sisestama identimisteabe iga andmeallika jaoks ja värskendama andmeallikaid käsitsi.
- Andmeallikad Common Data Model kaustast ja Dataverse hallatavast Data Lake'st. Peate need andmeallikad looma käsitsi sama nimega kui lähtekeskkond.

Keskkonna kopeerimisel näete kinnitusteadet, et loodi uus keskkond. Andmeallikate loendi nägemiseks valige suvand **Ava andmeallikad**.

Kõik andmeallikad kuvavad olekut **Mandaat nõutav**. Redigeerige andmeallikaid ja sisestage nende värskendamiseks identimisteave.

> [!div class="mx-imgBorder"]
> ![Andmeallikad kopeeritud.](media/data-sources-copied.png)

Pärast andmeallikate värskendamist avage jaotis **Andme** > **Ühendamine**. Siit leiate lähtekeskkonna sätted. Redigeerige neid vastavalt vajadusele või valige **Käivita**, et käivitada andmete ühendamise protsess ja luua ühtne kliendi olem.

Kui andmete ühendamine on lõpetatud, avage **Meetmed** ja **Segmendid**, et neid samuti värskendada.

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
   > - [Prognoosimine puuduvate väärtuste puhul olemis](predictions.md) pole praegu toetatud, kui lubate andmete ühiskasutuse Microsoft Dataverse hallatava Data Lake'iga.

   Pärast andmete jagamise lubamist teenusega Microsoft Dataverse, käivitatakse ühekordne täielik andmeallikate ja muude protsesside värskendamine. Kui protsessid praegu töötavad,, ei näe te suvandit andmete Microsoft Dataverse ühiskasutuse lubamiseks. Oodake, kuni need protsessid lõpetavad või tühistada need andmete jagamise lubamiseks. 
   
   :::image type="content" source="media/datasharing-with-DataverseMDL.png" alt-text="Konfigureerimissuvandid andmete jagamise lubamiseks Microsoft Dataverse abil.":::
   
   Protsesside käitamisel, näiteks andmete valmendamisel või segmendi loomisel, luuakse asjaomased kaustad eespool määratud salvestuskontol. Sõltuvalt käitatud protsessist luuakse andmefailid ja model.json-failid ning lisatakse need vastavatelsse alamkaustadesse.

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
