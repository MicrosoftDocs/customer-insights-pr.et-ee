---
title: Teamsi robot Dynamics 365 Customer Insightsi jaoks (eelversioon)
description: Otsige roboti abil Microsoft Teamsis koondatud kliendiprofiile.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: d140ae72578b48091a41005c4acafe03bac540da
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195837"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Teamsi robot Dynamics 365 Customer Insightsi jaoks (eelversioon)

Ühenduge Microsoft Teamsiga, et lasta robotil otsida koondatud kliendiprofiile Teamsi kanalites.

:::image type="content" source="media/teams-bot.png" alt-text="Kliendi kirjet kuvav Teamsi robot":::

## <a name="prerequisites"></a>eeltingimused

- Lisatud vähemalt üks [andmeallikas](data-sources.md).
- [Ühendamisprotsess](data-unification.md) on lõpule viidud.
- Väljad lisatakse otsingu- ja [filtriregistrisse](search-filter-index.md).
- Customer Insights ja Teams on samas organisatsioonis.
- Teie keskkonnas on peamiseks sihtrühmaks seatud üksikkliendid. Ettevõtte kontosid ei toetata.


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElj]

## <a name="configure-the-bot"></a>Boti konfigureerimine

1. Minge **Administraator** > **Ühendused**.
1. Valige Microsoft Teamsi paanil suvand **Seadista**.
1. Teid suunatakse ümber Teamsi alale **Rakendused**. Võite avada Teamsi ja valida alumises vasakus nurgas suvandi **Rakendused** või [hankida selle AppSource’ist](https://go.microsoft.com/fwlink/?linkid=2124104) otse.
1. Otsige mõistet **Customer Insights** ja valige rakendus.
1. Valige suvand **Lisa**.
1. Logige sisse Customer Insightsi Teamsis. Kuvatakse tervitussõnum.

## <a name="things-you-can-do-with-the-bot"></a>Asjad, mida saate botiga teha

Bot pakub ühendatud kliendiprofiilide otsinguvõimalusi.

- Sisestage **otsing**, millele järgneb nimi, meiliaadress või mõni muu väli ühtsel kliendiprofiilil, mis lisatakse otsingu- ja filtreerimisregistrisse.

  Saate tulemuseks olevalt kliendiprofiililt kaardi kuni 15 väljaga. Mitu vastet tagastavad tulemite loendi, kust saate valida soovitud profiili. Täpse vaste otsimiseks lisage otsingutermin jutumärkidesse.

- Kui teie organisatsioonil on samas organisatsioonis mitu Customer Insightsi keskkonda, sisestage **switchinstance**, et valida, millise keskkonnaga soovite roboti ühendada.

- Sisestage märksõna **spikker** boti jaoks saadaolevate käskude loendi kuvamiseks.  

[!INCLUDE [footer-include](includes/footer-banner.md)]