---
title: Seosed olemite ja olemiteede vahel
description: Looge ja hallake mitmest andmeallikast pärit olemite vahelisi seoseid.
ms.date: 04/14/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 292da986faa7f62d8aa73ed7214075612178e2e1
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269868"
---
# <a name="relationships-between-entities"></a>Olemitevaheline seos

Seosed aitavad ühendada olemeid ja luua andmetest graafik, mil olemid jagavad ühist tunnust (võõrvõti), mida saab viita ühest olemist teise. Ühendatud olemid võimaldavad määratleda segmente ja mõõte mitmete andmeallikate alusel.

Seoseid on kahte tüüpi: Kasutajate loodud ja seadistatud mittemuudetavad süsteemi seosed, mis tekivad ise, ning kohandatud seosed.

Süsteemi seosed luuakse vastendamise ja liitmise ajal taustal vastavalt intelligentsele vastendamisele. Need seosed aitavad seostada kliendiprofiili kirjeid teiste vastavate olemite kirjetega. Järgmisel diagrammil kirjeldatakse kolme süsteemi seose loomist, kui kliendiolemit vastendatakse täiendavate olemitega, et luua lõplik kliendiprofiili olem.

> [!div class="mx-imgBorder"]
> ![Seose loomine](media/relationships-entities-merge.png "Seose loomine")

- ***CustomerToContact* seos** loodi kliendi olemi ja kontakti olemi vahel. Kliendi olem saab võtme välja **Contact_contactId**, et olla seotud kontakti olemi võtme väljaga **contactId**.
- ***CustomerToAccount* seos** loodi kliendi olemi ja konto olemi vahel. Kliendi olem saab võtme välja **Account_accountId**, et olla seotud konto olemi võtme väljaga **accountId**.
- ***CustomerToWebAccount* seos** loodi kliendi olemi ja veebikonto olemi vahel. Kliendi olem saab võtme välja **WebAccount_webaccountId**, et olla seotud veebikonto olemi võtme väljaga **webaccountId**.

## <a name="create-a-relationship"></a>Seose loomine

Määratlege kohandatud seoseid lehel **Seosed**. Iga seos koosneb lähteolemist (võõrvõtit sisaldav olem) ja sihtolemist (olem, millele suunab lähteolemi võõrvõti).

1. Avage sihtrühmaülevaadetes jaotis **Andmed** > **Seosed**.

2. Valige **Uus seos**.

3. Sisestage paanil **Lisa seos** järgmised andmed.

   > [!div class="mx-imgBorder"]
   > ![Sisestage seose üksikasjad](media/relationships-add.png "Sisestage seose üksikasjad")

   - **Seose nimi**: seose eesmärki kirjeldav nimi (näiteks **AccountWebLogs**).
   - **Kirjeldus**: seose kirjeldus.
   - **Lähteolem**: valige olem, mida kasutatakse seose allikana (näiteks WebLog).
   - **Kardinaalsus**: valige lähteolemi kirjete kardinaalsus. Näiteks „mitu“ tähendab, et mitu Weblogi kirjet on seotud ühe WebAccountiga.
   - **Lähtevõtme väli**: see tähistab lähteolemi võõrvõtme välja. Näiteks WebLogi võõrvõtme väljaks on **accountId**.
   - **Sihtolem**: valige olem, mida kasutatakse seose sihtkohana (näiteks WebAccount).
   - **Sihtkardinaalsus**: valige sihtolemi kirjete kardinaalsus. Näiteks „üks“ tähendab, et mitu Weblogi kirjet on seotud ühe WebAccountiga.
   - **Sihtvõtme väli**: see väli tähistab sihtolemi võtme välja. Näiteks WebAccounti võtme väljaks on **accountId**.

> [!NOTE]
> Toetatakse vaid mitu-ühele ja üks-ühele seoseid. Mitu-mitmele seoseid saab luua kahe mitu-ühele seosega ja lingi olemiga (tegemist on olemiga, millega ühendatakse omavahel lähteolem ja sihtolem).

## <a name="delete-a-relationship"></a>Kustutage seos

1. Avage sihtrühmaülevaadetes jaotis **Andmed** > **Seosed**.

2. Valige märkeruutude abil seosed, mille soovite kustutada.

3. Valige tabeli **Seosed** algusest **Kustuta**.

4. Kinnitage, et soovite kustutada.

## <a name="next-step"></a>Järgmine etapp

Süsteemi ja kohandatud seoseid kasutatakse segmentide loomiseks vastavalt mitte enam eraldatud mitmele andmeallikale. Lisateavet vt [Segmendid](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]