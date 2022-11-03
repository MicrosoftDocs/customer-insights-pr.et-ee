---
title: Kliendi- või ärikontaktide tegevused
description: Määratlege kliendi- või ärikontaktide tegevused ja vaadake neid kliendiprofiilide ajaskaalal.
ms.date: 10/26/2022
ms.subservice: audience-insights
ms.reviewer: v-wendysmith
ms.topic: conceptual
author: srivas15
ms.author: shsri
manager: shellyha
searchScope:
- ci-entities
- ci-customer-card
- ci-relationships
- ci-activities
- ci-activities-wizard
- ci-measures
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: d8caa477278f04c3a0a95ced15f4bea2a22aa8cd
ms.sourcegitcommit: da6a2d189edacc8f2c0f2abedcb28245f26fe74c
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 10/27/2022
ms.locfileid: "9723776"
---
# <a name="customer-or-business-contact-activities"></a>Kliendi- või ärikontaktide tegevused

Kliendi tegevused on klientide või ärikontaktide toimingud või sündmused. Näiteks kanded, kõne kestuse tugi, veebisaidi arvustused, ostud või tagastused. Need tegevused sisalduvad ühes või mitmes andmeallikas. Klientide statistika abil konsolideerige oma klienditegevused nendest [andmeallikatest](data-sources.md) ja seostage need kliendiprofiilidega. Need tegevused kuvatakse kronoloogiliselt kliendiprofiili ajaskaalal. Lisage ajaskaala Dynamics 365 rakendustesse kliendikaardi lisandmooduli [lahendusega](customer-card-add-in.md).

## <a name="define-a-customer-activity"></a>Klienditegevuse määratlemine

Olemil peab olema vähemalt üks atribuut tüübiga **Kuupäev**, mis kaasatakse kliendi ajaskaalale. Kui sellist olemit ei leita, siis **Lisa tegevus** funktsioon keelatakse.

1. Avage **Andmetegevused** > **·**.

1. Juhendatud kasutuskogemuse alustamiseks valige **Lisa tegevus.**

1. **Sisestage etapile Tegevusandmed** järgmine teave.

   - **Tegevuse nimi**: valige oma tegevuse nimi.
   - **Tegevuse olem: valige olem**, mis sisaldab kande- või tegevusandmeid.
   - **Primaarvõti**: valige väli, milles tuvastatakse kirje kordumatult. See ei tohiks sisaldada korduvväärtusi, tühjasid väärtusi ega puuduvaid väärtusi.

     > [!NOTE]
     > Iga rea primaarklahv peab jääma andmeallikas värskendamisel ühtlaseks. Kui rea primaarvõtit värskendatakse andmeallikas värskendamisel, loob see väljundi tegevusüksuses duplikaadid. 

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Saate seadistada tegevuse andmed nimega, olemiga ja esmase võtmega.":::

1. Tehke valik **Edasi**.

1. **Valige etapis Seos** käsk Lisa seos **,** et ühendada oma tegevuse andmed vastava kliendikirjega. Selle sammuga visualiseeritakse olemite vaheline ühendus.  

   - **Välisvõti**: välismaine väli teie tegevusüksuses, mida kasutatakse suhte loomiseks teise olemiga.
   - **Olemi nimele**: vastav lähtekliendi olem, millega teie tegevuse olem on seotud. Saate olla seotud ainult lähtekliendi olemitega, mida kasutatakse andmete ühendamise protsessis.
   - **Seose nimi: kui seos selle tegevuse olemi ja valitud lähtekliendi olemi vahel on juba olemas, on seose nimi** kirjutuskaitstud režiimis. Kui sellist seost pole, luuakse uus seos, mille nime sisestate sellel väljal.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Olemi seose määratlemine.":::

   > [!TIP]
   > B2B keskkondades saate valida nii konto olemite kui ka muude olemite vahel. Kui valite konto olemi, seatakse seose tee automaatselt. Muude olemite puhul peate määratlema seose tee ühe või mitme vaheolemi üle, kuni olete jõudnud konto olemini.

1. Valige **seose loomiseks Rakenda**.

1. Tehke valik **Edasi**.

