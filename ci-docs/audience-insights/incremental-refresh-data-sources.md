---
title: Power Query põhiste andmeallikate astmeline värskendamine
description: Suurte Power Query põhiste andmeallikate uute ja värskendatud andmete värskendamine.
ms.date: 09/28/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b7e834f5f2fd1328563139675d7f850008348734
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405557"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a>Power Query põhiste andmeallikate astmeline värskendamine

Andmeallikate astmelisel värskendamisel on järgmised eelised.

- **Kiiremad värskendamised** – värskendatakse ainult muudetud andmeid. Näiteks võite värskendada ainult ajaloolise andmekomplekti viimased viis päeva.
- **Suurem töökindlus** – väiksemate värskendamistega ei pea te hoidma hävivate lähtesüsteemidega nii kaua ühendust, vähendades ühenduse probleemide ohtu.
- **Vähenenud ressursside tarbimine** – värskendades ainult teie kõikide andmete alamhulka toob kaasa palju tõhusama arvutusressursside kasutamise ja vähendab ökoloogilist jalajälge.

## <a name="configure-incremental-refresh"></a>Astmelise värskendamise konfigureerimine

Sihtrühmaülevaated võimaldavad värskendada astmeliselt Power Query kaudu imporditud andmeallikaid, mille korral toetatakse astmelist valmendamist. Näiteks Azure SQL-i andmebaasid kuupäeva ja kellaaja väljadega, mis näitavad, millal andmete kirjeid viimati värskendati.

1. [Looge Power Queryl põhinev uus andmeallikas](connect-power-query.md).

1. Andke andmeallikale nimi.

1. Valige andmeallikas, mis toetab astmelist värskendamist (nt Azure SQL-i andmebaas).

1. Valige olemid või tabelid, mida soovite sisestada.

1. Viige teisenduse sammud lõpule ja valige suvand **Edasi**.

1. Dialoogiboksis **Astmelise värskendamise seadistamine** valige suvand **Seadista**, et avada suvand **Astmelise värskendamise sätted**. Kui valite suvandi **Jäta vahele**, värskendab andmeallikas kogu andmekomplekti.
   > [!TIP]
   > Saate astmelise värskendamise rakendada ka hiljem, redigeerides olemasolevat andmeallikat.

1. Suvandis **Astmelise värskendamise sätted** konfigureerite astmelise värskendamise kõigi olemite jaoks, mille andmeallikate loomisel valisite.

   > [!div class="mx-imgBorder"]
   > ![Andmeallika olemite konfigureerimine astmeliseks värskendamiseks](media/incremental-refresh-settings.png "Andmeallika olemite konfigureerimine astmeliseks värskendamiseks")

1. Valige olem ja sisestage järgmised üksikasjad.

   - **Määratle primaarvõti**: valige olemi või tabeli primaarvõti.
   - **Määratle väli „Viimati värskendatud”**: see väli kuvab ainult tüübi kuupäeva või kellaaja atribuudid. Valige atribuut, mis näitab, millal kirjed viimati värskendati. Seda kasutatakse selliste kirjete tuvastamiseks, mis jäävad astmelise värskendamise ajavahemikku.
   - **Otsi värskendusi iga järgmise vahemiku järel**: määrake kui pika te soovite, astmelise värskendamise ajavahemik oleks.

1. Andmeallika loomise lõpetamiseks valige suvand **Salvesta**. Esmane andmete värskendamine on täielik värskendamine. Pärast seda leiavad astmelised andmete värskendused aset vastavalt eelmises etapis konfigureeritule.
