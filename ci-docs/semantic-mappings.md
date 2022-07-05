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
ms.openlocfilehash: b3a0643ab71c98ce212f4e4581a584d8382c67eb
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9083139"
---
# <a name="semantic-mappings-preview"></a>Semantilised vastendused (eelversioon)

Semantilised vastendused lasevad teil vastendada oma mittetegevuseandmed eelmääratletud skeemidega. Need skeemid aitavad Customer Insightsil teie andmeatribuute paremini mõista. Semantiline vastendamine ja esitatud andmed võimaldavad Customer Insightsis uusi ülevaateid ja funktsioone. Tegevuseandmete vastendamiseks skeemidega vaadake [tegevuste](activities.md) dokumentatsioon üle.

**Semantilised vastendused on praegu lubatud ärikontodel põhinevates keskkondades**. *ContactProfile* on ainus semantilise vastenduse tüüp, mis on praegu saadaval Customer Insightsis.

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>ContactProfile'i semantilise olemi vastenduse määratlemine

1. **Avage jaotis Andme** > **Semantilised vastendused (eelvaade)**.

1. Juhendava kogemus käivitamiseks valige **Lisa semantiline vastendus**.

1. Määrake **Olemi andmete** sammus järgmiste väljade väärtused:

   - **Semantilise olemite vastendamise nimi**: Sisestage oma semantilise olemi vastendamise nimi.
   - **Lähteolem**: Valige olem, mis sisaldab kontaktandmeid.
   - **Peamine võti**: Valige väli, mis tuvastab kontakti kirje kordumatult. See ei tohiks sisaldada korduvväärtusi, tühjasid väärtusi ega puuduvaid väärtusi.

   :::image type="content" source="media/Semantic_Mapping_Wizard1.png" alt-text="Saate seadistada semantilise olemi vastenduse nime, lähteolemi ja peamise võtme.":::

1. Jätkamiseks valige **Edasi**.