1. Valige **tegevuse ühendamise** etapis tegevussündmus ja oma tegevuse algusaeg.
   - **Kohustuslikud väljad**
      - **Sündmustegevus**: Väli, mis on selle tegevuse sündmus.
      - **Ajatempel**: Väli, mis tähistab teie tegevuse algusaega.

   - **Valikulised väljad**
      - **Lisateave**: Väli, kus on selle tegevuse jaoks oluline teave.
      - **Ikoon**: ikoon, mis tähistab seda tegevusetüüpi kõige paremini.
      - **Veebiaadress**: Väli, mis sisaldab selle tegevuse kohta teavet sisaldavat URL-i. Näiteks tehingute süsteem, mis on selle tegevuse allikaks. See URL võib olla mis tahes andmeallikas väli või selle saab teisenduse Power Query abil konstrueerida uue väljana. URL-i andmed talletatakse olemis *Ühendatud tegevus*, mida saab ära kasutada edaspidi kasutades [API-sid](apis.md).

   - **Kuva ajajoonel**
      - Märkige, kas soovite kuvada seda tegevust kliendiprofiilide ajaskaala vaates. Kui soovite tegevuse ajaskaalal kuvada, valige **Jah**, tegevuse peitmiseks valige **Ei**.

      :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Määrake klienditegevuse andmed Ühendatud tegevuse olemis.":::

1. Tegevuse tüübi valimiseks valige Edasi või valige **Lõpeta** ja vaadake üle **, et salvestada tegevus, mille tegevuse tüübiks on määratud** Muu **.**

1. Valige etapis **Tegevuse tüüp** tegevuse tüüp ja soovi korral valige, kas soovite mõnda tegevusetüüpi semantiliselt kaardistada, et neid oleks võimalik kasutada Customer Insights muudes alades. Praegu *toetavad tagasiside* tüübid, püsiklienditeenus *, SalesOrder,* *SalesOrderLine* *ja* *Tellimuse* tegevuste tüübid semantikat pärast väljade vastendamisega nõustumist. Kui tegevustüüp pole uue tegevuse jaoks oluline, võite kohandatud tegevustüübi jaoks valida valiku *Muu* või *Loo uus*.

1. Tehke valik **Edasi**.

1. Kontrollige **Vaata üle** etapis oma valikuid. Minge tagasi mõne eelmise toimingu juurde ja vajadusel värskendage teavet.

1. Valige **Salvestage tegevus**, et muudatused rakendada ja seejärel valige **Valmis**, et minna tagasi **Andmed** > **Tegevused** juurde. Kuvatakse loodud tegevus.

1. Pärast kõigi tegevuste loomist valige **nende töötlemiseks käsk Käivita**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-customer-activities"></a>Olemasolevate klienditegevuste haldamine

Avage **andmetegevused** > **·**, et vaadata salvestatud tegevusi, nende lähteolemit, tegevuse tüüpi ja seda, kas need on kliendi ajaskaalale kaasatud. Saate sortida tegevuste loendi mis tahes veeru järgi või kasutada otsinguvälja, et leida tegevus, mida soovite hallata.

Valige saadaolevate toimingute vaatamiseks tegevus.

- **Redigeerige** tegevust selle konfiguratsiooni muutmiseks. Konfiguratsioon avaneb ülevaatuse etapis. Pärast konfiguratsiooni muutmist valige **Salvesta tegevus** ja seejärel valige **Käivita** käsk muudatuste töötlemiseks.
- **Nimetage** tegevus ümber. Vajutage nuppu **Salvesta**, et muudatused rakendada.
- **Kustutage** tegevus. Korraga mitme tegevuse kustutamiseks valige tegevused ja seejärel **Kustuta**. Kinnitage kustutamine.

## <a name="view-activity-timelines-on-customer-profiles"></a>Tegevuse ajaskaala kuvamine kliendiprofiilides

1. Kui tegite tegevuse konfiguratsioonis valiku Kuva tegevuse ajaskaalal **, minge jaotisse** Kliendid **ja valige kliendiprofiil, et vaadata kliendi tegevusi** jaotises Tegevuse ajaskaala **.**

   :::image type="content" source="media/Activity_Timeline1.PNG" alt-text="Konfigureeritud tegevuste kuvamine kliendiprofiilides.":::

