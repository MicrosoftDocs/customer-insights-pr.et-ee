---
title: Ülevaade toetatud prognoosi stsenaariumidest
description: Prognoosistsenaariumid ja -valikud, mida rakendus Dynamics 365 Customer Insights hõlmab.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: get-started
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 57c61895d636273fc90a0ac5a942fd0c9abf583c687ae20621949554e581cdf8
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036004"
---
# <a name="predictions-overview"></a>Prognooside ülevaade

Dynamics 365 Customer Insights sisaldab mitmesuguseid võimalusi, mis võimendavad tehisintellekti ja masinõpet andmete prognoosimiseks. 

## <a name="out-of-box-models"></a>"Karbist väljas" mudelid

Lihtsaim viis andmete prognoosimisega alustamiseks on eelnevalt määratletud mudelid, mida sageli nimetatakse "karbist väljas" mudeliteks. Need nõuavad ainult teatud andmeid ja struktuuri, et kiiresti ülevaateid saada. Praegu on saadaval järgmised mudelid. 
- [Kliendi eluaja väärtus](predict-customer-lifetime-value.md): ennustab kliendi potentsiaalset tulu kogu suhtluses ettevõttega. 
- [Tootesoovitus](predict-product-recommendation.md): soovitab prognoositava tootesoovituste komplekte, mis põhinevad ostukäitumisel ja sarnaste ostuharjumustega klientidel.
- [Kordustellimuste valim](predict-subscription-churn.md): prognoosib, kas kliendi puhul valitseb oht, et ta ei kasuta enam teie ettevõtte kordustellimuse tooteid või teenuseid.
- [Tehingute valim](predict-transactional-churn.md): prognoosib, kas klient ei osta enam teie tooteid või teenuseid teatud aja jooksul.

## <a name="azure-machine-learning-integration"></a>Azure’i masinõppe integratsioon

Kui organisatsioon juba kasutab Azure masinõppe eksperimentidel põhinevaid Masinõpe stsenaariume, aitab Customer Insights kohandatud mudelite funktsiooni punkte ühendada. Saate luua töövooge, mis aitavad teil valida andmeid, millest soovite ülevaateid luua ja vastendada tulemused oma ühtsete kliendiprofiilidega. Lisateavet vt teemast [Kohandatud masinõppemudelid](custom-models.md).

## <a name="ai-builder-prediction"></a>AI Builderi prognoos

Mõnikord on andmekogumid poolikud ja mõned väärtused puuduvad. Customer Insights aitab prognoosida kliendi olemi ja segmentide puuduvaid väärtusi. Lisateavet vt teemast [Osaliste andmete prognooside täiustamine](predictions.md).
