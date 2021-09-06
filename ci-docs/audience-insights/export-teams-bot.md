---
title: Microsoft Teamsi robot
description: Otsige roboti abil Microsoft Teamsis koondatud kliendiprofiile.
ms.date: 04/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 9bf401124b0ffb21b046954056141e7703386d4911f89f34ffc0fcb84bf0f4be
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032477"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Teamsi robot Dynamics 365 Customer Insightsi jaoks (eelversioon)

Ühenduge Microsoft Teamsiga, et lasta robotil otsida koondatud kliendiprofiile Teamsi kanalites.

> [!div class="mx-imgBorder"]
> ![Kliendi kirjet kuvav Teamsi robot.](media/teams-bot.png "Kliendi kirjet kuvav Teamsi robot")

## <a name="prerequisites"></a>Eeltingimused

Boti seadistamiseks ja konfigureerimiseks peavad olema täidetud järgmised eeltingimused.

- Vähemalt üks [andmeallikas on lisatud](data-sources.md).
- [Ühendamisprotsess](data-unification.md) on lõpule viidud.
- [Otsingu ja filtri indeksisse](search-filter-index.md) on lisatud väljad.
- Customer Insights ja Teams on samas organisatsioonis.

## <a name="configure-the-bot"></a>Boti konfigureerimine

1. Avage sihtrühmaülevaadetes jaotis **Haldus** > **Eksportimise sihtkohad**.
1. Valige Microsoft Teamsi paanil suvand **Seadista**.
1. Teid suunatakse ümber Teamsi alale **Rakendused**. Võite avada Teamsi ja valida alumises vasakus nurgas suvandi **Rakendused** või [hankida selle AppSource’ist](https://go.microsoft.com/fwlink/?linkid=2124104) otse.
1. Otsige mõistet **Customer Insights** ja valige rakendus.
1. Valige suvand **Lisa**.
1. Pärast Teamsis Customer Insightsi sisselogimist näete tervitussõnumit ja võite alustada.

## <a name="things-you-can-do-with-the-bot"></a>Asjad, mida saate botiga teha

Bot pakub ühendatud kliendiprofiilide otsinguvõimalusi.

- Sisestage **otsing**, millele järgneb nimi, meiliaadress või mis tahes muu väli ühendatud kliendiprofiilis, mis lisatakse otsingu ja filtri indeksisse.

  Saate tulemuseks olevalt kliendiprofiililt kaardi kuni 15 väljaga. Mitu vastet tagastavad tulemite loendi, kust saate valida soovitud profiili. Täpse vaste otsimiseks saate lisada otsingusõna kahekordsetes jutumärkides.

- Kui teie organisatsioon haldab ühes organisatsioonis mitut Customer Insightsi keskkonda, saate sisestada **switchinstance**, et valida, millise keskkonnaga soovite robotit ühendada.

- Sisestage märksõna **spikker** boti jaoks saadaolevate käskude loendi kuvamiseks.  


[!INCLUDE[footer-include](../includes/footer-banner.md)]