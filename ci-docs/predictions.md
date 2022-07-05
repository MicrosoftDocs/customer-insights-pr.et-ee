---
title: Osaliste andmete lõpetamine prognooside abil
description: Kasutage prognoose, et täiendada mittetäielikke kliendiandmeid.
ms.date: 11/01/2021
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-predictions
- ci-custom-models
- customerInsights
ms.openlocfilehash: 7e93670007db27d13b84d7516f56830988da083e
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082509"
---
# <a name="complete-your-partial-data-with-predictions-deprecated"></a>Täitke oma osalised andmed ennustustega (aegunud)

> [!IMPORTANT]
> See funktsioon on **aegunud** alates 5. novembrist **2021**. Praegused rakendused töötavad seni, kuni funktsioon on eemaldatud, kuid te ei saa allpool toodud juhiste abil uusi integratsioone luua.

Prognooside abil saate hõlpsalt luua ennustatud väärtusi, mis aitavad suurendada teie arusaamist kliendist. Lehel **Ärianalüüs** > **Prognoosid** saate valida suvandi **Minu prognoosid**, et näha prognoose, mille olete Customer Insightsi teistes osades konfigureerinud, ja saate neid veelgi kohandada.

> [!NOTE]
> Seda funktsiooni ei saa kasutada, kui teie keskkond kasutab Azure Data Lake Gen 2 mäluruumi.
>
> Prognooside funktsioon kasutab andmete hindamiseks ja andmete põhjal prognooside tegemiseks automatiseeritud vahendeid. Seetõttu on seda võimalik kasutada profileerimisviisina, selle termini isikuandmete kaitse üldmääruses (edaspidi „GDPR”) toodud definitsiooni kohaselt. Kui klient seda funktsiooni andmete töötlemiseks kasutab, võivad kohalduda GDPR või muud seadused ja määrused. Teie vastutate selle eest, et Dynamics 365 Customer Insightsi kasutades (sh prognoose kasutades) järgite te kõiki kohaldatavaid seadusi ja määrusi, sh eraelu puutumatuse, isikuandmete, biomeetriliste andmete, andmekaitse ja suhtluse konfidentsiaalsusega seotud seadusi.

## <a name="prerequisites"></a>Eeltingimused

Enne kui teie organisatsioon saab prognooside funktsiooni kasutada, peavad olema täidetud järgmised eeltingimused.

