---
title: Osaliste andmete täiendamine prognooside abil
description: Kasutage prognoose, et täiendada mittetäielikke kliendiandmeid.
ms.date: 11/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 3100acf383d85c00a6ff0a8ebc54e038bd813427
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732373"
---
# <a name="complete-your-partial-data-with-predictions-deprecated"></a>Täitke oma osalised andmed ennustustega (aegunud)

> [!IMPORTANT]
> See funktsioon **aegub** alates **5. novembrist 2021**. Praegused rakendusfunktsioonid töötavad edasi kuni funktsiooni eemaldamiseni, kuid te ei saa allolevate juhiste abil uusi integratsioone luua.

Prognooside abil saate hõlpsalt luua ennustatud väärtusi, mis aitavad suurendada teie arusaamist kliendist. Saate valida lehel **Ärianalüüs** > **Prognoosid** suvandi **Minu prognoosid**, et näha prognoose, mille olete konfigureerinud sihtrühmaülevaadetes muudes kohtades, ning neid veelgi kohandada.

> [!NOTE]
> Seda funktsiooni ei saa kasutada, kui teie keskkond kasutab Azure Data Lake Gen 2 mäluruumi.
>
> Prognooside funktsioon kasutab andmete hindamiseks ja andmete põhjal prognooside tegemiseks automatiseeritud vahendeid. Seetõttu on seda võimalik kasutada profileerimisviisina, selle termini isikuandmete kaitse üldmääruses (edaspidi „GDPR”) toodud definitsiooni kohaselt. Kui klient seda funktsiooni andmete töötlemiseks kasutab, võivad kohalduda GDPR või muud seadused ja määrused. Teie vastutate selle eest, et teie Dynamics 365 Customer Insights kasutamine, sealhulgas prognoosid, vastaks kõigile kohaldatavatele seadustele ja määrustele, sealhulgas eraelu puutumatuse, isikuandmete, biomeetriliste andmete, andmekaitse ja side konfidentsiaalsusega seotud seadustele.

## <a name="prerequisites"></a>Eeltingimused

Enne kui teie organisatsioon saab prognooside funktsiooni kasutada, peavad olema täidetud järgmised eeltingimused.

