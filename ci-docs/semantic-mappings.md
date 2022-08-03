---
title: Semantilised vastendused (eelversioon)
description: Ülevaade semantilisest vastendusest ja kuidas neid kasutada.
ms.date: 12/01/2021
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- customerInsights
ms.openlocfilehash: 7c9588ac7a132ca6f43cf26ea3a744109a0dd2b8
ms.sourcegitcommit: ad74ace653db9a25fce4343adef7db1c9b0d8904
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183626"
---
# <a name="semantic-mappings-preview"></a>Semantilised vastendused (eelversioon)

Semantilised vastendused lasevad teil vastendada oma mittetegevuseandmed eelmääratletud skeemidega. Need skeemid aitavad Customer Insightsil teie andmeatribuute paremini mõista. Semantiline kaardistamine ja esitatud andmed võimaldavad Customer Insightsis uusi ülevaateid ja funktsioone. Tegevuseandmete vastendamiseks skeemidega vaadake [tegevuste](activities.md) dokumentatsioon üle.

**Semantilised vastendused on praegu lubatud ärikontodel põhinevates keskkondades**. *ContactProfile* on ainus semantilise vastenduse tüüp, mis on praegu Customer Insightsis saadaval.

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>ContactProfile'i semantilise olemi vastenduse määratlemine

1. Avage **jaotis Andmete** > **semantilised vastendused (eelvaade)**.

1. Juhendava kogemus käivitamiseks valige **Lisa semantiline vastendus**.

1. Määrake **Olemi andmete** sammus järgmiste väljade väärtused:

   - **Semantilise olemi vastenduse nimi**: teie semantilise olemi vastenduse nimi.
   - **Lähteolem**: olem, mis sisaldab kontaktandmeid.
   - **Primaarvõti**: väli, mis tuvastab kontaktikirje kordumatult. See ei tohiks sisaldada korduvväärtusi, tühjasid väärtusi ega puuduvaid väärtusi.

   :::image type="content" source="media/Semantic_Mapping_Wizard1.png" alt-text="Saate seadistada semantilise olemi vastenduse nime, lähteolemi ja peamise võtme.":::

1. Tehke valik **Edasi**.

