---
title: Kliendi tegevused
description: Määratleda klienditegevused ja kuvada need kliendiprofiilide ajaskaalal.
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
ms.openlocfilehash: bcb8d42963719f5d225556c31b3fc06db8573e5b
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673132"
---
# <a name="customer-activities"></a>Kliendi tegevused

Erinevatest andmeallikatest [pärinevaid klienditegevusi](data-sources.md) saate ühendada Dynamics 365 Customer Insights ajaskaala loomiseks, mis sisaldab tegevuste kronoloogilist loendit. Lisage ajajoon Dynamics 365 rakendustesse [kliendikaardi lisandmooduli](customer-card-add-in.md) lahendusega või Power BI juhtpaneelile.

## <a name="define-an-activity"></a>Määratle tegevus

Teie andmeallikad võivad hõlmata mitmesugustest andmeallikatest pärinevaid tehingute ja tegevustega seotud andmeid sisaldavaid olemeid. Tuvastage need olemid ja valige tegevused, mida soovite kliendi ajajoonel kuvada. Valige olem, mis hõlmab teie sihttegevust või -tegevusi.

Olemil peab olema vähemalt üks **Kuupäeva** tüüpi atribuut, mis lisatakse kliendi ajajoonele ning ilma **Kuupäeva** väljata olemeid ei saa lisada. Kui sellist olemit ei leita, siis **Lisa tegevus** funktsioon keelatakse.

1. Avage sihtrühmaülevaadetes jaotis **Andmed** > **Tegevused**.

1. Valige **Tegevuse lisamise** protsess, et käivitada tegevuse seadistamise juhendamine.

1. Määrake **tegevuse andmeetapis** järgmiste väljade väärtused:

   - **Tegevuse nimi**: valige oma tegevuse nimi.
   - **Olem**: valige olem, mis sisaldab tehingu või tegevuse andmeid.
   - **Primaarvõti**: valige väli, milles tuvastatakse kirje kordumatult. See ei tohiks sisaldada korduvväärtusi, tühjasid väärtusi ega puuduvaid väärtusi.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Saate seadistada tegevuse andmed nimega, olemiga ja esmase võtmega.":::

1. Valige **Edasi** järgmise etapi juurde minemiseks.

1. Konfigureerige **Seose** sammus üksikasjad, et ühendada oma tegevuseandmed vastava kliendikirjega. Selle sammuga visualiseeritakse olemite vaheline ühendus.  

   - **Esimeseks**: Teie tegevusolemi tundmatu väli, mida kasutatakse seose loomiseks teise olemiga.
   - **Teiseks**: Vastava lähtekliendi olem, kellega teie tegevusolem on seoses. Saate olla seotud ainult lähtekliendi olemitega, mida kasutatakse andmete ühendamise protsessis.
   - **Kolmandaks**: kui selle tegevuseolemi ja valitud lähtekliendi olemi vaheline seos on juba olemas, on seose nimi kirjutuskaitstud režiimis. Kui sellist seost pole, luuakse uus seos, mille nime sisestate sellel väljal.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Olemi seose määratlemine.":::

   > [!TIP]
   > B2B keskkondades saate valida nii konto olemite kui ka muude olemite vahel. Kui valite konto olemi, seatakse seose tee automaatselt. Muude olemite puhul peate määratlema seose tee ühe või mitme vaheolemi üle, kuni olete jõudnud konto olemini.

1. Valige **Edasi** järgmise etapi juurde minemiseks. 

1. Valige **tegevuse ühendamise** etapis tegevussündmus ja oma tegevuse algusaeg. 
   - **Kohustuslikud väljad**
      - **Sündmustegevus**: Väli, mis on selle tegevuse sündmus.
      - **Ajatempel**: Väli, mis tähistab teie tegevuse algusaega.

   - **Valikulised väljad**
      - **Lisateave**: Väli, kus on selle tegevuse jaoks oluline teave.
      - **Ikoon**: ikoon, mis tähistab seda tegevusetüüpi kõige paremini.
      - **Veebiaadress**: Väli, mis sisaldab selle tegevuse kohta teavet sisaldavat URL-i. Näiteks tehingute süsteem, mis on selle tegevuse allikaks. See URL võib olla andmeallika mis tahes väli või seda saab luua uue väljana Power Query teisenduse abil. URL-i andmed talletatakse olemis *Ühendatud tegevus*, mida saab ära kasutada edaspidi kasutades [API-sid](apis.md).

   - **Kuva ajajoonel**
      - Märkige, kas soovite kuvada seda tegevust kliendiprofiilide ajaskaala vaates. Kui soovite tegevuse ajaskaalal kuvada, valige **Jah**, tegevuse peitmiseks valige **Ei**.

      :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Määrake klienditegevuse andmed Ühendatud tegevuse olemis.":::

1. Järgmise etapi juurde liikumiseks klõpsake nuppu **Edasi**. Vvõite valida suvandi **Valmis ja ülevaade**, et salvestada tegevus tüüpiga **Muud**. 

