---
title: Azure Data Lake'i andmeallikate järkjärguline Power Query värskendamine
description: Värskendage uusi ja värskendatud andmeid suurte andmeallikate jaoks, mis põhinevad Power Query Azure'i andmejärve andmeallikatel.
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
ms.openlocfilehash: de39743eb8728fac34e417724c5f73bf44309c89
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207132"
---
# <a name="incremental-refresh-for-power-query-and-azure-data-lake-data-sources"></a>Azure Data Lake'i andmeallikate järkjärguline Power Query värskendamine

Azure Data Lake'il Power Query põhinevate andmeallikate astmeline värskendamine pakub järgmisi eeliseid.

- **Kiiremad värskendamised** – värskendatakse ainult muudetud andmeid. Näiteks võite värskendada ainult ajaloolise andmekomplekti viimased viis päeva.
- **Suurem töökindlus** – väiksemate värskendamistega ei pea te hoidma hävivate lähtesüsteemidega nii kaua ühendust, vähendades ühenduse probleemide ohtu.
- **Vähenenud ressursside tarbimine** – värskendades ainult teie kõikide andmete alamhulka toob kaasa palju tõhusama arvutusressursside kasutamise ja vähendab ökoloogilist jalajälge.

## <a name="configure-incremental-refresh-for-data-sources-based-on-power-query"></a>Andmeallikate astmelise värskendamise konfigureerimine Power Query

Customer Insights võimaldab järkjärgulist värskendamist andmeallikate puhul, mis on imporditud selle toe järkjärgulise allaneelamise kaudu Power Query. Näiteks Azure SQL-i andmebaasid kuupäeva ja kellaaja väljadega, mis näitavad, millal andmete kirjeid viimati värskendati.

1. [Looge uus andmeallikas, mis põhineb Power Query](connect-power-query.md).

1. Valige andmeallikas, mis toetab astmelist värskendamist (nt [Azure'i SQL-andmebaas)](/power-query/connectors/azuresqldatabase).

1. Valige olemid või tabelid, mida soovite sisestada.

1. Viige teisenduse sammud lõpule ja valige suvand **Edasi**.

1. Dialoogiboksis **Astmelise värskendamise seadistamine** valige suvand **Seadista**, et avada suvand **Astmelise värskendamise sätted**. Kui valite suvandi **Jäta vahele**, värskendab andmeallikas kogu andmekomplekti.
   > [!TIP]
   > Saate astmelise värskendamise rakendada ka hiljem, redigeerides olemasolevat andmeallikat.

1. Suvandis **Astmelise värskendamise sätted** konfigureerite astmelise värskendamise kõigi olemite jaoks, mille andmeallikate loomisel valisite.

   :::image type="content" source="media/incremental-refresh-settings.png" alt-text="Konfigureerige astmelised värskendussätted.":::

1. Valige olem ja sisestage järgmised üksikasjad.

   - **Määratle primaarvõti**: valige olemi või tabeli primaarvõti.
   - **Määratle väli „Viimati värskendatud”**: see väli kuvab ainult tüübi kuupäeva või kellaaja atribuudid. Valige atribuut, mis näitab, millal kirjed viimati värskendati. Seda kasutatakse selliste kirjete tuvastamiseks, mis jäävad astmelise värskendamise ajavahemikku.
   - **Otsi värskendusi iga järgmise vahemiku järel**: määrake kui pika te soovite, astmelise värskendamise ajavahemik oleks.

1. Andmeallika loomise lõpetamiseks valige suvand **Salvesta**. Esmane andmete värskendamine on täielik värskendamine. Pärast seda leiavad astmelised andmete värskendused aset vastavalt eelmises etapis konfigureeritule.

## <a name="configure-incremental-refresh-for-azure-data-lake-data-sources"></a>Azure Data Lake'i andmeallikate astmelise värskendamise konfigureerimine

Customer Insights võimaldab järkjärgulist värskendamist andmeallikate puhul, mis on ühendatud Azure Data Lake Storage. Olemi inkrementaalse allaneelamise ja värskendamise kasutamiseks konfigureerige see olem Azure Data Lake'i andmeallikas või uuemate andmeallikas redigeerimisel. Olemi andmekaust peab sisaldama järgmisi kaustu.

- **FullData**: kaust andmefailidega, mis sisaldavad algseid kirjeid
- **IncrementalData**: kaust kuupäeva/kellaaja hierarhia kaustadega **vormingus yyyy/kk/pp/hh**, mis sisaldab astmelisi värskendusi. **hh** tähistab värskenduste UTC tundi ja sisaldab **kaustu Upserts** ja **Deletes**. **Upserts** sisaldab andmefaile, mis sisaldavad värskendusi olemasolevatele kirjetele või uutele kirjetele. **Deletes** sisaldab andmefaile, mille kirjed tuleb eemaldada.

1. Andmeallikas lisamisel või redigeerimisel liikuge **olemi paanile Atribuudid**.

1. Vaadake atribuudid üle. Veenduge, et loodud või viimati värskendatud kuupäevaatribuut oleks seadistatud vormingus dateTime *Data* ja **tüübiga** *Calendar.Date* **Semantic.** Vajadusel redigeerige atribuuti ja valige **Valmis**.

1. Olemit redigeerige **paanil Olemi valimine**. Ruut **Astmeline allaneelamine** on valitud.

   :::image type="content" source="media/ADLS_inc_refresh.png" alt-text="Andmeallika olemite konfigureerimine j'rkj'rguliseks värskendamiseks.":::

   1. Liikuge sirvides juurkataloogini, mis sisaldab .csv- või .parketifaile, et saada täisandmeid, astmelisi andmeid suurendada ja astmelisi andmeid kustutada.
   1. Sisestage täielike andmete ja mõlema astmelise faili (\. csv või \. parkett) laiendus.
   1. .csv faili puhul valige veeru eraldaja ja soovi korral faili esimene rida veerupäisena.
   1. Valige **Salvesta**.

1. Väljal **Viimati värskendatud** valige kuupäeva ajatempli atribuut.

1. **Kui primaarvõti** pole valitud, valige primaarvõti. Primaarvõti on olemile ainuomane atribuut. Et atribuut saaks olla sobiv primaarvõti, ei tohi see sisaldada topeltväärtusi, puuduvaid väärtusi ega null-väärtusi. Stringi, täisarvu ja GUID andmetüübi atribuute toetatakse primaarvõtmetena.

1. Paani salvestamiseks ja sulgemiseks valige **Sule**.

1. Jätkake andmeallikas lisamise või redigeerimisega.

[!INCLUDE [footer-include](includes/footer-banner.md)]
