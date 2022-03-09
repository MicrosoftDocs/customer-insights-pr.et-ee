---
title: -Põhiste andmeallikate Power Query järk-järguline värskendamine
description: Värskendage uusi ja värskendatud andmeid suurte andmeallikate jaoks, mis põhinevad Power Query.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: 62632efda3c0c7e53fcdd8864b053ba93e2918bc
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 02/25/2022
ms.locfileid: "8353676"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a>Andmeallikate järk-järguline värskendamine, mis põhineb Power Query

Selles artiklis käsitletakse, kuidas konfigureerida andmeallikate järkjärgulist värskendamist rakenduse alusel Power Query.

Andmeallikate astmelisel värskendamisel on järgmised eelised.

- **Kiiremad värskendamised** – värskendatakse ainult muudetud andmeid. Näiteks võite värskendada ainult ajaloolise andmekomplekti viimased viis päeva.
- **Suurem töökindlus** – väiksemate värskendamistega ei pea te hoidma hävivate lähtesüsteemidega nii kaua ühendust, vähendades ühenduse probleemide ohtu.
- **Vähenenud ressursside tarbimine** – värskendades ainult teie kõikide andmete alamhulka toob kaasa palju tõhusama arvutusressursside kasutamise ja vähendab ökoloogilist jalajälge.

## <a name="configure-incremental-refresh"></a>Astmelise värskendamise konfigureerimine

Vaatajaskonna ülevaated võimaldavad selle toe juurdeneelamise kaudu Power Query imporditud andmeallikate järkjärgulist värskendamist. Näiteks Azure SQL-i andmebaasid kuupäeva ja kellaaja väljadega, mis näitavad, millal andmete kirjeid viimati värskendati.

1. [Looge uus andmeallikas, mis põhineb Power Query](connect-power-query.md).

1. Sisestage **andmeallikas nimi**.

1. Valige andmeallikas, mis toetab järkjärgulist värskendamist (nt [Azure'i SQL-andmebaas](/power-query/connectors/azuresqldatabase)).

1. Valige olemid või tabelid, mida soovite sisestada.

1. Viige teisenduse sammud lõpule ja valige suvand **Edasi**.

1. Dialoogiboksis **Astmelise värskendamise seadistamine** valige suvand **Seadista**, et avada suvand **Astmelise värskendamise sätted**. Kui valite suvandi **Jäta vahele**, värskendab andmeallikas kogu andmekomplekti.
   > [!TIP]
   > Saate astmelise värskendamise rakendada ka hiljem, redigeerides olemasolevat andmeallikat.

1. Suvandis **Astmelise värskendamise sätted** konfigureerite astmelise värskendamise kõigi olemite jaoks, mille andmeallikate loomisel valisite.

   :::image type="content" source="media/incremental-refresh-settings.png" alt-text="Andmeallika olemite konfigureerimine j'rkj'rguliseks värskendamiseks.":::

1. Valige olem ja sisestage järgmised üksikasjad.

   - **Määratle primaarvõti**: valige olemi või tabeli primaarvõti.
   - **Määratle väli „Viimati värskendatud”**: see väli kuvab ainult tüübi kuupäeva või kellaaja atribuudid. Valige atribuut, mis näitab, millal kirjed viimati värskendati. Seda kasutatakse selliste kirjete tuvastamiseks, mis jäävad astmelise värskendamise ajavahemikku.
   - **Otsi värskendusi iga järgmise vahemiku järel**: määrake kui pika te soovite, astmelise värskendamise ajavahemik oleks.

1. Andmeallika loomise lõpetamiseks valige suvand **Salvesta**. Esmane andmete värskendamine on täielik värskendamine. Pärast seda leiavad astmelised andmete värskendused aset vastavalt eelmises etapis konfigureeritule.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