1. Valige etapis **Tegevuse tüüp** tegevuse tüüp ja soovi korral valige, kas soovite mõnda tegevusetüüpi semantiliselt kaardistada, et neid oleks võimalik kasutada Customer Insights muudes alades. Praegu, *Tagasiside*, *Lojaalsus*, *SalesOrder*, *SalesOrderLine* ja *Kordustellimus* tegevuse tüüpe, saab semantiliselt vastendada pärast väljade vastendamisega nõustumist. Kui tegevustüüp pole uue tegevuse jaoks oluline, võite kohandatud tegevustüübi jaoks valida valiku *Muu* või *Loo uus*.

1. Järgmise etapi juurde liikumiseks klõpsake nuppu **Edasi**. 

1. Kontrollige **Vaata üle** etapis oma valikuid. Minge tagasi mõne eelmise toimingu juurde ja vajadusel värskendage teavet.

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="Vaadake läbi tegevuse määratud väljad.":::
   
1. Valige **Salvestage tegevus**, et muudatused rakendada ja seejärel valige **Valmis**, et minna tagasi **Andmed** > **Tegevused** juurde. Siin näete, millised tegevused on seatud ajaskaalal kuvamiseks. 

1. Valige **Tegevused** lehel suvand **Käita** tegevuse töötlemiseks. 

> [!TIP]
> Ülesannete/protsesside jaoks on [kuus tüüpi olekuid](system.md#status-types). Lisaks sõltuvad enamikud protsessid [muudest järgnevatest protsessidest](system.md#refresh-policies). Kogu töö edenemise üksikasjade nägemiseks saate valida protsessi oleku. Kui olete valinud ühe tööülesande jaoks suvandi **Kuva üksikasjad**, näete järgmist lisateavet: töötlemise aeg, viimane töötlemise kuupäev ja kõik ülesandega seotud tõrked ja hoiatused.


## <a name="manage-existing-activities"></a>Olemasolevate tegevuste haldamine

Suvandil **Andmed** > **Tegevused** saate vaadata salvestatud tegevusi ja hallata neid. Iga tegevust tähistab rida, mis sisaldab ka lähteallika, olemi- ja tegevustüübi üksikasju.

Järgmised toimingud on saadaval tegevuse valimiseks. 

- **Redigeeri**: avab tegevuse seadistuse läbivaatuse etapi. Selles etapis saate muuta kõiki praeguseid konfiguratsioone. Pärast konfiguratsiooni muutmist valige **Salvesta tegevus** ja seejärel valige **Käivita** käsk muudatuste töötlemiseks.

- **Ümbernimetamine** : Avab dialoogi, kus saab sisestada valitud tegevusele mõne muu nime. Vajutage nuppu **Salvesta**, et muudatused rakendada.

- **Kustuta**: Avab dialoogi, mis kinnitab valitud tegevuse kustutamise. Korraga saate kustutada ka mitu tegevust, valides tegevused ja seejärel valides kustutamisikooni. Valige käsk **Kustuta**, et kinnitada kustutamine.

## <a name="view-activity-timelines-on-customer-profiles"></a>Tegevuse ajaskaala kuvamine kliendiprofiilides

Pärast klienditegevuste konfigureerimist valige tegevuse konfiguratsioonis suvand **Kuva tegevuse ajaskaalal**, et leida nende kliendiprofiililt kõik teie kliendi tegevused.

Kliendi jaoks ajaskaala avamiseks minge jaotisesse **Kliendid** ja valige kliendiprofiil, mida soovite vaadata.

Kui klient on osalenud teie konfigureeritud tegevuses, leiate selle jaotisest **Tegevuse ajaskaala**.

:::image type="content" source="media/Activity_Timeline1.PNG" alt-text="Konfigureeritud tegevuste kuvamine kliendiprofiilides.":::

Tegevuste filtreerimiseks tegevuse ajaskaalal on mitu võimalust:

- Saate valida ühe või mitu tegevuse ikooni, et viimistleda oma tulemusi ainult valitud tüüpide kaasamiseks.

  :::image type="content" source="media/Activity_Timeline2.PNG" alt-text="Tegevuste filtreerimine ikoonide abil tüübi järgi.":::

- Filtripaneeli avamiseks saate ajaskaalafiltrite konfigureerimiseks valida **Filtri**.

   1. Filtreerida saate *ActivityType'i* ja *Kuupäeva* alusel
   1. Tegevuse ajaskaalal filtrite kasutamiseks tehke valik **Rakenda**.

   :::image type="content" source="media/Activity_Timeline3.PNG" alt-text="Filtripaneeli abil saate konfigureerida filtri tingimusi.":::

Filtrite eemaldamiseks valige ajaskaalale rakendatud filtri kõrval **x** või **Tühjendage filtrid**.


> [!NOTE]
> Kliendiprofiilist lahkudes eemaldatakse tegevuse filtrid. Need tuleb rakendada iga kord kliendiprofiilil avamisel.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