1. Konfigureerige **Seose** sammus üksikasjad, et ühendada oma kontaktandmed vastava konto andmetega. Selle sammuga visualiseeritakse olemite vaheline ühendus.  

   Seose teekondi saab rakendada kahte tüüpi: **Otseseosed** ja **Kaudsed seosed**. Lisateabe saamiseks minge [Otseseose ja kaudse seose teekonnad](relationships.md#relationship-paths).

   1. Seose konfigureerimiseks valige **Lisa** seos.
   1. Valige lähteolemist atribuut, mis ühendab teie kontaktiolemi mõne muu olemiga.
   1. Valige olem, mida soovite oma kontaktolemiga ühendada. Valige olem jaotisest **Konto olemid** või **Vaheüksus**. Kui valite vaheüksuse, määratlege sihtkonto olemiga ühenduse loomiseks teine seos.

      :::image type="content" source="media/Semantic_Mapping_Wizard2.png" alt-text="Valige Konto olem või Vahepealne olem.":::

   1. Sisestage **Seose nimi**. Kui teie olemite vaheline seos on juba olemas, on seose nimi ainult lugemiseks. Kui seost pole olemas, luuakse uus seos teie pakutava nimega.
   1. Seose konfiguratsiooni lõpuleviimiseks tehke valik **Rakenda**.

   > [!NOTE]
   > Saate konfigureerida rohkem seoseid kontakti olemi ja muude konto olemite vahel, kus on vahepealsed olemid.
   
     :::image type="content" source="media/Semantic_Mapping_Wizard4.png" alt-text="Erinevate seoste visualiseerimine ühendab kontakti olemid konto olemitega.":::

1. Tehke valik **Edasi**.

1. Etapis **Semantilise tüübi valimine** valige **Semantiline tüüp**. Praegu on üks **Semantiline tüüp** nimega *ContactProfile*.

1. Vastendage oma kontakti ID *ContactProfile'i* semantilise tüübiga **Contact ID**. Soovi korral vastendage muud väljad (nt eesnimi, perekonnanimi, sugu või meil).

   :::image type="content" source="media/Semantic_Mapping_Wizard5.png" alt-text="Vastendage oma kontakti andmeatribuudid esitatud nõutavate ja valikuliste väljadega.":::

1. Tehke valik **Edasi**.

1. Vaadake ülevaatusetapis **üle** semantilise vastenduse konfiguratsioon. Muudatuste tegemiseks valige **vastava jaotise jaoks Redigeeri**.

1. Valige **Salvesta**.

1. Semantilise vastenduse töötlemiseks valige **Käivita**. Või valige **Sule**, et salvestada oma semantiline vastendus ilma seda töötlemata. Selle hilisemaks käivitamiseks valige semantiline vastendus ja valige **Värskenda**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-semantic-mappings"></a>Olemasolevate semantilise vastenduste haldamine

Avage **jaotis Andmete** > **semantilised vastendused (eelvaade),** et vaadata salvestatud semantilisi vastendusi, nende lähteolemit, semantilist tüüpi, vastenduse tüüpi ja olekut.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="Suvandid semantilise vastenduste haldamiseks.":::

Valige saadaolevate toimingute vaatamiseks semantiline vastendus.
- **Redigeerige** praegust konfiguratsiooni. Muudatuste töötlemiseks valige **Salvesta** ja **Käivita** .
- **Värskendage** semantilist vastendust, et kaasata uusimad andmed. Iga antud semantilise vastenduse värskendamisel värskendatakse kõik sama tüüpi semantilised vastendused.
- **Nimetage semantiline vastendus ümber**. Valige **Salvesta**.
- **Kustutage** semantiline vastendus. Korraga rohkem kui ühe semantilise vastenduse kustutamiseks valige semantilised vastendused ja kustutamise ikoon. Valige käsk **Kustuta**, et kinnitada kustutamine.

## <a name="use-a-contactprofile-semantic-entity-mapping-to-create-contact-level-activities"></a>ContactProfile'i semantilise olemi vastenduse kasutamine kontaktitaseme tegevuste loomiseks

Pärast ContactProfile'i *semantilise olemi vastenduse loomist* saate jäädvustada kontaktide tegevusi. See võimaldab teil konto tegevuste ajaskaalal näha, milline kontakt iga tegevuse eest vastutas. Enamik etappe järgib tüüpilist tegevuse vastendamise konfiguratsiooni.

   > [!NOTE]
   > Kontaktitasemel tegevuste toimimiseks peavad teil tegevuse andmetes olema iga kirje jaoks atribuudid **AccountID** ja **ContactID**.

1. [*Määratlege ContactProfile'i* semantiline olemi vastendus](#define-a-contactprofile-semantic-entity-mapping) ja käivitage semantiline vastendus.

1. Avage **jaotis Andmetegevused** > **·**.

1. Uue tegevuse **loomiseks valige** Lisa tegevus.

1. Pange tegevusele nimi, valige lähtetegevuse olem ja valige tegevuse olemi primaarvõti.

1. **Looge etapis Seosed** kaudne seos oma tegevuse lähteandmete ja kontode vahel, kasutades oma kontaktandmeid vahendajana. Lisateabe saamiseks vaadake [otseste ja kaudsete suhete teid](relationships.md#relationship-paths).
   - Näide seos tegevusele nimega *Ostud*:
      - **Ostud Lähtetegevuse andmed** > **Kontaktandmed** atribuudil **ContactID**
      - **Kontaktandmed** > **Konto andmed** atribuudil **AccountID**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="Seose seadistamise näide.":::

1. Pärast seoste seadistamist valige **Edasi** ja viige tegevuse vastendamise konfiguratsioon lõpule. Tegevuse loomise üksikasjalikud juhised leiate teemast [Tegevuse](activities.md) määratlemine.

1. Käivitage oma tegevuste vastendused.

1. Pärast kontaktitasemel tegevuse vastendamise käivitamist valige **Kliendid**. Kontaktitaseme tegevused kuvatakse teie kliendi ajaskaalal.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="Lõpptulemus pärast kontaktitegevuste konfigureerimist":::

### <a name="contact-level-activity-timeline-filtering"></a>Kontaktitaseme tegevuste ajaskaala filtreerimine

Teie klientide tegevuste ajaskaala sisaldab nende ID-sid või nimesid (olenevalt teie *ContactProfile'i* konfiguratsioonist) tegevuste kohta, mida nad tegid. Filtreerige tegevusi ajaskaalal olevate kontaktide järgi, et näha teid huvitavaid kontakte. Kõigi tegevuste vaatamiseks, mis pole konkreetsele kontaktile määratud, valige **Tegevused, mis pole kontaktiga vastendatud**.

:::image type="content" source="media/Contact_Activities3.png" alt-text="Kontaktitaseme tegevuste jaoks saadaolevad filtreerimissuvandid.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
