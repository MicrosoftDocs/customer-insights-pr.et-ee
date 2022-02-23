---
title: Semantilised vastendused (Eelversioon)
description: Ülevaade semantilisest vastendusest ja kuidas neid kasutada.
ms.date: 12/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
ms.openlocfilehash: 08b257b97704b219bb3277042516e00deb886a49
ms.sourcegitcommit: 58651d33e0a7d438a2587c9ceeaf7ff58ae3b648
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 12/02/2021
ms.locfileid: "7881825"
---
# <a name="semantic-mappings-preview"></a>Semantilised vastendused (Eelversioon)

Semantilised vastendused lasevad teil vastendada oma mittetegevuseandmed eelmääratletud skeemidega. Need skeemid aitavad sihtrühma ülevaadetel oma andmeatribuute paremini mõista. Semantiline vastendamine ja esitatud andmed võimaldavad publiku ülevaadetes uusi ülevaateid ja funktsioone. Tegevuseandmete vastendamiseks skeemidega vaadake [tegevuste](activities.md) dokumentatsioon üle.

**Semantilised vastendused on praegu lubatud ärikontodel põhinevates keskkondades**. *ContactProfile* on ainus semantilise vastenduse tüüp, mis on praegu sihtrühma ülevaadetes saadaval.

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>ContactProfile'i semantilise olemi vastenduse määratlemine

1. Avage sihtrühma ülevaadetes **Andmed** > **Semantilised vastendused (eelvaade)**.

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

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="manage-existing-semantic-mappings"></a>Olemasolevate semantilise vastenduste haldamine

Väljal **Andmed** > **Semantilised vastendusel (eelversioon)** saate vaadata kõiki salvestatud semantilisi vastendusi ja neid hallata. Iga semantilist vastendust tähistab omaette rida. Saate otsida üksikasju lähteolemi, semantilise tüübi, vastendustüübi ja selle oleku kohta.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="Suvandid semantilise vastenduste haldamiseks.":::

- **Redigeeri**: Avab arvustuse etapis semantilise vastenduse seadistuse konfiguratsiooni. Saate praegust konfiguratsiooni muuta. Muudatuste töötlemiseks valige **Salvesta** ja **Käivita** .

- **Värskenda**: Värskendab valitud semantilise vastenduse selle konfiguratsiooni kuuluvate olemite kõige uuemate andmetega. Iga antud semantilise vastenduse värskendamisel värskendatakse kõik sama tüüpi semantilised vastendused.

- **Nimeta ümber**: Avab dialoogi, kuhu saate valitud semantilise vastenduse jaoks sisestada teistsuguse nime. Vajutage nuppu **Salvesta**, et muudatused rakendada.

- **Kustuta**: Avab dialoogi, mis kinnitab valitud semantilise vastenduse kustutamist. Korraga saate kustutada ka mitu semantilist vastendust, valides semantilised vastendused ja kustutamise ikooni. Valige käsk **Kustuta**, et kinnitada kustutamine.

## <a name="use-a-contactprofile-semantic-entity-mapping-to-create-contact-level-activities"></a>Kontaktitaseme tegevuste loomiseks kasutage ContactProfile semantilist olemi vastendust

Pärast *ContactProfile* semantilise olemi vastenduse loomist saate jäädvustada kontaktide tegevusi. See võimaldab teil näha tegevuse ajaskaalal ettevõtte, mille kontakt vastutas iga tegevuse eest. Enamik juhiseid järgib tüüpilist tegevuste vastendamise konfiguratsiooni.

   > [!NOTE]
   > Kontaktitaseme tegevuste toimimiseks peavad teil olema nii AccountID kui **ka** **ContactID** atribuudid iga tegevuseandmete kirje kohta.

1. [Määratlege *ContactProfile* semantilise olemi vastendamine.](#define-a-contactprofile-semantic-entity-mapping) Ja käivitage semantiline kaardistamine.

1. Avage sihtrühmaülevaadetes jaotis **Andmed** > **Tegevused**.

1. Uue tegevuse loomiseks valige **Lisa** tegevus.

1. Nimetage tegevus, valige lähtetegevuse olem ja valige tegevuse olemi primaarvõti.

1. Looge **jaotises Seosed** kaudne seos oma tegevuse lähteandmete ja kontode vahel, kasutades oma kontaktandmeid vahendajana. Lisateavet vt [otse- ja kaudsete seoste teed](relationships.md#relationship-paths).
   - Ostuga seotud tegevuse *näidissuhe*:
      - **Ostud Lähtetegevuse andmed** > **Kontaktandmed** atribuudil **ContactID**
      - **Kontaktandmete** > **konto andmed** atribuudi **kontoID kohta**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="Näidissuhte häälestus.":::

1. Pärast seoste seadistamist valige **Edasi ja viige tegevuse** vastendamise konfiguratsioon lõpule. Tegevuse loomise üksikasjalikke samme leiate teemast [Tegevuse määratlemine](activities.md).

1. Käivitage oma tegevuste vastended.

1. Teie kontaktitaseme tegevused on nüüd nähtavad teie kliendi ajaskaalal.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="Lõpptulemus pärast kontaktitegevuste konfigureerimist":::

### <a name="contact-level-activity-timeline-filtering"></a>Kontaktitaseme tegevuse ajaskaala filtreerimine

Pärast kontaktitaseme tegevuste vastendamise konfigureerimist ja selle käivitamist värskendatakse teie klientide tegevuse ajaskaalat. See sisaldab nende ID-sid või nimesid, olenevalt teie *ContactProfile* konfiguratsioonist, tegevuste jaoks, mida nad tegutsesid. Saate filtreerida tegevusi ajaskaalal olevate kontaktide kaupa, et näha konkreetseid teid huvitatud kontakte. Lisaks näete kõiki tegevusi, mis pole konkreetsele kontaktile määratud, valides **Kontaktiga vastendusse mitte vastetuna tegevused**.

   :::image type="content" source="media/Contact_Activities3.png" alt-text="Kontaktitaseme tegevuste jaoks saadaolevad filtreerimissuvandid.":::

[!INCLUDE[footer-include](../includes/footer-banner.md)]
