---
title: Kliendi tegevused
description: Määratleda klienditegevused ja kuvada need kliendiprofiilide ajaskaalal.
ms.date: 07/22/2022
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-entities
- ci-customer-card
- ci-relationships
- ci-activities
- ci-activities-wizard
- ci-measures
- ci-segment-suggestions
- customerInsight
ms.openlocfilehash: cc21b0eeb368156437e60d851c2d144f3974c066
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 07/22/2022
ms.locfileid: "9188134"
---
# <a name="customer-activities"></a>Klienditegevused

Kliendi tegevused on klientide tehtud toimingud või sündmused. Näiteks tehingud, tugikõne kestus, veebisaidi ülevaated, ostud või tagastused. Need tegevused sisalduvad ühes või mitmes andmeallikas. Kliendistatistika abil konsolideerige oma klienditegevused nendest [andmeallikatest](data-sources.md) ja seostage need kliendiprofiilidega. Need tegevused kuvatakse kronoloogiliselt kliendiprofiili ajaskaalal. Lisage dynamics 365 rakenduste ajaskaala kliendikaardi lisandmooduli [lahendusega](customer-card-add-in.md).

## <a name="define-an-activity"></a>Määratle tegevus

Olemil peab olema vähemalt üks atribuut, mille tüüp **on Kuupäev**, et kaasata kliendi ajaskaalasse. Kui sellist olemit ei leita, siis **Lisa tegevus** funktsioon keelatakse.

1. Avage **jaotis Andmetegevused** > **·**.

1. Valige **Käsk Lisa tegevusi**, et alustada juhendatud kogemust.

1. Sisestage **tegevusetapis** järgmine teave.

   - **Tegevuse nimi**: teie tegevuse nimi.
   - **Tegevuse olem**: ettevõte, mis sisaldab kande- või tegevusandmeid.
   - **Primaarvõti**: väli, mis tuvastab kirje kordumatult. See ei tohiks sisaldada korduvväärtusi, tühjasid väärtusi ega puuduvaid väärtusi.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Saate seadistada tegevuse andmed nimega, olemiga ja esmase võtmega.":::

1. Tehke valik **Edasi**.

1. **Valige etapis Seos** käsk **Lisa seos**, et ühendada oma tegevuse andmed vastava kliendikirjega. Selle sammuga visualiseeritakse olemite vaheline ühendus.  

   - **Välisvõti olemist**: väli teie tegevuse olemis, mida kasutatakse seose loomiseks teise olemiga.
   - **Üksuse nimele**: vastav lähtekliendi olem, millega teie tegevuse olem on seotud. Saate olla seotud ainult lähtekliendi olemitega, mida kasutatakse andmete ühendamise protsessis.
   - **Seose nimi**: nimi, mis identifitseerib olemite vahelise seose. Kui seos selle tegevuse olemi ja valitud lähtekliendi olemi vahel on juba olemas, on seose nimi kirjutuskaitstud.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Olemi seose määratlemine.":::

   > [!TIP]
   > B2B keskkondades saate valida nii konto olemite kui ka muude olemite vahel. Kui valite konto olemi, seatakse seose tee automaatselt. Muude olemite puhul peate määratlema seose tee ühe või mitme vaheolemi üle, kuni olete jõudnud konto olemini.

1. Seose loomiseks valige **Rakenda**.

1. Tehke valik **Edasi**.

1. Valige **tegevuse ühendamise** etapis tegevussündmus ja oma tegevuse algusaeg.
   - **Kohustuslikud väljad**
      - **Sündmustegevus**: Väli, mis on selle tegevuse sündmus.
      - **Ajatempel**: Väli, mis tähistab teie tegevuse algusaega.

   - **Valikulised väljad**
      - **Lisateave**: Väli, kus on selle tegevuse jaoks oluline teave.
      - **Ikoon**: ikoon, mis tähistab seda tegevusetüüpi kõige paremini.
      - **Veebiaadress**: Väli, mis sisaldab selle tegevuse kohta teavet sisaldavat URL-i. Näiteks tehingute süsteem, mis on selle tegevuse allikaks. See URL võib olla mis tahes väli andmeallikas või selle saab teisenduse abil Power Query konstrueerida uue väljana. URL-i andmed talletatakse olemis *Ühendatud tegevus*, mida saab ära kasutada edaspidi kasutades [API-sid](apis.md).

   - **Kuva ajajoonel**
      - Märkige, kas soovite kuvada seda tegevust kliendiprofiilide ajaskaala vaates. Kui soovite tegevuse ajaskaalal kuvada, valige **Jah**, tegevuse peitmiseks valige **Ei**.

      :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Määrake klienditegevuse andmed Ühendatud tegevuse olemis.":::