1. Sinu organisatsioonil on näide [seadista Microsoft Dataverse-is](/ai-builder/build-model#prerequisites) ja see on Customer Insights -iga samas organisatsioonis.

2. Teenuse Customer Insights keskkond on lisatud teie teenuse Dataverse eksemplarile.

Lisateavet leiate teemast [Uue keskkonna loomine](create-environment.md).

## <a name="create-a-prediction-in-the-customer-entity"></a>Prognoosi loomine kliendiolemis

1. **Avage andmeolemid** > **·**.

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

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="create-a-prediction-while-creating-a-segment"></a>Prognoosi loomine segmendi loomisel

Mõne kindla atribuudi valimisel puuduvate väärtuste prognoosimine on võimalik ka segmendi loomisel. Täpsemalt siis, kui loote kiiresti segmendi, mis põhineb kas teie ühtlustatud kliendiolemil või kliendi mõõtmise olemil.

Selle voo osana saate valida kindla atribuudi, mis põhineb teie segmendil (nt kliendi rahulolu või ostusumma). Segmendi loomisel soovitab süsteem meetodit selle atribuudi mis tahes puuduvate väärtuste prognoosimiseks.

1. **Avage jaotis Segmendid** ja valige **paan Profiilid**.

2. Valige **Väli**, mille alusel soovite segmendi luua, ja seejärel **Tehtemärk** ja käsk **Vaata üle**.

3. Sisestage segmendi jaoks väärtused **Nimi** ja **Kuvanimi**.

4. Valige **Salvesta**.

5. Kui äsja loodud segmendil allikavälja andmed on puudulikud, saate valida puuduvate väärtuste prognoosimise.
   > [!div class="mx-imgBorder"]
   > ![Prognoosi Nupp.](media/segments-predictoption.png "Nupp Prognoos")

6. Esitage prognooside tulemuste jaoks **Kuvanimi** ja **Väljundi olemi nimi**.

7. Valige nupp **Valmis**. Teie prognoos luuakse peatselt uues olemis nimega, mille sisestasite suvandi **Väljundi olemi nimi** jaoks.

## <a name="view-a-prediction"></a>Prognoosi kuvamine

1. Mine luure **ennustuste** > **juurde** > **Minu ennustused**.

2. Valige prognoos, mille soovite üle vaadata.

3. Valige veerus &vellip; Toimingud **vertikaalne kolmikpunkt (**) ja valige **Vaade**.

4. Näete prognoosi vaates andmepunktide arvu.
   > [!div class="mx-imgBorder"]
   > ![Prognooside leht.](media/intelligence-predictionsviewpage.png "Prognooside leht")

   - **Prognoositud väärtused** näitavad vastendust, mille lõite väljaväärtuse ja kategooria vastendamisel. Need on teie andmekomplektis olevad väärtused, mis on vastendatud kindla kategooriaga.
   -**Peamised mõjutajad** on teie andmekomplekti tegurid, mis mõjutavad kõige tõenäolisemalt prognoosi usaldusväärsust teie väljaväärtuse vastendamisel kindla kategooriaga.
   - **Jõudlus** näitab prognooside edenemist. Lisateabe saamiseks valige soovitud link.
   - **Eelvaade** kuvab teie prognooside ja tõenäosuste väljundi andmekogumi näited, või meie usalduse väärtused eeldatava väärtusega, kus 0 on ebakindel ja 1 on kindel.

## <a name="update-a-prediction"></a>Prognoosi värskendamine

1. Mine luure **ennustuste** > **juurde** > **Minu ennustused**.

2. Valige prognoos, mida soovite värskendada, ja seejärel ikoon **Värskenda**.

3. Prognoos kavandatakse töötlemiseks. Lehe **Prognoosid** veerus **Värskendatud** saate vaadata, millal seda viimati värskendati.

## <a name="edit-a-prediction"></a>Prognoosi redigeerimine

Pärast prognoos loomist saate mudeli AI Builder kohandada, et suurendada oma mudeli tõhusust.  

1. Mine luure **ennustuste** > **juurde** > **Minu ennustused**.

2. Valige prognoos, mida soovite redigeerida.

3. Valige veerus &vellip; Toimingud **vertikaalne kolmikpunkt (**) ja valige **Vaade**.

4. Valige **Kohanda rakenduses AI Builder**.

5. Värskendage oma mudelit väljal AI Builder. [Lisateave AI Builderis mudelite haldamise kohta](/ai-builder/manage-model#retrain-and-republish-existing-models).

Teie prognoosi järgmiseks käivitamiseks kasutatakse teie loodud värskendatud mudelit.

> [!NOTE]
> Uusi rakenduses AI Builder loodud mudeleid ei kuvata Customer Insightsis, välja arvatud juhul, kui mudel on loodud ülalkirjeldatud funktsioonide põhjal.

## <a name="remove-a-prediction"></a>Prognoosi eemaldamine

1. Mine luure **ennustuste** > **juurde** > **Minu ennustused**.

2. Valige prognoos, mille soovite kustutada.

3. Valige veerus &vellip; Toimingud **vertikaalne kolmikpunkt (**) ja valige **Kustuta**.

4. Kinnitage kustutamine.

## <a name="troubleshooting"></a>Tõrkeotsing

Kui te ei saa tõrke tõttu Dataverse'i manustamise protsessi lõpule viia, võite proovida protsessi käsitsi lõpule viia. On kaks teadaolevat probleemi, mis võivad manustamise protsessis esineda.

- Kliendikaardi lisandmooduli lahendus pole installitud.
    1. Täitke [lahenduse installimise ja konfigureerimise](customer-card-add-in.md) juhised.

- Rakenduse õiguseid pole antud.
    1. Avage [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).
    1. Seejärel valige **Keskkonnad**.
    1. Valige selle keskkonna kõrval vertikaalne kolmikpunkt (&vellip;), kuhu soovite õiguse lisada, ja valige **Sätted**.
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


[!INCLUDE [footer-include](includes/footer-banner.md)]
