---
title: Kasutajaõiguste haldamine
description: Lisateave õiguste ja kasutajarollide kohta.
ms.date: 02/09/2022
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
ms.openlocfilehash: b80f07dfa734f4dd762bd711151a7045f24bed7d
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653563"
---
# <a name="user-permissions"></a>Kasutajaõigused

Lehel **Õigused** saate seadistada rollid ja õigused Customer Insightsi kasutamiseks.

Lehe nägemiseks peavad teil olema administraatori õigused. Õiguste lehele juurdepääsemiseks avage **veebisait AdminSecurityUsers** > **·** > **·**.

Rolle on kolme tüüpi.

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
- Viige lõpule *andmete koondamise* jaotised (**vastendamine**, **vastavusseviimine** ja **ühendamine**), mis loovad koondatud kliendiprofiili olemi.
- Määratlege **Suhted** ja **Tegevused**.
- Looge segmente lehel **Segmendid**.
- Mõõtude loomine lehe **Mõõdud** abil.
- Hallake konfiguratsiooni ja rikastage kliendiprofiile lehel **Rikastamine** (ainult esimese osapoole rikastamine).
- Hallake ja looge ekspordid kaastöötajatega jagatud ühenduste põhjal. [Lisateave selle kohta, kuidas administraatorid lubavad kaastöötajatel kasutada ekspordi jaoks ühendust](connections.md#allow-contributors-to-use-a-connection-for-exports).

## <a name="admin"></a>Haldus

- Kõik kaasautorile saadaval õigused.
- Muutke lehel **Süsteem** sätteid, sealhulgas süsteemiprotsesside töökeel ja värskendamise ajakavad.
- Vaadake ja lisage õigusi lehel **Õigused**.
- Sisestage klientide lehe otsingu- ja filtrimääratlused lehel **Otsingu- ja filtriregister** (sellele pääseb juurde lehelt **Kliendid**).
- Hallata ühendusi ja lubada neil kasutada teistel kasutajarollidel **Ühendused** lehel.
- Hallake konfiguratsiooni ja rikastage kliendiprofiile lehel **Rikastamine** (kõik rikastamised).
- Eksportide haldamine ja loomine **Ekspordid** lehel.
- **Kliendikaardi lisandmooduli** paigaldamine ja kasutamine.
- Lisage ja kasutage **Power Appsi konnektorit**.
- Lubage [Customer Insightsi API-de](apis.md) kasutamine.
- [Keskkonna omandiõiguse](manage-environments.md#change-the-owner-of-an-environment) määramine teisele administraatorile.

## <a name="admin-owner"></a>Administraator (omanik)

- Kõik administraatorile saadaolevad õigused.
- [Keskkonna lähtestamine ja kustutamine](manage-environments.md#reset-an-existing-environment).

## <a name="assign-roles-and-permissions"></a>Rollide ja õiguste määramine

1. **Avage adminSecurity** > **·** > **Users***.

1. Valige **Lisa kasutajad**, et avada paan **Õiguste lisamine/redigeerimine**.

1. Kasutage välja **Otsing** Azure Active Directory kasutaja või rühma leidmiseks, kelle õigusi soovite kohandada. Valige **Roll**, et määrata see kasutajale või rühmale.

1. Valige **Salvesta**. Praegust keskkonda jagatakse automaatselt selle rühma kasutaja või liikmetega, kelle õigusi olete muutnud. Kasutajad pääsevad juurde rakendusele Customer Insights ja töötavad vastavalt neile määratud rollile.

## <a name="view-current-permissions"></a>Vaadake praeguseid õigusi

**Avage veebisait AdminSecurityUsers** > **·** > **·**, et näha, millised rollimääramised on praegu aktiivsed.

- Veerg **Tüüp** määrab ühe kasutaja, rühma või rakenduse. Süsteem toetab üksikuid kasutajaid ja rühmi.
- Rollid on määratletud veerus **Roll**.
- Valige mis tahes veeru pealkiri, et sortida tulemeid selle veeru väärtusega.
- Kasutage lehe ülaservas välja **Otsing** kindlate kasutajate leidmiseks.


[!INCLUDE [footer-include](includes/footer-banner.md)]
