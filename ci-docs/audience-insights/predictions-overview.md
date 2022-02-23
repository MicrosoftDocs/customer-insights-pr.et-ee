---
title: Ülevaade toetatud prognoosi stsenaariumidest
description: Prognoosistsenaariumid ja -valikud, mida rakendus Dynamics 365 Customer Insights hõlmab.
ms.date: 12/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 5972d5b191ded7db14e2ebe9a4a26570a8ea60ba
ms.sourcegitcommit: bb1ca84bc38e81fb2ff2961c457384b7beb5b5fa
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 01/15/2022
ms.locfileid: "7978008"
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
- [Sentiment analüüs](sentiment-analysis.md) : Analüüsige klientide tagasiside tundeid ja tuvastage sageli mainitud äriaspektid.

# <a name="business-accounts-b-to-b"></a>[Ettevõtte kontod (B-st B-ni)](#tab/b2b)

- [Tehingute valim](predict-transactional-churn.md): prognoosib, kas klient ei osta enam teie tooteid või teenuseid teatud aja jooksul.

---


## <a name="azure-machine-learning-integration"></a>Azure’i masinõppe integratsioon

Kui organisatsioon juba kasutab Azure masinõppe eksperimentidel põhinevaid Masinõpe stsenaariume, aitab Customer Insights kohandatud mudelite funktsiooni punkte ühendada. Saate luua töövooge, mis aitavad teil valida andmeid, millest soovite ülevaateid luua ja vastendada tulemused oma ühtsete kliendiprofiilidega. Lisateavet vt teemast [Kohandatud masinõppemudelid](custom-models.md).

## <a name="ai-builder-prediction"></a>AI Builder prognoos

Mõnikord on andmekogumid poolikud ja mõned väärtused puuduvad. Customer Insights aitab prognoosida kliendi olemi ja segmentide puuduvaid väärtusi. Lisateavet vt teemast [Osaliste andmete prognooside täiustamine](predictions.md).
