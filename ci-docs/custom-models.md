---
title: Kohandatud masinõppe mudelid | Microsoft Docs
description: Azure'i masinõppe kohandatud mudelitega töötamine rakenduses Dynamics 365 Customer Insights.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
searchScope:
- ci-custom-models
- customerInsights
ms.openlocfilehash: 89553b511d249fd586e36a1c4944a977513b0643
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609740"
---
# <a name="custom-machine-learning-models"></a>Kohandatud masinõppe mudelid

> [!NOTE]
> Masinõpe Studio (klassikaline) toetus lõpeb 31. augustil 2024. Soovitame teil selleks kuupäevaks [azure Masinõpe](/azure/machine-learning/overview-what-is-azure-machine-learning) üle minna.
>
> Alates 1. detsembrist 2021 ei saa te luua uusi Masinõpe Studio (klassikalisi) ressursse. Kuni 31. augustini 2024 saate jätkata olemasolevate Masinõpe Studio (klassikaliste) ressursside kasutamist. Lisateavet leiate teemast [Azure’i migreerimine Masinõpe](/azure/machine-learning/migrate-overview).

Kohandatud mudelid võimaldavad hallata töövooge Azure Masinõpe mudelite põhjal. Töövood aitavad teil valida andmed, mille põhjal soovite ülevaateid luua, ja vastendada tulemused teie koondatud kliendiandmetega. Lisateavet kohandatud masinõppemudelite loomise kohta leiate teemast [Azure'i masinaõppe põhiste mudelite kasutamine](azure-machine-learning-experiments.md).

## <a name="prerequisites"></a>eeltingimused

- Azure’i Masinõpe pakett-konveierite kaudu [avaldatud veebiteenused](/azure/machine-learning/concept-ml-pipelines).
- Torujuhe tuleb avaldada torujuhtme lõpp-punkti [all](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).
- [Azure Data Lake Gen2 salvestusruumikonto,](/azure/storage/blobs/data-lake-storage-quickstart-create-account) mis on seotud teie Azure Studio eksemplariga.
- Azure Masinõpe tööruume, millel on müügitorud, omaniku või kasutaja juurdepääsu administraatori õigused Azure Masinõpe Workspace’ile.

  > [!NOTE]
  > Andmed edastatakse teie Customer Insightsi eksemplaride ja töövoos valitud Azure'i veebiteenuste või konveierite vahel. Andmete edastamisel Azure'i teenusele veenduge, et teenus oleks konfigureeritud andmeid töötlema vajalikul viisil ja kohas, mis vastaks mis tahes juriidilistele või regulatiivsetele nõuetele nende andmete puhul teie organisatsioonis.

## <a name="add-a-new-workflow"></a>Uue töövoo lisamine

1. Avage jaotis **Ärianalüüs** > **Kohandatud mudelid** ja valige **Uus töövoog**.

1. Sisestage äratuntav **nimi**.

   :::image type="content" source="media/new-workflowv2.png" alt-text="Uue töövoo paani kuvatõmmis.":::

1. Valige veebiteenust sisaldav organisatsioon jaotises **Teie veebiteenust sisaldav rentnik**.

1. Kui teie Azure'i masinõppe kordustellimus on mõnes muus rentnikus kui Customer Insights, valige suvand **Logi sisse** oma valitud organisatsiooni mandaadiga.

1. Valige oma veebiteenusega seotud **tööruumid**.

1. Valige veebiteenuses **Azure Masinõpe, mis sisaldab teie mudeli** ripploendit. Seejärel valige suvand **Edasi**.
   Lugege lisateavet [konveieri avaldamise kohta Azure'i masinõppes kujundaja abil](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) või [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk) kohta.

1. Valige iga **Veebiteenuse sisendi** kohta Customer Insightsist vastav **Olem**. Seejärel valige suvand **Edasi**.
   > [!NOTE]
   > Kohandatud mudeli töövoog rakendab heuristikat veebiteenuse sisendväljade vastendamiseks olemiatribuutidele, võttes aluseks välja nime ja andmetüübi. Kui veebiteenuse välja ei saa olemile vastendada, kuvatakse tõrge.

   :::image type="content" source="media/intelligence-screen2-updated.png" alt-text="Konfigureeri töövoog.":::

1. Määrake mudeli väljundparameetrite **jaoks** järgmised atribuudid.
   - **Müügitoru väljundtulemite olemi nimi**
   - **Partiitoru väljund andmesalv parameetri nimi**
   - **Teie partiitoru parameetri Väljundtee nimi**

   :::image type="content" source="media/intelligence-screen3-outputparameters.png" alt-text="Mudeli väljundi parameetri paan.":::

1. Valige tulemites **kliendi ID-st** vastav atribuut, mis tuvastab kliendid, ja valige **Salvesta**.

   :::image type="content" source="media/intelligence-screen4-relatetocustomer.png" alt-text="Tulemuste seostamine paanil „Kliendiandmed“.":::

   Salvestatud **töövoo** kuval kuvatakse töövoo üksikasjad. Kui konfigureerisite Töövoo Azure Masinõpe müügitoru jaoks, manustatakse Customer Insights müügitoru sisaldavale tööruumile. Customer Insights saab Kaasautori **rolli** Azure’i tööruumis.

1. Valige nupp **Valmis**. Kuvatakse **leht Kohandatud mudelid**.

1. Valige töövoo vertikaalne kolmikpunkt (&vellip;) ja valige **Käivita**. Teie töövoog töötab automaatselt ka iga [ajastatud värskendamisega](schedule-refresh.md).

## <a name="manage-an-existing-workflow"></a>Olemasoleva töövoo haldamine

Minge jaotisse **Intelligentsuse** > **kohandatud mudelid**, et vaadata teie loodud töövooge.

Valige töövoog saadaolevate toimingute vaatamiseks.

- **Töövoo redigeerimine**
- **Töövoo käivitamine**
- [**Töövoo kustutamine**](#delete-a-workflow)

### <a name="edit-a-workflow"></a>Töövoo redigeerimine

1. Avage **jaotis Intelligentsuse** > **kohandatud mudelid**.

1. Valige värskendatava töövoo kõrval vertikaalne kolmikpunkt (&vellip;) ja valige **Redigeeri**.

1. Vajadusel muutke **kuvatavat nime** ja valige **Edasi**.

1. Vajadusel värskendage iga **veebiteenuse sisendi** puhul vastavat **olemit** Customer Insightsist. Seejärel valige suvand **Edasi**.

1. Mudeli väljundparameetrite **puhul** muutke ühte järgmistest.
   - **Müügitoru väljundtulemite olemi nimi**
   - **Partiitoru väljund andmesalv parameetri nimi**
   - **Teie partiitoru parameetri Väljundtee nimi**

1. Muutke tulemites **kliendi ID-st** vastavat atribuuti, et kliente tuvastada. Valige tuletuse väljundist atribuut, mille väärtused on sarnased kliendiolemi veeru „Kliendi ID“ omadega. Kui teie andmekogumis pole sellist veergu, valige atribuut, mis tuvastab rea kordumatult.

1. Valige **Salvesta**

### <a name="delete-a-workflow"></a>Töövoo kustutamine

1. Avage **jaotis Intelligentsuse** > **kohandatud mudelid**.

1. Valige kustutatava töövoo kõrval vertikaalne kolmikpunkt (&vellip;) ja valige **Kustuta**.

1. Kinnitage, et soovite kustutada.

Teie töövoog kustutatakse. [Töövoo loomisel loodud olem](entities.md) jääb alles ja seda saab vaadata lehelt **Andmeüksused** > **·**.

## <a name="view-the-results"></a>Vaadake tulemusi

Töövoo tulemused salvestatakse mudeli väljundparameetrite jaoks **määratletud olemi nimes**. Juurdepääs nendele andmetele lehelt Andmeüksused [**·** > **või API-juurdepääsuga**](entities.md).[...](apis.md)

### <a name="api-access"></a>API-juurdepääs

Kindla OData päringu andmete toomiseks kohandatud mudeli olemist kasutage järgmist vormingut.

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. Asendage `<your instance id>` oma Customer Insightsi keskkonna ID-ga, mis kuvatakse teie brauseri aadressiribal, kui kasutate Customer Insightsi.

1. Asendage `<custom model output entity>` olemi nimega, mille esitasite mudeli väljundparameetrite **jaoks**.

1. Asendage `<guid value>` selle kliendi kliendi ID-ga, kellele soovite juurde pääseda. See ID kuvatakse [kliendiprofiilide lehel](customer-profiles.md) väljal CustomerID.

## <a name="frequently-asked-questions"></a>Korduma kippuvad küsimused

- Miks ei saa kohandatud mudeli töövoo seadistamisel konveierit vaadata?
  Selle probleemi põhjuseks on sageli konveieri konfiguratsiooniprobleem. Veenduge, [et sisendparameeter oleks](azure-machine-learning-experiments.md#dataset-configuration)konfigureeritud ning konfigureeritud on ka [väljundandmesalve ja tee parameetrid](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights).

- Mida tähendab tõrge „Ei saanud ärianalüüsi töövoogu salvestada“? 
  Kasutajad näevad seda tõrketeadet tavaliselt juhul, kui neil pole tööruumis omaniku- või kasutajajuurdepääsu administraatori õigusi. Kasutajal on vaja õiguste kõrgemat taset, et võimaldada Customer Insightsil töövoogu teenusena töödelda, mitte kasutada kasutaja identimisteavet töövoo järgmisteks töövoogudeks.

- Kas minu kohandatud mudeli töövoo privaatne lõpp-punkt / privaatne link on toetatud?
  Customer Insights ei toeta praegu kohandatud mudelite privaatset lõpp-punkti, kuid saadaval on käsitsi lahendus. Lisateabe saamiseks võtke ühendust toega.

## <a name="responsible-ai"></a>Vastutustundlik tehisintellekt

Prognoosid pakuvad võimalusi klientidele paremate kogemuste loomiseks ning ärivõimaluste ja tulu parandamiseks. Soovitame teil oma prognoosi väärtuse hindamisel võtta eetiliselt arvesse selle mõju ja kallutusi, milleni see võib viia. Lugege lisateavet selle kohta, kuidas Microsoft [käsitleb vastutustundlikku tehisintellekti](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). Samuti saate tutvuda Azure'i masinõppega seotud [vastutustundliku masinõppe meetodite ja protsessidega](/azure/machine-learning/concept-responsible-ml).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElk]

[!INCLUDE [footer-include](includes/footer-banner.md)]
