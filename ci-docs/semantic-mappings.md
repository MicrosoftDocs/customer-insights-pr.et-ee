---
title: Semantilised vastendused (eelversioon)
description: Ülevaade semantilisest vastendusest ja kuidas neid kasutada.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.reviewer: v-wendysmith
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- customerInsights
ms.openlocfilehash: 8780c11c8b091717349f0fd75a36b99c3a63ab49
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303871"
---
# <a name="semantic-mappings-preview"></a>Semantilised vastendused (eelversioon)

> [!NOTE]
> Leht **Semantilised vastendused** on saadaval ainult ärikeskkondade jaoks (B-B), kus kontaktiprofiilid on selle lehe abil juba loodud. Saate jätkata individuaalsete kontaktiprofiilide loomist ja haldamist, kasutades **lehte Semantilised vastendused**. Või ühendage oma kontaktandmed [,](data-unification-contacts.md) et eemaldada duplikaadid, tuvastada vasteid olemite lõikes ja luua üks ühtne kontaktiprofiil. Seejärel saate kontaktitasemel tegevuste loomiseks kasutada ühtset kontaktiprofiili.

Semantilised vastendused lasevad teil vastendada oma mittetegevuseandmed eelmääratletud skeemidega. Need skeemid aitavad Customer Insightsil teie andmeatribuute paremini mõista. Semantiline kaardistamine ja esitatud andmed võimaldavad Customer Insightsis uusi ülevaateid ja funktsioone. Tegevuseandmete vastendamiseks skeemidega vaadake [tegevuste](activities.md) dokumentatsioon üle.

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

1. Vastendage oma kontakti ID *ContactProfile’i* semantilise tüübiga **Contact ID**. Soovi korral vastendage muud väljad (nt eesnimi, perekonnanimi, sugu või meil).

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

[!INCLUDE [footer-include](includes/footer-banner.md)]
