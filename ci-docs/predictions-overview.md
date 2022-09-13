---
title: Prognooside ülevaade
description: Prognoosistsenaariumid ja -valikud, mida rakendus Dynamics 365 Customer Insights hõlmab.
ms.date: 03/24/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 32240c8c43751d8514d38b392f23ef4138d50ee2
ms.sourcegitcommit: 3c7cdfc8bd83ca236e4777240e08a541dc955d34
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 09/07/2022
ms.locfileid: "9411826"
---
# <a name="predictions-overview"></a>Prognooside ülevaade

Dynamics 365 Customer Insights sisaldab mitmesuguseid võimalusi, mis võimendavad tehisintellekti ja masinõpet andmete prognoosimiseks. 

## <a name="out-of-box-models"></a>"Karbist väljas" mudelid

Lihtsaim viis andmete prognoosimisega alustamiseks on eelnevalt määratletud mudelid, mida sageli nimetatakse "karbist väljas" mudeliteks. Need nõuavad ainult teatud andmeid ja struktuuri, et kiiresti ülevaateid saada. Praegu on saadaval järgmised mudelid. 

# <a name="individual-consumers-b-to-c"></a>[Üksikud tarbijad (B-st C-ni)](#tab/b2c)

- [Kliendi eluaja väärtus](predict-customer-lifetime-value.md): ennustab kliendi potentsiaalset tulu kogu suhtluses ettevõttega.
- [Tootesoovitus](predict-product-recommendation.md): soovitab prognoositava tootesoovituste komplekte, mis põhinevad ostukäitumisel ja sarnaste ostuharjumustega klientidel.
- [Kordustellimuste valim](predict-subscription-churn.md): prognoosib, kas kliendi puhul valitseb oht, et ta ei kasuta enam teie ettevõtte kordustellimuse tooteid või teenuseid.
- [Tehingute valim](predict-transactional-churn.md): prognoosib, kas klient ei osta enam teie tooteid või teenuseid teatud aja jooksul.
- [Sentimentanalüüs](sentiment-analysis.md): analüüsige klientide tagasiside meeleolu ja tuvastage sageli mainitud äriaspektid.

# <a name="business-accounts-b-to-b"></a>[Ettevõtte kontod (B-st B-ni)](#tab/b2b)

- [Tehingute valim](predict-transactional-churn.md): prognoosib, kas klient ei osta enam teie tooteid või teenuseid teatud aja jooksul.

---

> [!TIP]
> Soovitame teil regulaarselt värskendada valmis mudeleid värskendatud andmetega, et tagada nende täpne teavitamine teie ärikasutuse juhtumist. Andmeid värskendatakse ad hoc, kui süsteem kasutab uusi või värskendatud andmeallikaid. Kuid mudelid korrigeerivad ainult sel juhul ja jätkavad olemasolevate treeningandmete kasutamist.
>
> Saate konfigureerida **värskenduste ajakava**, määrates konfiguratsioonikogemuses mudeli ümberõppe ajakava. Mudel treenib ja korrigeerib seda ajakava, mida saate igal ajal muuta.

## <a name="azure-machine-learning-integration"></a>Azure’i masinõppe integratsioon

Kui organisatsioon juba kasutab Azure masinõppe eksperimentidel põhinevaid Masinõpe stsenaariume, aitab Customer Insights kohandatud mudelite funktsiooni punkte ühendada. Saate luua töövooge, mis aitavad teil valida andmeid, millest soovite ülevaateid luua ja vastendada tulemused oma ühtsete kliendiprofiilidega. Lisateavet vt teemast [Kohandatud masinõppemudelid](custom-models.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
