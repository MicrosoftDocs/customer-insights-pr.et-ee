---
title: Semantilised vastendused (Eelversioon)
description: Ülevaade semantilisest vastendusest ja kuidas neid kasutada.
ms.date: 11/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
ms.openlocfilehash: f23c622572ff9f967eca07de7898419d1ffc18b0
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 11/02/2021
ms.locfileid: "7731938"
---
# <a name="semantic-mappings"></a>Semantilised vastendused

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]
