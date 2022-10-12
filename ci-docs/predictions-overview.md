---
title: Prognooside ülevaade
description: Prognoosistsenaariumid ja -valikud, mida rakendus Dynamics 365 Customer Insights hõlmab.
ms.date: 09/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: f8c61d7530126890d26ce482a27a0f97a39e836c
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610185"
---
# <a name="predictions-overview"></a>Prognooside ülevaade

Dynamics 365 Customer Insights sisaldab mitmesuguseid võimalusi, mis võimendavad tehisintellekti ja masinõpet andmete prognoosimiseks.

## <a name="out-of-box-models"></a>"Karbist väljas" mudelid

Lihtsaim viis andmete prognoosimisega alustamiseks on eelnevalt määratletud mudelid, mida sageli nimetatakse "karbist väljas" mudeliteks. Need nõuavad ainult teatud andmeid ja struktuuri, et kiiresti ülevaateid saada. Saadaval on järgmised mudelid:

# <a name="individual-consumers-b-to-c"></a>[Üksikud tarbijad (B-st C-ni)](#tab/b2c)

- [Kliendi eluaja väärtus](predict-customer-lifetime-value.md): ennustab kliendi potentsiaalset tulu kogu suhtluses ettevõttega.
- [Tootesoovitus](predict-product-recommendation.md): soovitab prognoositava tootesoovituste komplekte, mis põhinevad ostukäitumisel ja sarnaste ostuharjumustega klientidel.
- [Kordustellimuste valim](predict-subscription-churn.md): prognoosib, kas kliendi puhul valitseb oht, et ta ei kasuta enam teie ettevõtte kordustellimuse tooteid või teenuseid.
- [Tehingumaht](predict-transactional-churn.md): ennustab, kas üksikklient ei osta enam teie tooteid või teenuseid teatud aja jooksul.
- [Sentimentanalüüs](sentiment-analysis.md): analüüsib klientide tagasiside sentimenti ja tuvastab sageli mainitud äriaspektid.

# <a name="business-accounts-b-to-b"></a>[Ettevõtte kontod (B-st B-ni)](#tab/b2b)

- [Tehingumaht](predict-transactional-churn.md): ennustab, kas kliendikonto ei osta enam teatud aja jooksul teie tooteid või teenuseid.

---

> [!TIP]
> Soovitame teil regulaarselt värskendada valmis mudeleid värskendatud andmetega, et tagada nende täpne teavitamine teie ärikasutuse juhtumist. Andmeid värskendatakse ad hoc, kui süsteem kasutab uusi või värskendatud andmeallikaid. Kuid mudelid korrigeerivad ainult sel juhul ja jätkavad olemasolevate treeningandmete kasutamist.
>
> **Konfigureerige värskendusgraafikut**, määrates konfiguratsiooni ajal mudeli ümberõppe ajakava. Mudel treenib ja korrigeerib seda ajakava, mida saate igal ajal muuta.

## <a name="azure-machine-learning-integration"></a>Azure’i masinõppe integratsioon

Kui organisatsioon juba kasutab Azure masinõppe eksperimentidel põhinevaid Masinõpe stsenaariume, aitab Customer Insights kohandatud mudelite funktsiooni punkte ühendada. Saate luua töövooge, mis aitavad teil valida andmeid, millest soovite ülevaateid luua ja vastendada tulemused oma ühtsete kliendiprofiilidega. Lisateavet vt teemast [Kohandatud masinõppemudelid](custom-models.md).

## <a name="manage-existing-predictions"></a>Olemasolevate prognooside haldamine

Minge **·** > **luureprognooside** lehele. **Vahekaardil Minu ennustused** saate vaadata enda loodud prognoose, nende prognoos tüüpi, väljundolemi nime, olekut, prognoos viimati redigeerimise aega ja viimast korda, kui andmeid värskendati. Prognooside loendit saate sortida mis tahes veeru järgi.

Valige saadaolevate toimingute vaatamiseks prognoos.

:::image type="content" source="media/predictions.png" alt-text="Minu ennustuste leht.":::

- **Redigeerige** prognoos selle atribuutide muutmiseks.
- [**Värskendage**](#refresh-a-prediction) prognoos, et lisada uusimad andmed.
- **Vaadake** prognoos üksikasju.
- [**Sisendandmete kasutatavuse aruanne**](#view-the-input-data-usability-report) tõrgete, hoiatuste ja soovituste vaatamiseks.
- **Kustutage** prognoos.

### <a name="refresh-a-prediction"></a>Prognoosi värskendamine

Ennustusi saab värskendada automaatse ajakava alusel või nõudmisel käsitsi värskendada. Kõigi ennustuste käsitsi värskendamiseks valige **Värskenda kõik**. Prognoos käsitsi värskendamiseks valige see ja valige **Värskenda**. Automaatse värskendamise ajastamiseks [minge jaotisse](schedule-refresh.md) Haldussüsteemi **·** > **ajakava** > **.**

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

### <a name="view-the-input-data-usability-report"></a>Vaata sisendandmete kasutatavusaruannet

Sisendandmete kasutatavuse aruanne annab konsolideeritud ülevaate tõrgetest ja hoiatustest, mida teie "karbist-väljas" prognoosid võivad tekitada. Samuti annab see soovitusi mudeli jõudluse parandamiseks.

Aruanne on saadaval pärast seda, kui mudel on oma treeninguprotsessi lõpetanud. See luuakse iga mudeli jaoks eraldi, olenemata sellest, kas see läbis koolituse edukalt või mitte.

**Valige vahekaardil Minu ennustused** prognoos ja valige **sisendandmete kasutatavuse aruanne**. Või tehke vaates prognoos üksikasjad valik **Sisendandmete kasutatavuse aruanne**.

:::image type="content" source="media/input-data-usability-report.png" alt-text="Sisendandmete kasutatavuse aruande näide, milles on kuvatud tõrgete, hoiatuste ja soovitustega tabel.":::

Aruanne sisaldab järgmist:

- **Nimi:** tõrke, hoiatuse või soovituse kirjeldav nimi.
- **Etapp:** mudeli faas, treenimine või skoor, millele teave viitab.
- **Olek:** Teabe raskusaste (viga, hoiatus, soovitus).
- **Veeru nimi:** veerg olemis, mida tuleb mudeli jõudluse parandamiseks muuta.
- **Olemi nimi:** selle olemi nimi, mida tuleb mudeli jõudluse parandamiseks muuta.
- **Üksikasjad:** tõrke, hoiatuse või soovituse üksikasjad.

[!INCLUDE [footer-include](includes/footer-banner.md)]
