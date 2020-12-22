---
title: Kasutajaõiguste haldamine
description: Lisateave õiguste ja kasutajarollide kohta.
ms.date: 10/27/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7de78c0ef71ec5b83870d396de36a7dcabbd14e5
ms.sourcegitcommit: b50c754481d0af6d0cf4b550775d7b31d95846ef
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 12/06/2020
ms.locfileid: "4689215"
---
# <a name="user-permissions"></a>Kasutajaõigused

Lehel **Õigused** saate seadistada rolle ja õigusi sihtrühmaülevaadete kasutamiseks.

Lehe nägemiseks peavad teil olema administraatori õigused. Sihtrühmaülevaadetes õiguste lehe avamiseks minge jaotisse **Haldus** > **Õigused**.

Rolle on kolme tüüpi.

## <a name="viewer"></a>Vaataja

- Tutvuge lehtedel **Avaleht** ja **Segmendid** ülevaadete ning segmentidega.
- Otsige ja filtreerige kliendiprofiile lehel **Kliendid**. Väljad peavad olema otsitavad.
- Lehe **Rikastamine** kuvamine ja sellega tutvumine.
- Olemite avastamine ja eksportimine lehel **Olemid**.
- Vaadake süsteemi protsesside olekut lehel **Süsteem**.
- Eksportige segmendid lehelt **Segmendid**.
- Installige ja kasutage armatuurlauda **Power BI Customer Insights**.

## <a name="contributor"></a>Kaasautor

- Kõik vaatajatele saadaval õigused.
- Laadige ja teisendage andmeid lehel **Andmeallikad**.
- Viige lõpule *andmete koondamise* jaotised (**vastendamine**, **vastavusseviimine** ja **ühendamine**), mis loovad koondatud kliendiprofiili olemi.
- Määratlege **Suhted** ja **Tegevused**.
- Looge segmente lehel **Segmendid**.
- Mõõtude loomine lehe **Mõõdud** abil.
- Hallake konfiguratsiooni ja rikastage kliendiprofiile lehel **Rikastamine** (ainult esimese osapoole rikastamine).

## <a name="administrator"></a>Administraator

- Kõik kaasautorile saadaval õigused.
- Muutke lehel **Süsteem** sätteid, sealhulgas süsteemiprotsesside töökeel ja värskendamise ajakavad.
- Vaadake ja lisage õigusi lehel **Õigused**.
- Sisestage klientide lehe otsingu- ja filtrimääratlused lehel **Otsingu- ja filtriregister** (sellele pääseb juurde lehelt **Kliendid**).
- Määratlege Dynamics 365 Salesi segmendi sihtkohad lehel **Sihtkohtade eksportimine**.
- Hallake konfiguratsiooni ja rikastage kliendiprofiile lehel **Rikastamine** (kõik rikastamised).
- **Kliendikaardi lisandmooduli** paigaldamine ja kasutamine.
- Lisage ja kasutage **Power Appsi konnektorit**.
- Lubage [Customer Insightsi API-de](apis.md) kasutamine.

## <a name="assign-roles-and-permissions"></a>Rollide ja õiguste määramine

1. Avage sihtrühmaülevaadetes jaotis **Haldus** > **Õigused**.

1. Valige **Lisa kasutajad**, et avada paan **Õiguste lisamine/redigeerimine**.

1. Kasutage välja **Otsing** Azure Active Directory kasutaja või rühma leidmiseks, kelle õigusi soovite kohandada. Valige **Roll**, et määrata see kasutajale või rühmale.

1. Valige **Salvesta**. Praegust keskkonda jagatakse automaatselt selle rühma kasutaja või liikmetega, kelle õigusi olete muutnud. Kasutajad pääsevad juurde rakendusele Customer Insights ja töötavad vastavalt neile määratud rollile.

## <a name="view-current-permissions"></a>Vaadake praeguseid õigusi

Minge sihtrühmaülevaadetes jaotisse **Haldus** > **Õigused**, et näha, millised rollimäärangud on praegu aktiivsed.

- Veerg **Tüüp** määrab ühe kasutaja, rühma või rakenduse. Süsteem toetab üksikuid kasutajaid ja rühmi.
- Rollid on määratletud veerus **Roll**.
- Valige mis tahes veeru pealkiri, et sortida tulemeid selle veeru väärtusega.
- Kasutage lehe ülaservas välja **Otsing** kindlate kasutajate leidmiseks.
