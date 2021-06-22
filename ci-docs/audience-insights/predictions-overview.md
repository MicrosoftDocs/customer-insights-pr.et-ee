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
ms.openlocfilehash: 69ae945b22819521db217508c6fc232876346747
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095701"
---
# <a name="predictions-overview"></a><span data-ttu-id="d01af-103">Prognooside ülevaade</span><span class="sxs-lookup"><span data-stu-id="d01af-103">Predictions overview</span></span>

<span data-ttu-id="d01af-104">Dynamics 365 Customer Insights sisaldab mitmesuguseid võimalusi, mis võimendavad tehisintellekti ja masinõpet andmete prognoosimiseks.</span><span class="sxs-lookup"><span data-stu-id="d01af-104">Dynamics 365 Customer Insights comes with a variety of options that leverage AI and machine learning to predict data.</span></span> 

## <a name="out-of-box-models"></a><span data-ttu-id="d01af-105">"Karbist väljas" mudelid</span><span class="sxs-lookup"><span data-stu-id="d01af-105">Out-of-box models</span></span>

<span data-ttu-id="d01af-106">Lihtsaim viis andmete prognoosimisega alustamiseks on eelnevalt määratletud mudelid, mida sageli nimetatakse "karbist väljas" mudeliteks.</span><span class="sxs-lookup"><span data-stu-id="d01af-106">The easiest way to start with predicting data are predefined models, often referred to as out-of-box models.</span></span> <span data-ttu-id="d01af-107">Need nõuavad ainult teatud andmeid ja struktuuri, et kiiresti ülevaateid saada.</span><span class="sxs-lookup"><span data-stu-id="d01af-107">They only require certain data and structure to generate insights quickly.</span></span> <span data-ttu-id="d01af-108">Praegu on saadaval järgmised mudelid.</span><span class="sxs-lookup"><span data-stu-id="d01af-108">Currently, the following models are available:</span></span> 
- <span data-ttu-id="d01af-109">[Kliendi eluaja väärtus](predict-customer-lifetime-value.md): ennustab kliendi potentsiaalset tulu kogu suhtluses ettevõttega.</span><span class="sxs-lookup"><span data-stu-id="d01af-109">[Customer lifetime value](predict-customer-lifetime-value.md): Predicts the potential revenue of a customer throughout the entire interaction with a business.</span></span> 
- <span data-ttu-id="d01af-110">[Tootesoovitus](predict-product-recommendation.md): soovitab prognoositava tootesoovituste komplekte, mis põhinevad ostukäitumisel ja sarnaste ostuharjumustega klientidel.</span><span class="sxs-lookup"><span data-stu-id="d01af-110">[Product recommendation](predict-product-recommendation.md): Suggests sets of predictive product recommendations based on purchase behavior and customers with similar purchase patterns.</span></span>
- <span data-ttu-id="d01af-111">[Kordustellimuste valim](predict-subscription-churn.md): prognoosib, kas kliendi puhul valitseb oht, et ta ei kasuta enam teie ettevõtte kordustellimuse tooteid või teenuseid.</span><span class="sxs-lookup"><span data-stu-id="d01af-111">[Subscription churn](predict-subscription-churn.md): Predicts whether a customer is at risk for no longer using your company’s subscription products or services.</span></span>
- <span data-ttu-id="d01af-112">[Tehingute valim](predict-transactional-churn.md): prognoosib, kas klient ei osta enam teie tooteid või teenuseid teatud aja jooksul.</span><span class="sxs-lookup"><span data-stu-id="d01af-112">[Transactional churn](predict-transactional-churn.md): Predict if a customer will no longer purchase your products or services in a certain time frame.</span></span>

## <a name="azure-machine-learning-integration"></a><span data-ttu-id="d01af-113">Azure’i masinõppe integratsioon</span><span class="sxs-lookup"><span data-stu-id="d01af-113">Azure Machine Learning integration</span></span>

<span data-ttu-id="d01af-114">Kui organisatsioon juba kasutab Azure masinõppe eksperimentidel põhinevaid Masinõpe stsenaariume, aitab Customer Insights kohandatud mudelite funktsiooni punkte ühendada.</span><span class="sxs-lookup"><span data-stu-id="d01af-114">If an organization already uses machine learning scenarios based on Azure Machine Learning experiments, the custom models feature in Customer Insights helps to connect the dots.</span></span> <span data-ttu-id="d01af-115">Saate luua töövooge, mis aitavad teil valida andmeid, millest soovite ülevaateid luua ja vastendada tulemused oma ühtsete kliendiprofiilidega.</span><span class="sxs-lookup"><span data-stu-id="d01af-115">Create workflows that help you choose the data you want to generate insights from and map the results to your unified customer profiles.</span></span> <span data-ttu-id="d01af-116">Lisateavet vt teemast [Kohandatud masinõppemudelid](custom-models.md).</span><span class="sxs-lookup"><span data-stu-id="d01af-116">For more information, see [Custom machine learning models](custom-models.md).</span></span>

## <a name="ai-builder-prediction"></a><span data-ttu-id="d01af-117">AI Builderi prognoos</span><span class="sxs-lookup"><span data-stu-id="d01af-117">AI Builder prediction</span></span>

<span data-ttu-id="d01af-118">Mõnikord on andmekogumid poolikud ja mõned väärtused puuduvad.</span><span class="sxs-lookup"><span data-stu-id="d01af-118">Sometimes, data sets are incomplete and some values are missing.</span></span> <span data-ttu-id="d01af-119">Customer Insights aitab prognoosida kliendi olemi ja segmentide puuduvaid väärtusi.</span><span class="sxs-lookup"><span data-stu-id="d01af-119">Customer Insights can help to predict missing values for the Customer entity and segments.</span></span> <span data-ttu-id="d01af-120">Lisateavet vt teemast [Osaliste andmete prognooside täiustamine](predictions.md).</span><span class="sxs-lookup"><span data-stu-id="d01af-120">For more information, see [Complete your partial data with predictions](predictions.md).</span></span>