1. Konfigureerige **Seose** sammus üksikasjad, et ühendada oma kontaktandmed vastava konto andmetega. Selle sammuga visualiseeritakse olemite vaheline ühendus.  

   Seose teekondi saab rakendada kahte tüüpi: **Otseseosed** ja **Kaudsed seosed**. Lisateabe saamiseks minge [Otseseose ja kaudse seose teekonnad](relationships.md#relationship-paths).

   1. Valige **Seose lisamine**, konfigureerige seos.
   1. Valige lähteolemist atribuut, mis ühendab teie kontaktiolemi mõne muu olemiga.
   1. Valige olem, mida soovite oma kontaktolemiga ühendada. Olemi saate valida **Konto olemite** või **Vahepealsete olemite** jaotistes. Kui valite eeldatava olemi, peate määratlema teise seose sihtkonto olemiga ühenduse loomiseks.

      :::image type="content" source="media/Semantic_Mapping_Wizard2.png" alt-text="Valige Konto olem või Vahepealne olem.":::

   1. Sisestage **Seose nimi**. Kui teie olemite vaheline seos on juba olemas, on seose nimi ainult lugemiseks. Kui seost pole olemas, luuakse uus seos teie pakutava nimega.
   1. Seose konfiguratsiooni lõpuleviimiseks tehke valik **Rakenda**.

   > [!NOTE]
   > Saate konfigureerida rohkem seoseid kontakti olemi ja muude konto olemite vahel, kus on vahepealsed olemid.
   >  :::image type="content" source="media/Semantic_Mapping_Wizard4.png" alt-text="Erinevate seoste visualiseerimine ühendab kontakti olemid konto olemitega.":::

1. Kui olete seose konfiguratsiooniga lõpetanud, valige **Edasi**.

1. Etapis **Semantilise tüübi valimine** valige **Semantiline tüüp**. Praegu on üks **Semantiline tüüp** nimega *ContactProfile*.

1. Vastendage oma andmed näidatud väljadel *ContactProfile* **Semantilise tüübiga**.
   - Nõutud väli: Kontakti ID
   - Valikulised väljad: Eesnimi, Perekonnanimi, Sünnikuupäev, Sugu, Peamine meil ja Peamine telefon

   :::image type="content" source="media/Semantic_Mapping_Wizard5.png" alt-text="Vastendage oma kontakti andmeatribuudid esitatud nõutavate ja valikuliste väljadega.":::

1. Jätkamiseks valige **Edasi**.

1. Vaadake **Arvustuse** etapis semantilise vastenduse konfiguratsiooni. Vastava jaotise puhul muudatuste tegemiseks valige **Redigeeri**.

1. Valige **Salvesta**, et salvestada enda uus **Semantiline vastendus**.

1. Pärast salvestamist saate valida semantilise vastenduse protsessi **Käitamine** või valida suvandi **Sulge**, et salvestada oma semantiline vastendus ilma seda töötlemata.

1. Semantilise vastenduse hilisemaks käivitamiseks valige semantiline vastendus ja valige **Värskenda**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-semantic-mappings"></a>Olemasolevate semantilise vastenduste haldamine

Väljal **Andmed** > **Semantilised vastendusel (eelversioon)** saate vaadata kõiki salvestatud semantilisi vastendusi ja neid hallata. Iga semantilist vastendust tähistab omaette rida. Saate otsida üksikasju lähteolemi, semantilise tüübi, vastendustüübi ja selle oleku kohta.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="Suvandid semantilise vastenduste haldamiseks.":::

- **Redigeeri**: Avab arvustuse etapis semantilise vastenduse seadistuse konfiguratsiooni. Saate praegust konfiguratsiooni muuta. Muudatuste töötlemiseks valige **Salvesta** ja **Käivita** .

- **Värskenda**: Värskendab valitud semantilise vastenduse selle konfiguratsiooni kuuluvate olemite kõige uuemate andmetega. Iga antud semantilise vastenduse värskendamisel värskendatakse kõik sama tüüpi semantilised vastendused.

- **Nimeta ümber**: Avab dialoogi, kuhu saate valitud semantilise vastenduse jaoks sisestada teistsuguse nime. Vajutage nuppu **Salvesta**, et muudatused rakendada.

- **Kustuta**: Avab dialoogi, mis kinnitab valitud semantilise vastenduse kustutamist. Korraga saate kustutada ka mitu semantilist vastendust, valides semantilised vastendused ja kustutamise ikooni. Valige käsk **Kustuta**, et kinnitada kustutamine.

## <a name="use-a-contactprofile-semantic-entity-mapping-to-create-contact-level-activities"></a>KontaktProfiili semantilise olemi vastenduse kasutamine kontaktitaseme tegevuste loomiseks

Pärast ContactProfile *semantilise olemi vastenduse loomist* saate jäädvustada kontaktide tegevusi. See võimaldab teil näha tegevuse ajaskaalal kontot, mille eest kontakt iga tegevuse eest vastutas. Enamik samme järgib tüüpilist tegevuse vastendamise konfiguratsiooni.

   > [!NOTE]
   > Kontaktitaseme tegevuste toimimiseks peavad teie tegevusandmetes iga kirje jaoks olema nii AccountID **kui** ka **ContactID** atribuudid.

1. [Määratlege *ContactProfile* semantiline olemi vastendus.](#define-a-contactprofile-semantic-entity-mapping) Ja käivitage semantiline kaardistamine.

1. **Avage jaotis Andmetegevused** > **·**.

1. Uue tegevuse loomiseks valige **Lisa tegevus**.

1. Nimetage tegevus, valige lähtetegevuse olem ja valige tegevuse olemi primaarvõti.

1. **Looge etapis Seosed** kaudne seos oma tegevuste lähteandmete ja kontode vahel, kasutades oma kontaktandmeid vahendaja olemina. Lisateabe saamiseks vaadake [otseseid ja kaudseid seoseteid](relationships.md#relationship-paths).
   - Näite seos tegevuse *kohta nimega Ostud*:
      - **Ostude lähtetegevuse andmed atribuudil** > **·** **ContactID**
      - **Kontaktandmete** > **konto andmed** atribuudil **AccountID**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="Näidissuhte häälestus.":::

1. Pärast seoste seadistamist valige **Edasi** ja viige lõpule tegevuse vastendamise konfiguratsioon. Tegevuse loomise üksikasjalikke juhiseid leiate teemast [Tegevuse](activities.md) määratlemine.

1. Käivitage oma tegevuse vastendused.

1. Teie kontaktitaseme tegevused on nüüd nähtavad teie kliendi ajaskaalal.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="Lõpptulemus pärast kontaktitegevuste konfigureerimist":::

### <a name="contact-level-activity-timeline-filtering"></a>Kontakttaseme tegevuse ajaskaala filtreerimine

Pärast kontaktitaseme tegevuste vastendamise konfigureerimist ja käitamist värskendatakse teie klientide tegevuse ajaskaalat. See sisaldab nende ID-sid või nimesid, sõltuvalt teie *ContactProfile* konfiguratsioonist, tegevuste jaoks, millega nad tegutsesid. Tegevusi saate ajaskaalal kontaktide järgi filtreerida, et näha konkreetseid kontakte, kellest olete huvitatud. Lisaks saate vaadata kõiki tegevusi, mis pole määratud kindlale kontaktile, valides **tegevused, mis pole kontaktiga** vastendatud.

   :::image type="content" source="media/Contact_Activities3.png" alt-text="Kontaktitaseme tegevuste jaoks saadaolevad filtreerimissuvandid.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
