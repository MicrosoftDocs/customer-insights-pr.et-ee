---
title: Azure Data Lake'i andmeallikate Power Query täiendav värskendamine
description: Värskendage uusi ja värskendatud andmeid suurte andmeallikate kohta, mis põhinevad Power Query Azure'i andmeallikatel või Azure'i andmeallikatel.
ms.date: 05/30/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: bff27bf7fec2bcb741846ae76bb1f616f459136c
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 06/14/2022
ms.locfileid: "9012020"
---
# <a name="incremental-refresh-for-power-query-and-azure-data-lake-data-sources"></a>Azure Data Lake'i andmeallikate Power Query täiendav värskendamine

Selles artiklis käsitletakse, kuidas konfigureerida andmeallikate järkjärgulist värskendust Azure Data Lake'i Power Query või Azure Data Lake'i põhjal.

Andmeallikate astmelisel värskendamisel on järgmised eelised.

- **Kiiremad värskendamised** – värskendatakse ainult muudetud andmeid. Näiteks võite värskendada ainult ajaloolise andmekomplekti viimased viis päeva.
- **Suurem töökindlus** – väiksemate värskendamistega ei pea te hoidma hävivate lähtesüsteemidega nii kaua ühendust, vähendades ühenduse probleemide ohtu.
- **Vähenenud ressursside tarbimine** – värskendades ainult teie kõikide andmete alamhulka toob kaasa palju tõhusama arvutusressursside kasutamise ja vähendab ökoloogilist jalajälge.

## <a name="configure-incremental-refresh-for-data-sources-based-on-power-query"></a>Andmeallikate täiendava värskendamise konfigureerimine põhineb Power Query

Customer Insights võimaldab selle toe kaudu Power Query imporditud andmeallikate järkjärgulist värskendamist. Näiteks Azure SQL-i andmebaasid kuupäeva ja kellaaja väljadega, mis näitavad, millal andmete kirjeid viimati värskendati.

1. [Looge uus andmeallikas, mis põhineb rakendusel Power Query](connect-power-query.md).

1. Valige andmeallikas, mis toetab järkjärgulist värskendamist (nt [Azure'i SQL-i andmebaas)](/power-query/connectors/azuresqldatabase).

1. Valige olemid või tabelid, mida soovite sisestada.

1. Viige teisenduse sammud lõpule ja valige suvand **Edasi**.

1. Dialoogiboksis **Astmelise värskendamise seadistamine** valige suvand **Seadista**, et avada suvand **Astmelise värskendamise sätted**. Kui valite suvandi **Jäta vahele**, värskendab andmeallikas kogu andmekomplekti.
   > [!TIP]
   > Saate astmelise värskendamise rakendada ka hiljem, redigeerides olemasolevat andmeallikat.

1. Suvandis **Astmelise värskendamise sätted** konfigureerite astmelise värskendamise kõigi olemite jaoks, mille andmeallikate loomisel valisite.

   :::image type="content" source="media/incremental-refresh-settings.png" alt-text="Konfigureerige täiendavad värskendussätted.":::

1. Valige olem ja sisestage järgmised üksikasjad.

   - **Määratle primaarvõti**: valige olemi või tabeli primaarvõti.
   - **Määratle väli „Viimati värskendatud”**: see väli kuvab ainult tüübi kuupäeva või kellaaja atribuudid. Valige atribuut, mis näitab, millal kirjed viimati värskendati. Seda kasutatakse selliste kirjete tuvastamiseks, mis jäävad astmelise värskendamise ajavahemikku.
   - **Otsi värskendusi iga järgmise vahemiku järel**: määrake kui pika te soovite, astmelise värskendamise ajavahemik oleks.

1. Andmeallika loomise lõpetamiseks valige suvand **Salvesta**. Esmane andmete värskendamine on täielik värskendamine. Pärast seda leiavad astmelised andmete värskendused aset vastavalt eelmises etapis konfigureeritule.

## <a name="configure-incremental-refresh-for-azure-data-lake-data-sources"></a>Azure Data Lake'i andmeallikate täiendava värskendamise konfigureerimine

Customer Insights võimaldab rakendusega Azure Data Lake Storage ühendatud andmeallikate järkjärgulist värskendamist. Olemi astmelise allaneelamise ja värskendamise kasutamiseks konfigureerige see olem Azure Data Lake'i andmeallikas või uuema lisamisel andmeallikas redigeerimisel. Olemi andmekaust peab sisaldama järgmisi kaustu.

- **FullData**: kaust andmefailidega, mis sisaldavad algseid kirjeid
- **IncrementalData**: kaust kuupäeva/kellaaja hierarhia kaustadega **yyyy/mm/dd/hh** vormingus, mis sisaldab astmelisi värskendusi. **hh** tähistab värskenduste UTC tundi ja sisaldab kaustu **Upserts** ja **Deletes**. **Upserts** sisaldab andmefaile olemasolevate kirjete või uute kirjete värskendustega. **Kustutamine** sisaldab andmefaile, mille kirjed tuleb eemaldada.

1. Andmeallikas lisamisel või redigeerimisel liikuge **olemi paanile Atribuudid**.

1. Vaadake atribuudid üle. Veenduge, et loodud või viimati värskendatud kuupäevaatribuut oleks häälestatud kuupäeva ja kellaaja *andmevormingu* **ja** kalendri tüübiga *Kalender.Date* **Semantiline.** Vajadusel redigeerige atribuuti ja valige **Valmis**.

1. Redigeerige **olemit paanil Olemite** valimine. Märkige **ruut Järk-järguline allaneelamine**.

   :::image type="content" source="media/ADLS_inc_refresh.png" alt-text="Andmeallika olemite konfigureerimine j'rkj'rguliseks värskendamiseks.":::

   1. Sirvige juurkaustani, mis sisaldab .csv- või .parkettfaile, et saada täielikke andmeid, järkjärgulisi andmekõikumisi ja järkjärgulisi andmekustutusi.
   1. Sisestage täielike andmete ja mõlema astmelise faili (\. CSV või \. parkett) laiendus.
   1. Valige **Salvesta**.

1. Valige jaotises **Viimati värskendatud** kuupäeva atribuut kuupäeva ajatempli.

1. Kui primaarvõtit **pole** valitud, valige primaarvõti. Primaarvõti on olemile ainuomane atribuut. Et atribuut saaks olla sobiv primaarvõti, ei tohi see sisaldada topeltväärtusi, puuduvaid väärtusi ega null-väärtusi. Põhivõtmetena toetatakse stringi-, täisarvu- ja GUID-andmetüübi atribuute.

1. Paani salvestamiseks ja sulgemiseks valige **Sule**.

1. Jätkake andmeallikas lisamist või redigeerimist.

[!INCLUDE [footer-include](includes/footer-banner.md)]
