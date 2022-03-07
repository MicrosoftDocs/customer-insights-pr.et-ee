---
title: Alustage ärikontodega peamise sihtrühmana
description: Õppige ärikontode kohta peamise sihtrühmana Dynamics 365 Customer Insights abil.
ms.date: 10/19/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.custom: intro-internal
ms.author: wimohabb
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-semantic-mapping
- ci-connections
- customerInsights
ms.openlocfilehash: 88882dc727c37262c9f204fbc8049abe17bd21a3
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 02/25/2022
ms.locfileid: "8353538"
---
# <a name="work-with-business-accounts-in-audience-insights"></a>Ärikontodega töötamine sihtrühma ülevaadetes

Sihtrühma ülevaadete võimalus rakenduses Dynamics 365 Customer Insights võimaldab teil konfigureerida oma keskkonda erinevate esmaste sihtrühmade jaoks: eratarbijad (B2C) ja ärikontod (B2B). B2C stsenaariumide puhul on andmed üksikisikutele keskendunud. B2B puhul on esmaseks sihtrühmaks kontod – organisatsioonid või ettevõtted – ja kontaktid. See artikkel aitab teil alustada äriettevõtete jaoks mõeldud keskkonnaga. Selles on välja toodud erinevused funktsioonivaldkondades, mis on välja toodud sihtrühma ülevaadetes, olenevalt teie keskkonna fookusest. Lisateavet erinevuste kohta leiate funktsioonialade arvustuse dokumentidest. 

## <a name="create-an-environment-for-business-accounts"></a>Ärikonto jaoks keskkonna loomine

Administraatorid saavad [luua olemasolevas organisatsioonis keskkonna](create-environment.md). Uue keskkonna loomise protsessi samm küsib administraatorilt keskkonna esmase sihtrühma kohta. Juhul kui see on pärast litsentsi ostmist sihtrühma ülevaadete algne seadistus, aitab juhendav kogemus luua esimese keskkonna.

Seejärel saate [neelata](data-sources.md) äriettevõtete ja seotud kontaktide andmeid kõigist toetatud allikatest pärineva andmeallikana.

Pärast andmete ühendamist [määrake konto hierarhiad](relationships.md#set-up-account-hierarchies) seose konfiguratsiooni osana. Samuti saate [semantilised vastendused konfigureerida](semantic-mappings.md) kontakti ja konto olemite ühendamiseks. 

## <a name="switch-between-primary-target-audience"></a>Peamise sihtrühma vahel vahetamine

Kui teie asutuses hallatakse keskkondasid üksikklientide ja äriettevõtete jaoks, saate vasakpoolsel paanil valida lüliti abil peamise sihtrühma.

:::image type="content" source="media/switch-primary-target-audience.png" alt-text="Vahetaja, et muuta põhilist sihtrühma eraklientide ja ärikontode vahel.":::

## <a name="supported-feature-areas"></a>Toetatud funktsioonialad

- [Tegevused](activities.md): Kontode ja seotud kontaktide tugi tegevuste loomiseks ja nende ajaskaalal näitamiseks.
- [Seosed](relationships.md): Tegevuse viisard aitab olemite vahel seoseid luua, nii et kontovaates saab kuvada kõik kontaktide tegevused. Kontaktid saavad süvitsi minna, et näha kontaktivaadet ja hierarhiaid saab kasutada ettevõtte tegevuse koondamiseks.
- [Mõõdikud](measures.md): Toetab mõõtmete koostajast ühe arvutusega loodud mõõtmeid. Valikuline säte võimaldab alamkontode ümberarvestust mõõtmete loomisel.
- [Segmendid](segments.md): Toetab segmente, mis luuakse segmendi koostajaga nullist. Uued tehtemärgid võimaldavad segmentide loomisel sisaldada kontohierarhiat.
- [Andmete neelamine](data-sources.md): Kõik selle ala funktsioonid on äriettevõtete ja üksikklientide jaoks samad.
- [Andmete ühendamine](data-unification.md): Kõik selle ala funktsioonid on äriettevõtete ja üksikklientide jaoks samad.
- [Rikastus](enrichment-hub.md): Teatud rikastustüübid on saadaval ainult üksikkliendi stsenaariumide jaoks, teised aga on saadaval ainult ärikontodele.
- [Prognoosid ja kastist välja mudelid](predictions-overview.md): Tehingu voolavuse prognoos sisaldab täiendavaid samme ärikontode jaoks. Muud prognoosid on saadaval ainult üksikklientidele.
- [Aktiveerimine ja eksport](export-destinations.md): Ekspordid on saadaval nii äriettevõtetele kui ka üksikklientidele. Mõne ekspordi jaoks on vaja lisakonfiguratsiooni ja aluseks olevatesse segmentidesse kavandatud kontaktteavet, et see kehtiks ärikontode jaoks.
- [Süsteemi seaded](system.md) ja [kasutajate haldus](permissions.md): Kõik selle ala funktsioonid on ärikontode ja üksikklientide jaoks samad.

