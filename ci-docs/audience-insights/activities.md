---
title: Klienditegevused
description: Määratlege klienditegevusi ja vaadake neid kliendi ajaskaalal.
ms.date: 04/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: 0c728fad4ed00d1bf085fed60057211861b3a195
ms.sourcegitcommit: f0855bd7762b1f0a1d3dd5259e23c95e1b0a6a93
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 04/07/2021
ms.locfileid: "5866402"
---
# <a name="customer-activities"></a>Klienditegevused

Erinevatest andmeallikatest [pärinevaid klienditegevusi](data-sources.md) saate ühendada Dynamics 365 Customer Insights ajaskaala loomiseks, mis sisaldab tegevuste kronoloogilist loendit. Lisage ajajoon Dynamics 365 rakendustesse [kliendikaardi lisandmooduli](customer-card-add-in.md) lahendusega või Power BI juhtpaneelile.

## <a name="define-an-activity"></a>Määratle tegevus

Teie andmeallikad võivad hõlmata mitmesugustest andmeallikatest pärinevaid tehingute ja tegevustega seotud andmeid sisaldavaid olemeid. Tuvastage need olemid ja valige tegevused, mida soovite kliendi ajajoonel kuvada. Valige olem, mis hõlmab teie sihttegevust või -tegevusi.

> [!NOTE]
> Olemil peab olema vähemalt üks **Kuupäeva** tüüpi atribuut, mis lisatakse kliendi ajajoonele ning ilma **Kuupäeva** väljata olemeid ei saa lisada. Kui sellist olemit ei leita, siis **Lisa tegevus** funktsioon keelatakse.

1. Avage sihtrühmaülevaadetes jaotis **Andmed** > **Tegevused**.

1. Valige **Tegevuse lisamise** protsess, et käivitada tegevuse seadistamise juhendamine.

1. Määrake **tegevuse andmeetapis** järgmiste väljade väärtused:

   - **Tegevuse nimi**: valige oma tegevuse nimi.
   - **Olem**: valige olem, mis sisaldab tehingu või tegevuse andmeid.
   - **Primaarvõti**: valige väli, milles tuvastatakse kirje kordumatult. See ei tohiks sisaldada korduvväärtusi, tühjasid väärtusi ega puuduvaid väärtusi.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Saate seadistada tegevuse andmed nimega, olemiga ja esmase võtmega.":::

1. Valige **Edasi** järgmise etapi juurde minemiseks.

1. Konfigureerige **Seosed** etapis üksikasjad, et ühendada oma tegevuseandmed vastava kliendiga. Selle sammuga visualiseeritakse olemite vaheline ühendus.  

   - **Esimeseks**: Teie tegevusolemi tundmatu väli, mida kasutatakse seose loomiseks teise olemiga.
   - **Teiseks**: Vastava lähtekliendi olem, kellega teie tegevusolem on seoses. Saate olla seotud ainult lähtekliendi olemitega, mida kasutatakse andmete ühendamise protsessis.
   - **Kolmandaks**: kui selle tegevuseolemi ja valitud lähtekliendi olemi vaheline seos on juba olemas, on seose nimi kirjutuskaitstud režiimis. Kui sellist seost pole olemas, luuakse uus seos sellel väljal teie nimega.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Olemi seose määratlemine.":::

1. Valige **Edasi** järgmise etapi juurde minemiseks. 

1. Valige **tegevuse ühendamise** etapis tegevussündmus ja oma tegevuse algusaeg. 
   - **Kohustuslikud väljad**
      1. **Sündmustegevus**: Väli, mis on selle tegevuse sündmus
      2. **Ajatempel**: Väli, mis tähistab teie tegevuse algusaega.

   - **Valikulised väljad**
      1. **Lisateave**: Väli, kus on selle tegevuse jaoks oluline teave.
      2. **Ikoon**: ikoon, mis tähistab seda tegevusetüüpi kõige paremini.
      3. **Veebiaadress**: Väli, mis sisaldab selle tegevuse kohta teavet sisaldavat URL-i. Näiteks tehingute süsteem, mis on selle tegevuse allikaks. See URL võib olla andmeallika mis tahes väli või seda saab luua uue väljana Power Query teisenduse abil. URL-i andmed talletatakse olemis *Ühendatud tegevus*, mida saab ära kasutada edaspidi kasutades [API-sid](apis.md).
   
   :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Määrake klienditegevuse andmed Ühendatud tegevuse olemis.":::

1. Järgmise etapi juurde liikumiseks klõpsake nuppu **Edasi**. Vvõite valida suvandi **Valmis ja ülevaade**, et salvestada tegevus tüüpiga **Muud**. 

1. Valige etapis **Tegevuse tüüp** tegevuse tüüp ja soovi korral valige, kas soovite mõnda tegevusetüüpi semantiliselt kaardistada, et neid oleks võimalik kasutada Customer Insights muudes alades. Praegu saab *Tellimus* & *Müügitellimuste rida* tegevustüübid pärast väljade kaardistamisega nõustumist semantiliselt kaardistada. Kui tegevustüüp pole uue tegevuse jaoks oluline, võite kohandatud tegevustüübi jaoks valida valiku *Muu* või *Loo uus*.

1. Järgmise etapi juurde liikumiseks klõpsake nuppu **Edasi**. 

1. Kontrollige **Vaata üle** etapis oma valikuid. Minge tagasi ükskõik millise eelmise etapi juurde ja värskendage vajadusel teavet.

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="Vaadake läbi tegevuse määratud väljad.":::
   
1. Valige **Salvestage tegevus**, et muudatused rakendada ja seejärel valige **Valmis**, et minna tagasi **Andmed** > **Tegevused** juurde. Siin näete, millised tegevused on seatud ajaskaalal kuvamiseks. 

1. Valige **Tegevused** lehel suvand **Käita** tegevuse töötlemiseks. 

> [!TIP]
> Ülesannete/protsesside jaoks on [kuus tüüpi olekuid](system.md#status-types). Lisaks sõltuvad enamikud protsessid [muudest järgnevatest protsessidest](system.md#refresh-policies). Kogu töö edenemise üksikasjade nägemiseks saate valida protsessi oleku. Kui olete valinud ühe tööülesande jaoks suvandi **Kuva üksikasjad**, näete järgmist lisateavet: töötlemise aeg, viimane töötlemise kuupäev ja kõik ülesandega seotud tõrked ja hoiatused.


## <a name="manage-existing-activities"></a>Olemasolevate tegevuste haldamine

Suvandil **Andmed** > **Tegevused** saate vaadata salvestatud tegevusi ja hallata neid. Iga tegevust tähistab rida, mis sisaldab ka lähteallika, olemi- ja tegevustüübi üksikasju.

Järgmised toimingud on saadaval tegevuse valimiseks. 

- **Redigeeri**: avab tegevuse seadistuse läbivaatuse etapi. Selles etapis saate muuta kõiki praeguseid konfiguratsioone. Pärast konfiguratsiooni muutmist valige **Salvesta tegevus** ja seejärel valige **Käivita** käsk muudatuste töötlemiseks.

- **Nimeta ümber**: avab dialoogi, kuhu sisestada valitud tegevusele muu nimi. Vajutage nuppu **Salvesta**, et muudatused rakendada.

- **Kustuta**: Avab dialoogi, mis kinnitab valitud tegevuse kustutamise. Korraga saate kustutada ka mitu tegevust, valides tegevused ja seejärel valides kustutamisikooni. Valige käsk **Kustuta**, et kinnitada kustutamine.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
