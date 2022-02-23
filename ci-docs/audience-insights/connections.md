---
title: Ühendused muude teenustega Customer Insights kaudu.
description: Andmete jagamine muude teenustega.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: overview
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e78e18b75ee9797b5fc76486615992e301e4c650
ms.sourcegitcommit: bb1ca84bc38e81fb2ff2961c457384b7beb5b5fa
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 01/15/2022
ms.locfileid: "7977732"
---
# <a name="connections-preview-overview"></a>Ühenduste (eelversioon) ülevaade

Ühendused on võti andmete jagamise lubamiseks Customer Insights kaudu. Iga ühendus loob andmete jagamise konkreetse teenusega. Ühendused on aluseks [kolmanda osapoole rikastamise konfigureerimiseks](enrichment-hub.md) ja [ekspordi konfigureerimiseks](export-destinations.md). Sama ühendust saab kasutada mitmeid kordi. Näiteks üks ühendus Dynamics 365 Marketing'iga töötab mitme ekspordi jaoks ja ühe Leadspace ühenduse abil saab kasutada mitut rikastamist.

Minge **Administraator** > **Ühendused**, et luua ja vaadata ühendusi.

Vahekaardil **Ühendused** kuvatakse kõik aktiivsed ühendused. Loendis kuvatakse rida iga ühenduse jaoks. 

Vaadake vahekaardil **Avastamine** kiirülevaadet, kirjeldust ja saate teada, mida iga laiendatavuse suvandiga teha.

### <a name="exports"></a>Eksportimised

Uusi ühendusi saavad konfigureerida ainult administraatorid, kuid nad saavad anda kaastöötajatele juurdepääsu olemasolevate ühenduste kasutamiseks. Administraatorid määravad, kuhu andmed võivad minna, kaastöötajad määratlevad koormuse ja sageduse, mis nende vajadustele vastab. Lisateavet leiate teemast [Luba toetajatel kasutada ühendust ekspordi jaoks](#allow-contributors-to-use-a-connection-for-exports).

### <a name="enrichments"></a>Rikastamised

Uusi ühendusi saavad konfigureerida ainult administraatorid, kuid loodud ühendused on alati saadaval nii administraatoritele kui ka kaastöötajatele. Administraatorid haldavad volitusi ja nõustuvad andmete edastamisega. Ühendusi saavad seejärel kasutada rikastamiseks nii administraatorid kui ka kaastöötajad.

## <a name="add-a-new-connection"></a>Uue ühenduse lisamine

Ühenduste lisamiseks peavad teil olema [administraatoriõigused](permissions.md). Kui loote ühenduse muude Microsofti teenustega, siis eeldame, et mõlemad teenused on samas organisatsioonis.

1. Minge **Administraator** > **Ühendused (eelversioon)**.

1. Avage vahekaart **Ühendused**.

1. Valige uue ühenduse loomiseks **Lisa ühendus**. Valige ripploendist, millist tüüpi ühendust soovite luua.

1. Sisestage **Loo ühendus** seadistuse paanil nõutavad üksikasjad. 
   1. **Kuva nimi** ja ühenduse tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.
   1. Täpsed väljad sõltuvad teenusest, millega loote ühenduse. Saate teavet konkreetse ühendusetüübi kohta sihtteenuse artklis.
   1. Kui [kasutate oma võtmehoidlat](use-azure-key-vault.md) saladuste salvestamiseks, aktiveerige **Kasutage võtmehoidlat** ja valige loendist saladus.

1. Uue ühenduse loomiseks valige **Salvesta**.

Samuti saate valida vahekaardi **Tuvastamine** paanil suvandi **Häälestamine**.

### <a name="allow-contributors-to-use-a-connection-for-exports"></a>Luba kaastöötajatel kasutada ühendust ekspordi jaoks

Ekspordiühenduse seadistamisel või redigeerimisel saate valida, millistel kasutajatel on lubatud kasutada seda kindlat ühendust [ekspordi](export-destinations.md)määratlemiseks. Vaikimisi on ühendus saadaval administraatorirollis kasutajatele. Saate seda sätet muuta jaotises **Valige, kes saab seda ühendust kasutada** ja lubada kaastöötaja rollis kasutajatel seda ühendust kasutada.

- Kaastöötajad ei saa ühendust vaadata ega redigeerida. Nad näevad ekspordi loomisel ainult kuvatavat nime ja selle tüüpi.
- Ühenduse jagamisel lubate kaastöötajatel ühendust kasutada. Kaastöötajad näevad ekspordi seadistamisel ühisühendusi. Nad saavad hallata igat eksporti, mis kasutab seda kindlat ühendust.
- Saate seda sätet muuta, hoides ekspordi alles, mille kaastöötajad on juba määratlenud.

## <a name="edit-a-connection"></a>Ühenduse redigeerimine

1. Minge **Administraator** > **Ühendused (eelversioon)**.

1. Avage vahekaart **Ühendused**.

1. Valige redigeeritava ühenduse jaoks vertikaalne ellips.

1. Valige **Redigeeri**.

1. Muutke värskendatavad väärtused ja valige **Salvesta**.

## <a name="remove-a-connection"></a>Eemaldage ühendus

Kui eemaldatav ühendus on kasutusel rikastamise või ekspordi puhul, peate need esmalt lahti võtma või eemaldama. Eemaldamise dialoog juhendab teid vastavalt rikastamise või eksportimise osas. 

Eraldatud rikastamine ja eksport muutuvad passiivseks. Aktiveerite need uuesti, lisades neile teise ühenduse [Rikastamised](enrichment-hub.md) või [Ekspordid](export-destinations.md) lehel.

1. Minge **Administraator** > **Ühendused (eelversioon)**.

1. Avage vahekaart **Ühendused**.

1. Valige eemaldatava ühenduse jaoks vertikaalne ellips.

1. Valige rippmenüüst **Eemalda**. Ilmub kinnituse dialoog.

   1. Kui seda ühendust kasutatakse rikastamiseks või eksportimiseks, valige nupp, et näha, mis seda ühendust kasutab.
      - **Eksport:** Ühenduse eemaldamiseks saate ekspordi eemaldada või katkestada. Ekspordi katkestamiseks saavad administraatorid kasutada **Katkesta** toimingut. See toiming on saadaval nii üksik- kui ka mitme ekspordi jaoks. Ühenduse katkestamisel säilitate ekspordikonfiguratsiooni, kuid seda ei käitata enne, kui failile on lisatud mõni muu ühendus.
      - **Rikastamine:** Ühenduse eemaldamiseks saate rikastamise deaktiveerida või eemaldada. 
   1. Kui ühendusel pole rohkem sõltuvusi, minge tagasi **Administraator** > **Ühendused** ja proovige ühendus uuesti eemaldada.

1. Valige käsk **Eemalda**, et kinnitada kustutamine.

## <a name="set-up-connections-with-secrets-managed-by-your-own-key-vault"></a>Saate seadistada ühendusi saladustega, mida haldab teie oma võtmehoidla.

Mõne ühenduse puhul on vaja saladusi, nagu API-võtmed või paroolid. Mõned ühendused toetavad saladusi, mis on talletatud teie enda võtmehoidlasse. Lisateave toetatud ühenduste kohta ja kuidas seadistada [oma võtmehoidlas publiku ülevaadete jaoks](use-azure-key-vault.md).
