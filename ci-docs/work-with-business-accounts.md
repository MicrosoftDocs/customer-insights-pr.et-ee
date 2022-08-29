---
title: Ärikontodega töötamine
description: Lisateavet ärikontode kui peamise sihtrühma kohta leiate jaotisest Dynamics 365 Customer Insights.
ms.date: 10/19/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.custom: intro-internal
ms.author: wimohabb
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-semantic-mapping
- ci-connections
- customerInsights
ms.openlocfilehash: abb77a720ab737520a905b0c93b65573e669109f
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303911"
---
# <a name="work-with-business-accounts"></a>Ärikontodega töötamine

See Dynamics 365 Customer Insights võimaldab teil konfigureerida oma keskkonda erinevate peamiste sihtrühmade jaoks: üksiktarbijad (B-kuni-C) ja ärikontod (B-B). B2C stsenaariumide puhul on andmed üksikisikutele keskendunud. B2B puhul on esmaseks sihtrühmaks kontod – organisatsioonid või ettevõtted – ja kontaktid. See artikkel aitab teil alustada äriettevõtete jaoks mõeldud keskkonnaga. See loetleb Customer Insightsi funktsioonivaldkondade erinevused, sõltuvalt teie keskkonna fookusest. Lisateavet erinevuste kohta leiate funktsioonialade arvustuse dokumentidest. 

## <a name="create-an-environment-for-business-accounts"></a>Ärikonto jaoks keskkonna loomine

Administraatorid saavad [luua olemasolevas organisatsioonis keskkonna](create-environment.md). Uue keskkonna loomise protsessi samm küsib administraatorilt keskkonna esmase sihtrühma kohta. Kui see on esmane seadistamine pärast litsentsi ostmist, aitab juhendatud kogemus esimese keskkonna loomisel.

Seejärel saate [neelata](data-sources.md) äriettevõtete ja seotud kontaktide andmeid kõigist toetatud allikatest pärineva andmeallikana.

 [Ühendage](data-unification.md) oma konto andmed, millele järgnevad teie kontaktandmed, et ühendada kontakt- ja kontoüksused.

## <a name="switch-between-primary-target-audience"></a>Peamise sihtrühma vahel vahetamine

Kui teie asutuses hallatakse keskkondasid üksikklientide ja äriettevõtete jaoks, saate vasakpoolsel paanil valida lüliti abil peamise sihtrühma.

:::image type="content" source="media/switch-primary-target-audience.png" alt-text="Vahetaja, et muuta põhilist sihtrühma eraklientide ja ärikontode vahel.":::

## <a name="supported-feature-areas"></a>Toetatud funktsioonialad

- [Tegevused](activities.md): Kontode ja seotud kontaktide tugi tegevuste loomiseks ja nende ajaskaalal näitamiseks.
- [Seosed](relationships.md): Tegevuse viisard aitab olemite vahel seoseid luua, nii et kontovaates saab kuvada kõik kontaktide tegevused. Kontaktid saavad süvitsi minna, et näha kontaktivaadet ja hierarhiaid saab kasutada ettevõtte tegevuse koondamiseks.
- [Mõõdikud](measures.md): Toetab mõõtmete koostajast ühe arvutusega loodud mõõtmeid. Valikuline säte võimaldab alamkontode ümberarvestust mõõtmete loomisel.
- [Segmendid](segments.md): Toetab segmente, mis luuakse segmendi koostajaga nullist. Segmendid võivad põhineda kontodel või kontaktidel.
- [Andmete neelamine](data-sources.md): Kõik selle ala funktsioonid on äriettevõtete ja üksikklientide jaoks samad.
- B-to-B andmete ühendamine on väga sarnane B-C andmete ühendamisega, kuid sellel on täiendav samm kontaktide ühendamiseks pärast konto ühendamist. Vaadake [teemat Ettevõtte kontod (B-B)](data-unification.md).
- [Rikastus](enrichment-hub.md): Teatud rikastustüübid on saadaval ainult üksikkliendi stsenaariumide jaoks, teised aga on saadaval ainult ärikontodele.
- [Prognoosid ja kastist välja mudelid](predictions-overview.md): Tehingu voolavuse prognoos sisaldab täiendavaid samme ärikontode jaoks. Muud prognoosid on saadaval ainult üksikklientidele.
- [Aktiveerimine ja eksport](export-destinations.md): Ekspordid on saadaval nii äriettevõtetele kui ka üksikklientidele. Mõne ekspordi jaoks on vaja lisakonfiguratsiooni ja aluseks olevatesse segmentidesse kavandatud kontaktteavet, et see kehtiks ärikontode jaoks.
- [Süsteemi seaded](system.md) ja [kasutajate haldus](permissions.md): Kõik selle ala funktsioonid on ärikontode ja üksikklientide jaoks samad.

[!INCLUDE [footer-include](includes/footer-banner.md)]