1. Teie asutuses on [Microsoft Dataverse seadistatud eksemplar](/ai-builder/build-model#prerequisites) ja see on samas organisatsioonis kui kliendiülevaated.

2. Teie vaatajaskonna ülevaatekeskkond on seotud teie Dataverse eksemplariga.

Lisateavet leiate teemast [Uue keskkonna loomine](create-environment.md).

## <a name="create-a-prediction-in-the-customer-entity"></a>Prognoosi loomine kliendiolemis

1. Avage sihtrühmaülevaadetes jaotis **Andmed** > **Olemid**.

2. Valige olem **Klient**.

3. Olemis **Klient: CustomerInsights** valige vahekaart **Väljad**.

4. Leidke atribuudi nimi, mille jaoks soovite väärtusi prognoosida, ja seejärel valige ikoon **Ülevaade** veerus **Kokkuvõte**.
   > [!div class="mx-imgBorder"]
   > ![Ülevaateikoon.](media/intelligence-overviewicon.png "Ülevaateikoon")

5. Kui teie atribuudil on palju puuduvaid väärtusi, valige prognoosiga jätkamiseks suvand **Prognoosi puuduvad väärtused**.
   > [!div class="mx-imgBorder"]
   > ![Ülevaate olek koos puuduvate väärtuste prognoosimise nupuga.](media/intelligence-overviewpredictmissingvalues.png "Ülevaate olek koos puuduvate väärtuste prognoosimise nupuga")

6. Esitage prognooside tulemuste jaoks **Kuvanimi** ja **Väljundi olemi nimi**.

7. Eeltäidetud suvandite loend näitab, missugused väärtused saate prognoositud kategooriatesse vastendada. Sel juhul on teie ainsad kategooriavalikud 0 või 1, kuna need on vastendatavad õige/vale prognoosi või prognoosi binaarse iseloomuga. Veerus Kategooria vastendage väljaväärtused, mida soovite veeru Kategooria lõplikus prognoosis kuni 0 klassifitseerida 0-na, ja üksused, mida soovite lõplikus prognoosis kuni 1 klassifitseerida 1-na.
   > [!div class="mx-imgBorder"]
   > ![Kategooriatega vastendatud väljade väärtuste näide.](media/intelligence-categorymapping.png "Kategooriatega vastendatud väljade väärtuste näide")

8. Valige **Valmis** ja prognoosi hakatakse töötlema. Andmete töötlemise mahust ja keerukusest olenevalt võib töötlemine aega võtta. Tulemused on saadaval uues olemis, mis põhineb teie loodud prognoosi suvandil **Väljundi olemi nimi**.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="create-a-prediction-while-creating-a-segment"></a>Prognoosi loomine segmendi loomisel

Mõne kindla atribuudi valimisel puuduvate väärtuste prognoosimine on võimalik ka segmendi loomisel. Täpsemalt siis, kui loote kiiresti segmendi, mis põhineb kas teie ühtlustatud kliendiolemil või kliendi mõõtmise olemil.

Selle voo osana saate valida kindla atribuudi, mis põhineb teie segmendil (nt kliendi rahulolu või ostusumma). Segmendi loomisel soovitab süsteem meetodit selle atribuudi mis tahes puuduvate väärtuste prognoosimiseks.

1. Minge sihtrühmaülevaadetes lehele **Segmendid** ja valige paan **Profiilid**.

2. Valige **Väli**, mille alusel soovite segmendi luua, ja seejärel **Tehtemärk** ja käsk **Vaata üle**.

3. Sisestage segmendi jaoks väärtused **Nimi** ja **Kuvanimi**.

4. Valige **Salvesta**.

5. Kui äsja loodud segmendil allikavälja andmed on puudulikud, saate valida puuduvate väärtuste prognoosimise.
   > [!div class="mx-imgBorder"]
   > ![Prognoosi Nupp.](media/segments-predictoption.png "Nupp Prognoos")

6. Esitage prognooside tulemuste jaoks **Kuvanimi** ja **Väljundi olemi nimi**.

7. Valige nupp **Valmis**. Teie prognoos luuakse peatselt uues olemis nimega, mille sisestasite suvandi **Väljundi olemi nimi** jaoks.

## <a name="view-a-prediction"></a>Prognoosi kuvamine

1. Avage sihtrühmaülevaadetes jaotis **Ärianalüüs** > **Prognoosid** > **Minu prognoosid**.

2. Valige prognoos, mille soovite üle vaadata.

3. Valige kolmikpunkt veerus **Toimingud** ja seejärel **Vaade**.

4. Näete prognoosi vaates andmepunktide arvu.
   > [!div class="mx-imgBorder"]
   > ![Prognooside leht.](media/intelligence-predictionsviewpage.png "Prognooside leht")

   - **Prognoositud väärtused** näitavad vastendust, mille lõite väljaväärtuse ja kategooria vastendamisel. Need on teie andmekomplektis olevad väärtused, mis on vastendatud kindla kategooriaga.
   -**Peamised mõjutajad** on teie andmekomplekti tegurid, mis mõjutavad kõige tõenäolisemalt prognoosi usaldusväärsust teie väljaväärtuse vastendamisel kindla kategooriaga.
   - **Jõudlus** näitab prognooside edenemist. Lisateabe saamiseks valige soovitud link.
   - **Eelvaade** kuvab teie prognooside ja tõenäosuste väljundi andmekogumi näited, või meie usalduse väärtused eeldatava väärtusega, kus 0 on ebakindel ja 1 on kindel.

## <a name="update-a-prediction"></a>Prognoosi värskendamine

1. Avage sihtrühmaülevaadetes jaotis **Ärianalüüs** > **Prognoosid** > **Minu prognoosid**.

2. Valige prognoos, mida soovite värskendada, ja seejärel ikoon **Värskenda**.

3. Prognoos kavandatakse töötlemiseks. Lehe **Prognoosid** veerus **Värskendatud** saate vaadata, millal seda viimati värskendati.

## <a name="edit-a-prediction"></a>Prognoosi redigeerimine

Kui olete prognoosi loonud, saate oma mudeli efektiivsuse tõstmiseks kohandada ka AI Builderi mudelit.  

1. Avage sihtrühmaülevaadetes jaotis **Ärianalüüs** > **Prognoosid** > **Minu prognoosid**.

2. Valige prognoos, mida soovite redigeerida.

3. Valige kolmikpunkt veerus **Toimingud** ja seejärel **Vaade**.

4. Valige käsk **Kohanda AI Builderis**.

5. Värskendage oma mudelit AI Builderis. [Lisateave AI Builderis mudelite haldamise kohta](/ai-builder/manage-model#retrain-and-republish-existing-models).

Teie prognoosi järgmiseks käivitamiseks kasutatakse teie loodud värskendatud mudelit.

> [!NOTE]
> AI Builderis loodud uusi mudeleid ei kuvata sihtrühmaülevaadetes, välja arvatud juhul, kui mudel on loodud eespool loetletud kogemuste põhjal.

## <a name="remove-a-prediction"></a>Prognoosi eemaldamine

1. Avage sihtrühmaülevaadetes jaotis **Ärianalüüs** > **Prognoosid** > **Minu prognoosid**.

2. Valige prognoos, mille soovite kustutada.

3. Valige veerus **Toimingud** kolmikpunkt ja seejärel käsk **Kustuta**.

4. Kinnitage kustutamine.

## <a name="troubleshooting"></a>Tõrkeotsing

Kui te ei saa manustamisprotsessi Dataverse tõrke tõttu lõpule viia, võite proovida protsessi käsitsi lõpule viia. On kaks teadaolevat probleemi, mis võivad manustamise protsessis esineda.

- Kliendikaardi lisandmooduli lahendus pole installitud.
    1. Täitke [lahenduse installimise ja konfigureerimise](customer-card-add-in.md) juhised.

- Rakenduse õiguseid pole antud.
    1. Avage [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).
    1. Seejärel valige **Keskkonnad**.
    1. Valige kolmikpunkt selle keskkonna kõrval, millele soovite õigused lisada, ja valige **Sätted**.
    1. Laiendage jaotis **Kasutajad + õigused** ja valige **Kasutajad**.
    1. Valige **+ Uus** ja valige **Kasutaja**.
    1. Valige **Rakenduse kasutaja**, kui see pole juba valitud, ja sisestage järgmised andmed.
        - **Kasutaja nimi:** cihelp@microsoft.com
        - **Rakenduse ID:** 38c77d00-5fcb-4cce-9d93-af4738258e3c
        - **Eesnimi:** Customer
        - **Perekonnanimi:** Insights
        - **Esmane meiliaadress:** cihelp@microsoft.com
    1. Valige **Salvesta ja sule**.
    1. Valige äsja loodud kasutaja.
    1. Valige ülemiselt menüüribalt suvand **Halda rolle**.
    1. Valige **Süsteemiadministraator** ja seejärel valige **OK**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