1. Tegevuste filtreerimiseks tegevuste ajaskaalal tehke järgmist.

   - Valige üks või mitu tegevuste ikooni, et täpsustada tulemusi nii, et need hõlmaksid ainult valitud tüüpe.

     :::image type="content" source="media/Activity_Timeline2.PNG" alt-text="Tegevuste filtreerimine ikoonide abil tüübi järgi.":::

   - Valige **Filtreeri**, et avada filtripaneel, et konfigureerida ajaskaalafiltrid. Filtreerige tegevuse tüübi *ja/või* kuupäeva *järgi*. Valige suvand **Rakenda**.

     :::image type="content" source="media/Activity_Timeline3.PNG" alt-text="Filtripaneeli abil saate konfigureerida filtri tingimusi.":::

> [!NOTE]
> Kliendiprofiilist lahkudes eemaldatakse tegevuse filtrid. Peate neid rakendama iga kord, kui avate kliendiprofiili.

## <a name="define-a-contact-activity"></a>Kontaktitegevuse määratlemine

Ärikontode (B-st B-ni) puhul kasutage *kontaktide tegevuste jäädvustamiseks olemit ContactProfile*. Konto tegevuste ajaskaalal näete, milline kontakt iga tegevuse eest vastutas. Enamik samme järgib klienditegevuse vastendamise konfiguratsiooni.

   > [!NOTE]
   > Kontaktitaseme tegevuse *määratlemiseks tuleb luua olem ContactProfile* kas ühtse kontaktiprofiilina [või](data-unification-contacts.md) semantilise vastendamise [kaudu](semantic-mappings.md#define-a-contactprofile-semantic-entity-mapping).
   >
   > Teil peavad tegevusandmetes iga kirje jaoks olema nii atribuudid AccountID kui ka **ContactID** **.**
  
1. Avage **Andmetegevused** > **·**.

1. Valige **Lisa tegevus.**

1. **Sisestage etapile Tegevusandmed** järgmine teave.

   - **Tegevuse nimi**: valige oma tegevuse nimi.
   - **Tegevuse olem: valige olem**, mis sisaldab kande- või tegevusandmeid.
   - **Primaarvõti**: valige väli, milles tuvastatakse kirje kordumatult. See ei tohiks sisaldada korduvväärtusi, tühjasid väärtusi ega puuduvaid väärtusi.

     > [!NOTE]
     > Iga rea primaarklahv peab jääma andmeallikas värskendamisel ühtlaseks. Kui rea primaarvõtit värskendatakse andmeallikas värskendamisel, loob see väljundi tegevusüksuses duplikaadid. 


1. **Looge etapis Seosed** kaudne seos tegevuse lähteandmete ja kontode vahel, kasutades oma kontaktandmeid vahendajana. Lisateavet leiate teemast [Otsesed ja kaudsed seoseteed](relationships.md#relationship-paths).
   - Ostudeks *nimetatava* tegevuse näidisseos:
      - **Ostud Allikas Tegevus Andmed** > **Kontaktandmed** atribuudil **ContactID**
      - **Kontaktandmed** > **Konto Andmed** atribuudil **AccountID**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="Näide seose seadistusest.":::

1. Pärast seoste seadistamist valige **Edasi** ja viige lõpule tegevuste kaardistamise konfiguratsioon. Tegevuse loomise üksikasjalikud juhised leiate teemast [Klienditegevuse](#define-a-customer-activity) määratlemine.

1. Käitage oma tegevuste vastendusi.

1. Teie kontaktitaseme tegevused on nüüd nähtavad teie kliendi ajaskaalal.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="Lõpptulemus pärast kontakttegevuste konfigureerimist":::

## <a name="contact-level-activity-timeline-filtering"></a>Kontaktitaseme tegevuse ajaskaala filtreerimine

Pärast kontaktitaseme tegevuste kaardistamise konfigureerimist ja käitamist värskendatakse teie klientide tegevuste ajaskaalat. See sisaldab nende ID-sid või nimesid, olenevalt teie *ContactProfile’i* konfiguratsioonist, tegevuste jaoks, millega nad tegutsesid. Saate filtreerida tegevusi ajaskaalal olevate kontaktide järgi, et näha konkreetseid kontakte, kellest olete huvitatud. Lisaks saate vaadata kõiki tegevusi, mis pole konkreetsele kontaktile määratud, valides **Kontaktiga** vastendamata tegevused.

   :::image type="content" source="media/Contact_Activities3.png" alt-text="Kontaktitaseme tegevuste jaoks saadaolevad filtreerimissuvandid.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