1. Tegevuse tüübi valimiseks valige **Edasi või valige** Valmis ja läbivaatus **, et salvestada tegevus, mille tegevuse tüübiks** on seatud **Muu**.

1. Valige etapis **Tegevuse tüüp** tegevuse tüüp ja soovi korral valige, kas soovite mõnda tegevusetüüpi semantiliselt kaardistada, et neid oleks võimalik kasutada Customer Insights muudes alades. *Praegu toetavad tagasiside*, *püsikliendi*, *müügitellimuse*, *SalesOrderLine'i* ja *tellimuse* tegevuste tüübid semantikat pärast väljade vastendamisega nõustumist. Kui tegevustüüp pole uue tegevuse jaoks oluline, võite kohandatud tegevustüübi jaoks valida valiku *Muu* või *Loo uus*.

1. Tehke valik **Edasi**.

1. Kontrollige **Vaata üle** etapis oma valikuid. Minge tagasi mõne eelmise toimingu juurde ja vajadusel värskendage teavet.

1. Valige **Salvestage tegevus**, et muudatused rakendada ja seejärel valige **Valmis**, et minna tagasi **Andmed** > **Tegevused** juurde. Loodud tegevus kuvatakse.

1. Pärast kõigi tegevuste loomist valige **nende töötlemiseks Käsk Käivita**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-activities"></a>Olemasolevate tegevuste haldamine

Minge jaotisse **Andmetegevused** > **·**, et vaadata salvestatud tegevusi, nende lähteolemit, tegevuse tüüpi ja seda, kas need on kaasatud kliendi ajaskaalale. Tegevuste loendit saate sortida mis tahes veeru järgi või kasutada otsinguvälja, et leida tegevus, mida soovite hallata.

Valige tegevus, et vaadata saadaolevaid toiminguid.

- **Redigeerige** tegevust, et muuta selle konfiguratsiooni. Konfiguratsioon avaneb ülevaatuse etapis. Pärast konfiguratsiooni muutmist valige **Salvesta tegevus** ja seejärel valige **Käivita** käsk muudatuste töötlemiseks.
- **Nimetage tegevus ümber**. Vajutage nuppu **Salvesta**, et muudatused rakendada.
- **Kustutage** tegevus. Mitme tegevuse korraga kustutamiseks valige tegevused ja seejärel **Kustuta**. Kinnitage kustutamine.

## <a name="view-activity-timelines-on-customer-profiles"></a>Tegevuse ajaskaala kuvamine kliendiprofiilides

1. Kui valisite tegevuse konfiguratsioonis käsu **Kuva tegevuse ajaskaalas**, minge jaotisse **Kliendid** ja valige kliendiprofiil, et vaadata kliendi tegevusi **jaotises Tegevuse ajaskaala**.

   :::image type="content" source="media/Activity_Timeline1.PNG" alt-text="Konfigureeritud tegevuste kuvamine kliendiprofiilides.":::

1. Tegevuste filtreerimiseks tegevuste ajaskaalal tehke järgmist.

   - Valige üks või mitu tegevuse ikooni, et täpsustada tulemusi nii, et need hõlmaksid ainult valitud tüüpe.

     :::image type="content" source="media/Activity_Timeline2.PNG" alt-text="Tegevuste filtreerimine ikoonide abil tüübi järgi.":::

   - Ajaskaalafiltrite konfigureerimiseks filtripaneeli avamiseks valige **Filter**. Filtreerige activitytype'i ja/või *kuupäeva järgi* *.* Valige suvand **Rakenda**.

     :::image type="content" source="media/Activity_Timeline3.PNG" alt-text="Filtripaneeli abil saate konfigureerida filtri tingimusi.":::

1. Filtrite eemaldamiseks valige **Tühjenda filtrid** või valige **Filtreeri** ja tühjendage märkeruut Filter.

> [!NOTE]
> Kliendiprofiilist lahkudes eemaldatakse tegevuse filtrid. Peate neid rakendama iga kord, kui avate kliendiprofiili.

[!INCLUDE [footer-include](includes/footer-banner.md)]
