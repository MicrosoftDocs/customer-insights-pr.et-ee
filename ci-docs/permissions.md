---
title: Kasutaja õiguste määramine
description: Lisateave õiguste ja kasutajarollide kohta.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-permissions
- ci-system-security
- customerInsights
ms.openlocfilehash: a59a672b6f7e1e67c2162ea14bb9860df0d551aa
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245414"
---
# <a name="assign-user-permissions"></a>Kasutaja õiguste määramine

Juurdepääs Customer Insightsile on piiratud teie ettevõtte kasutajatega, kelle administraator on rakendusse lisanud. Administraator saab kasutajaid lisada, redigeerida või eemaldada. Kasutaja võib olla üks kasutaja, rühm või rakendus. Kasutajal võib olla kolme tüüpi rolle.

## <a name="viewer"></a>Vaataja

- Tutvuge lehtedel **Avaleht** ja **Segmendid** ülevaadete ning segmentidega.
- Otsige ja filtreerige kliendiprofiile lehel **Kliendid**. Väljad peavad olema otsitavad.
- Lehe **Rikastamine** kuvamine ja sellega tutvumine.
- Olemite avastamine ja eksportimine lehel **Olemid**.
- Vaadake süsteemi protsesside olekut lehel **Süsteem**.
- Kuvage ekspordid **Ekspordid** lehel.
- Installige ja kasutage armatuurlauda **Power BI Customer Insights**.

## <a name="contributor"></a>Kaasautor

- Kõik vaatajatele saadaval õigused.
- Laadige ja teisendage andmeid lehel **Andmeallikad**.
- Lõpetage **andmete ühendamine**, mille tulemuseks on ühtne kliendiprofiili olem.
- Määratlege **Suhted** ja **Tegevused**.
- Looge segmente lehel **Segmendid**.
- Mõõtude loomine lehe **Mõõdud** abil.
- Hallake konfiguratsiooni ja rikastage kliendiprofiile lehel **Rikastamine** (ainult esimese osapoole rikastamine).
- Eksportide haldamine ja loomine kaasautoritega jagatud ühenduste [põhjal](connections.md#allow-contributors-to-use-a-connection-for-exports).

## <a name="admin"></a>Haldus

- Kõik kaasautorile saadaval õigused.
- Muutke lehel Süsteem **sätteid**, sh töökeelt, süsteemiprotsesside ajakavade värskendamist ja diagnostikalogide eksportimist.
- Muutke lehel Turvalisus **sätteid**, sh kasutajaid, API-võtmeid, privaatseid linke ja võtmehoidlat.
- Sisestage klientide lehe otsingu- ja filtrimääratlused lehel **Otsingu- ja filtriregister** (sellele pääseb juurde lehelt **Kliendid**).
- Hallata ühendusi ja lubada neil kasutada teistel kasutajarollidel **Ühendused** lehel.
- Hallake konfiguratsiooni ja rikastage kliendiprofiile lehel **Rikastamine** (kõik rikastamised).
- Eksportide haldamine ja loomine **Ekspordid** lehel.
- **Kliendikaardi lisandmooduli** paigaldamine ja kasutamine.
- Lisage ja kasutage **Power Appsi konnektorit**.
- Lubage [Customer Insightsi API-de](apis.md) kasutamine.
- [Määrake keskkonna omandiõigus](manage-environments.md#change-the-owner-of-an-environment) teisele administraatorile.

## <a name="admin-owner"></a>Administraator (omanik)

- Kõik administraatori käsutuses olevad õigused.
- [Lähtestage ja kustutage](manage-environments.md#reset-an-existing-environment-preview) keskkond.

## <a name="add-users"></a>Lisa kasutajaid

1. Avage **Administraatori turve** > **ja valige** vahekaart **Kasutajad**.

1. Valige **Lisa kasutajad**, et avada paan **Õiguste lisamine/redigeerimine**.

1. **Kasutage otsinguvälja**, et leida kasutaja või rühm, Azure Active Directory kelle soovite lisada. Valige **Roll**, et määrata see kasutajale või rühmale.

1. Valige **Salvesta**. Praegust keskkonda jagatakse automaatselt kasutaja või rühma liikmetega. Kasutajad pääsevad juurde rakendusele Customer Insights ja töötavad vastavalt neile määratud rollile.

## <a name="view-current-permissions"></a>Vaadake praeguseid õigusi

Minge jaotisse **Administraatori** > **turve** ja valige **vahekaart Kasutajad**, et vaadata aktiivsete kasutajate loendit ja nende rollimääranguid. Saate sortida kasutajate loendi mis tahes veeru järgi või kasutada otsinguvälja konkreetse kasutaja leidmiseks.

## <a name="manage-current-users"></a>Praeguste kasutajate haldamine

Avage **Administraatori turve** > **ja valige** vahekaart **Kasutajad**. Kasutajate loendit saate sortida mis tahes veeru järgi või kasutada otsinguvälja, et leida kasutaja, keda soovite hallata.

Valige saadaolevate toimingute vaatamiseks kasutaja.

- **Redigeerimine**, et muuta kasutaja rolli Customer Insightsis. Muudatuse kinnitamiseks valige **Salvesta**.
- **Eemaldage**, et eemaldada kasutaja juurdepääs Customer Insightsile. Valige käsk **Kustuta**, et kinnitada kustutamine.

[!INCLUDE [footer-include](includes/footer-banner.md)]
