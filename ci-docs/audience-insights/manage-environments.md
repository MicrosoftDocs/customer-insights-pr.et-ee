---
title: Keskkondade loomine ja haldamine
description: Siit leiate teavet selle kohta, kuidas teenuse kasutamiseks registreeruda ja kuidas keskkondasid hallata.
ms.date: 11/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
ms.reviewer: nimagen
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 010336445d0825a7ff82d1b7a65702fc12245788
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644128"
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

Uue keskkonna loomine.

1. Valige rakenduse päises sümbol **Sätted**.

1. Valige suvand **Uus keskkond**.

   > [!div class="mx-imgBorder"]
   > ![Keskkonnasätted](media/environment-settings-dialog.png)

1. Valige dialoogist **Uue keskkonna loomine** suvand **Uus keskkond**.

   Kui soovite [praegusest keskkonnast andmeid kopeerida](#additional-considerations-for-copy-configuration-preview), valige suvand **Kopeeri olemasolevast keskkonnast**. Näete teie ettevõtte kõigi saadaolevate keskkondade loendit, kust saate andmeid kopeerida.

1. Esitage järgmised andmed.
   - **Nimi**: selle keskkonna nimi. Olemasolevast keskkonnast kopeerides on see väli juba täidetud, kuid saate seda muuta.
   - **Piirkond**: piirkond, kus teenus juurutatakse ja majutatakse.
   - **Tüüp**: valige, kas soovite luua töö- või liivakastikeskkonna.

2. Soovi korral saate valida ka suvandi **Täpsemad sätted**.

   - **Salvesta kõik andmed**: määrab, kuhu soovite Customer Insightsist loodud väljundandmed talletada. Selleks on kaks võimalust: **Customer Insightsi salvestusruum** (Customer Insightsi meeskonna hallatav Azure Data Lake) ja **Azure Data Lake Storage Gen2** (teie isiklik Azure Data Lake Storage). Vaikimisi on valitud Customer Insightsi salvestusruumi suvand.

   > [!NOTE]
   > Andmete salvestamisel teenusesse Azure Data Lake Storage nõustute, et andmed edastatakse ja talletatakse selle Azure'i salvestusruumi konto asjakohases geograafilises asukohas, mis võib erineda rakendusse Dynamics 365 Customer Insights talletatud andmete salvestuskohast. [Lisateavet leiate Microsofti usalduskeskusest.](https://www.microsoft.com/trust-center)
   >
   > Praegu salvestatakse sisestatud olemid alati Customer Insightsi hallatavasse andmejärve.
   > Toetame ainult Azure Data Lake Gen2 salvestuskontosid, mis asuvad samas Azure'i regioonis, mille valisite keskkonna loomisel.
   > Toetame ainult salvestuskontosid, kus on lubatud Azure Data Lake Gen 2 hierarhiline nimeruum (HNS).

   - Azure Data Lake Storage Gen2 korral saate autentimiseks valida ressursipõhise ja tellimusepõhise valiku vahel. Lisateavet leiate teemast [Sihtrühmaülevaadete ühendamine Azure Data Lake Storage Gen2 kontoga Azure'i teenusesubjekti kaudu](connect-service-principal.md). **Konteineri** nime ei saa muuta ja see on „customerinsights“.
   
   - Kui soovite kasutada [prognoose](predictions.md), sisestage Common Data Service'i eksemplari URL väljale **Serveri aadress**, mis asub jaotises **Prognooside kasutamine**.

   Protsesside käitamisel, näiteks andmete valmendamisel või segmendi loomisel, luuakse asjaomased kaustad eespool määratud salvestuskontol. Luuakse andmefailid ja model.json failid ning need lisatakse teie käitatavate protsesside põhjal vastavatesse alamkaustadesse.

   Kui loote mitu Customer Insightsi keskkonda ja soovite salvestada väljundolemid nendest keskkondadest oma salvestuskontole, luuakse eraldi kaustad iga keskkonna jaoks, mille konteineris on ci_<environmentid>.

### <a name="additional-considerations-for-copy-configuration-preview"></a>Lisakaalutlused konfiguratsiooni kopeerimise puhul (eelvaade)

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
- Andmeallikad kaustast Ühine andmemudel ja Common Data Service’i hallatavast järvest. Peate need andmeallikad looma käsitsi sama nimega kui lähtekeskkond.

Keskkonna kopeerimisel näete kinnitusteadet, et loodi uus keskkond. Andmeallikate loendi nägemiseks valige suvand **Ava andmeallikad**.

Kõik andmeallikad kuvavad olekut **Mandaat nõutav**. Redigeerige andmeallikaid ja sisestage nende värskendamiseks identimisteave.

> [!div class="mx-imgBorder"]
> ![Andmeallikad kopeeritud](media/data-sources-copied.png)

Pärast andmeallikate värskendamist avage jaotis **Andme** > **Ühendamine**. Siit leiate lähtekeskkonna sätted. Redigeerige neid vastavalt vajadusele või valige **Käivita**, et käivitada andmete ühendamise protsess ja luua ühtne kliendi olem.

Kui andmete ühendamine on lõpetatud, avage **Meetmed** ja **Segmendid**, et neid samuti värskendada.

## <a name="edit-an-existing-environment"></a>Olemasoleva keskkonna redigeerimine

Saate muuta olemasolevate keskkondade teatud üksikasju.

1. Avage suvandid **Administraator** > **Süsteem** > **Teave**.

2. Valige **Redigeeri**.

3. Saate värskendada keskkonna **Kuvatavat nime**, kuid te ei saa muuta **Piirkonda** ega **Tüüpi**.

4. Kui keskkonna andmete salvestusruumiks on konfigureeritud Azure Data Lake Storage Gen2, siis saate uuendada suvandit **Kontovõti**. Kuid te ei saa muuta **Ettevõtte nime** ja **Konteineri** nime.

5. Soovi korral saate kasutada kontovõtmepõhise ühenduse asemel ressursipõhist või tellimusepõhist ühendust. Pärast selle tegemist ei saa te värskenduse järel hakata uuesti kontovõtit kasutama. Lisateavet leiate teemast [Sihtrühmaülevaadete ühendamine Azure Data Lake Storage Gen2 kontoga Azure'i teenusesubjekti kaudu](connect-service-principal.md). Ühenduse värskendamisel ei saa te muuta **konteineri** teavet.

## <a name="reset-an-existing-environment"></a>Olemasoleva keskkonna lähtestamine

Kui soovite kustutada kõik konfiguratsioonid ja eemaldada valmendatud andmed, saate keskkonna lähtestada nii, et see oleks täiesti tühi.

1.  Avage suvandid **Administraator** > **Süsteem** > **Teave**.

2.  Valige **Lähtesta**. 

3.  Kustutamise kinnitamiseks sisestage keskkonna nimi ja valige **Lähtesta**.


## <a name="delete-an-existing-environment"></a>Olemasoleva keskkonna kustutamine

1. Avage suvandid **Administraator** > **Süsteem** > **Teave**.

1. Valige **Kustuta**.

1. Kustutamise kinnitamiseks sisestage soovitud keskkonna nimi ja valige **Kustuta**.
