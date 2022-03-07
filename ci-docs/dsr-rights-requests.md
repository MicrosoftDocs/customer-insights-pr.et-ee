---
title: Andmesubjekti õigused (DSR) vastavalt GDPR-ile | Microsoft Docs
description: Vastake andmesubjekti taotlustele Dynamics 365 Customer Insights vaatajaskonna ülevaate võimaluse kohta.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: c116f7ce208c0288851a4b2230e27784ba3a5337
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732675"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Andmesubjekti õigused (DSR) vastavalt GDPR-ile

Euroopa Liidu General Data Protection Regulation (GDPR) on kehtiv alates 25. maist 2018. See annab üksikisikutele nende andmetega seoses märkimisväärselt õigusi. GDPR on üksikisikute privaatsusõiguste kaitse ja lubamise kohta. Rohkem teavet Microsofti enda õiguste ja turvalisuse kohta saate lugeda [Microsofti usalduskeskusest](https://www.microsoft.com/trust-center).

Oleme pühendunud sellele, et aitame klientidel täita GDPR-i nõudeid. See hõlmab õigust kustutada ja eksportida andmeid, mis sisaldavad isikuandmeid, nagu kasutaja ID-d, telefoninumbrid ja meiliaadressid. Administraatorid saavad juurutada kasutajataotlusi isiklike andmete kustutamiseks või eksportimiseks.

## <a name="audience-insights"></a>Sihtrühmaülevaated

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>GDPR-i andmesubjektile vastamine kustutab Dynamics 365 Customer Insights vaatajaskonna ülevaate võimaluse taotlused

Õigus isikuandmete eemaldamiseks ettevõtte kliendiandmetest on isikuandmete kaitse üldmääruse (GDPR-i) põhikaitse. Isikuandmete eemaldamine hõlmab kogi isiklike andmete ja süsteemi loodud logide eemaldamist, va auditi logi teabe.

#### <a name="manage-data-subject-delete-requests"></a>Andmete kustutamise taotluste haldamine

Sihtrühmaülevaadete funktsioon pakub järgmisi tootega seotud kogemusi, et kustutada teatud kliendi või kasutaja isikuandmed.

- **Kliendiandmete kustutamise taotluste haldamine**: kliendi andmed Customer Insightsis on sisestatud algsest andmeallikast, mis on Customer Insightsi väline. Kõik GDPR-i kustutamise taotlused tuleb teha algses andmeallikas.
- **Customer Insightsi kliendiandmete kustutamise taotluste haldamine**: kasutajate andmeid loob Customer Insights. Kõik GDPR-i kustutamise taotlused tuleb teha Customer Insightsis.

##### <a name="manage-requests-to-delete-customer-data"></a>Kliendiandmete kustutamise taotluste haldamine

Customer Insightsi administraator saab nende etappide abil eemaldada kliendiandmeid, mis kustutati andmeallikas.

1. Logige Dynamics 365 Customer Insights sisse.
2. Avage sihtrühmaülevaadetes jaotis **Andmed** > **Andmeallikad**
3. Tehke iga loendis oleva andmeallikaga, mis sisaldab kustutatud kliendiandmeid, järgmist.
   1. Valige (...) ja seejärel valige nupp **Värskenda**.
   2. Kontrollige andmeallikas olekut **Oleku** all. Märge tähendab, et värskendamine õnnestus. Ohukolmnurk tähendab, et midagi läks valesti. Kui kuvatakse ohukolmnurk, võtke ühendust aadressil D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Kliendiandmete GDPR-i kustutamise taotluste käsitlemine.](audience-insights/media/gdpr-data-sources.png "Kliendiandmete GDPR-i kustutamise taotluste käsitlemine")

##### <a name="manage-delete-requests-for-user-data"></a>Kasutajaandmete kustutamise taotluste haldamine

Customer Insightsi administraator saab Customer Insightsi kasutaja andmete kustutamiseks toimida järgmiselt.

1. Logige Dynamics 365 Customer Insights sisse.
2. Avage sihtrühmaülevaadetes jaotis **Haldus** > **Õigused**.
3. Valige märkeruutude abil kasutaja, kelle soovite kustutada.
4. Valige **Eemalda**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>GDPR-i andmesubjekti eksportimistaotlustele vastamine

Osana meie pühendumusest saatmaks teid teekonnal isikuandmete kaitse üldmääruseni (GDPR) oleme välja töötanud dokumendid, mis aitavad teil valmistuda. Selles dokumentatsioonis kirjeldatakse toiminguid, mida saate kohe teha, et toetada GDPR-i täitmist sihtrühmaülevaadete kasutamisel.

#### <a name="manage-export-and-view-requests"></a>Ekspordi ja vaate taotluste haldamine

Andmete teisaldamise õigus võimaldab andmesubjektil taotleda oma isikuandmete koopiat elektrooniliselt (määratletakse kui „struktureeritud, tavaliselt kasutatav, masinloetav ja koostalitlusvõimeline vorming“), mida võib edastada teisele andmetöötlejale.

##### <a name="export-customer-data-tenant-admin"></a>Kliendiandmete eksportimine (rentniku administraator)

Rentniku administraator võib järgida andmete eksportimisel järgmisi etappe.

1. Saatke meili aadressile D365CI@microsoft.com, et määrata taotluses kliendi meiliaadress. Customer Insightsi meeskond saadab registreeritud rentniku administraatori meiliaadressile meili, paludes kinnitust andmete eksportimiseks.
2. Kinnitage taotletud kliendile andmete eksportimise luba.
3. Saage eksporditud andmed rentniku administraatori meiliaadressi kaudu.

##### <a name="export-user-data-tenant-admin"></a>Kasutajaandmete eksportimine (rentniku administraator)

1. Saatke meil aadressile D365CI@microsoft.com, et määrata taotluses kasutaja meiliaadress. Customer Insightsi meeskond saadab registreeritud rentniku administraatori meiliaadressile meili, paludes kinnitust andmete eksportimiseks.
2. Kinnitage taotletud kasutajale andmete eksportimise luba.
3. Saage eksporditud andmed rentniku administraatori meiliaadressi kaudu.

## <a name="consent-management-preview"></a>Nõusoleku haldus (eelvaade)

Nõusoleku haldamise võimalus ei kogu kasutajaandmeid otse. See impordib ja töötleb ainult nõusolekuandmeid, mida kasutajad on esitanud muudes rakendustes.

Nõusolekuandmete eemaldamiseks konkreetsete kasutajate kohta eemaldage need andmeallikatest, mis on neelatud nõusoleku haldamise võimalusele. Pärast andmeallikas värskendamist kustutatakse eemaldatud andmed ka nõusolekukeskuses. Rakendused, mis kasutavad nõusoleku olemit, kustutavad ka andmed, mis eemaldati allikast pärast [värskendamist](audience-insights/system.md#refresh-processes). Soovitame andmeallikad kiiresti värskendada pärast andmesubjekti taotlusele vastamist, et eemaldada kasutaja andmed kõigist muudest protsessidest ja rakendustest.


## <a name="engagement-insights-preview"></a>Kaasamisülevaated (eelversioon)

### <a name="deleting-and-exporting-event-data-containing-end-user-identifiable-information"></a>Lõppkasutajat tuvastada võimaldavat teavet sisaldavate sündmuseandmete kustutamine ja eksportimine

Järgmistes jaotistes kirjeldatakse, kuidas kustutada ja eksportida sündmuseandmeid, mis võivad sisaldada isikuandmeid.

Andmete kustutamiseks või ekspordiks:

1. Sildistada sündmuse atribuudid, mis sisaldavad isikuandmeid.
2. Kindlate väärtustega seostatud andmete kustutamine või eksportimine (nt määratud kasutaja ID).

#### <a name="tag-and-update-event-properties"></a>Sündmuse atribuutide sildistamine ja värskendamine

Isikuandmed on sündmuste atribuudi tasandil üleliidsed. Selleks tuleb esmalt sildistada atribuudid, mida käsitletakse kustutamisel või eksportimisel.

Kui soovite sündmuse atribuudi sildistada isikuandmeid sisaldavana, toimige järgmiselt:

1. Avage sündmust sisaldav tööruum.

1. Minge **Andmed** > **Sündmused**, et näha sündmuste loendit tööruumis.
  
1. Valige sündmus, mida soovite märkida.

1. Valige **Redigeerige atribuute** et avada paani loendi avamiseks valitud sündmuse kõik atribuudid.
     
1. Valige **...** ja seejärel **Redigeerige** et jõuda **Atribuutide värskendamise** dialoogi.

   ![Redigeeri sündmust.](engagement-insights/media/edit-event.png "Redigeeri sündmust")

1. Tehke **Atribuudi värskendamine** aknas valik **...** ja parempoolses ülanurgas valige **Sisaldab EUII** väli. Valige **Värskenda** et muudatused salvestada.

   ![Salvestage muudatused.](engagement-insights/media/update-property.png "Saate oma muudatused salvestada")

   > [!NOTE]
   > Iga kord, kui sündmuseskeem muutub või loote uue sündmuse, on soovitatav hinnata seostatud sündmuse atribuute ja vajadusel neid sisaldavatena muuta või need eemaldada.

#### <a name="delete-or-export-tagged-event-data"></a>Sündmuse andmete kustutamine või eksportimine

Kui kõik sündmuse atribuudid on vastavalt eelmises sammus kirjeldatule märgistatud, saab keskkonnaadministraator väljastada kustutamistaotluse, mis vastaks sündmuseandmetele.

EUII kustutamis- või eksporditaotluse haldamine

1. Minge jaotisse **Haldus** > **Keskkond** > **Seaded**.

1. Jaotises **Lõppkasutajat tuvastada võimaldava teabe (EUII)** jaotises valige **Halda EUII**.

##### <a name="deletion"></a>Kustutamine

Kustutamiseks võite sisestada komadega eraldatud kasutaja ID-de loendi **Lõppkasutajat tuvastada võimaldava teabe kustutamine (EUII)** jaotises. Neid ID-sid võrreldakse kõigi praeguses keskkonnas asuvate projektide kõigi sündmuse atribuutidega täpse stringi sobitamise kaudu. 

Kui atribuudi väärtus vastab ühele esitatud ID-st, kustutatakse seostatud sündmus jäädavalt. Selle toimingu jäädavuse tõttu peate pärast nupu **Kustuta** valimist kustutamise kinnitama.

##### <a name="export"></a>Export

Ekspordiprotsess on sama, mis kustutamisprotsessil, mil tegemist on sündmuse atribuudi väärtuste kustutamisega jaotises **Eksport lõppkasutaja tuvastamist võimaldava teabe kohta (EUII)** jaotises. Lisaks peate sisestama **Azure'i bloobimälu URL-i**, et määrata ekspordi sihtkoht. Azure'i bloobi URL peab sisaldama [ühisjuurdepääsu allkirja (SAS)](/azure/storage/common/storage-sas-overview).

Pärast suvandi **Eksport** valimist eksporditakse kõik praeguse meeskonna sündmused, mis sisaldavad sobitatud atribuute, CSV-vormingus ekspordisihtkohta.

### <a name="good-practices"></a>Head tavad

* Proovige vältida mis tahes sündmusi, mis sisaldavad isikuandmeid.
* Kui on vaja saata EUII andmeid sisaldavaid sündmusi, piirake andmeid sisaldavate sündmuste ja sündmuse atribuutide arvu. Ideaaljuhul võiks olla piiratud ühe sellise sündmusega.
* Veenduge, et saadetud isikuandmetele oleks juurdepääs nii vähestel inimestel kui võimalik.
* Isikuandmetega seotud sündmuste puhul veenduge, et määrate ühe atribuudi, mis tagab kordumatu ID, mida saab konkreetse kasutajaga hõlpsasti linkida (nt kasutaja ID). See teeb andmete eraldamist ning õigete andmete eksportimise või kustutamise lihtsamaks.
* Sildista sündmuse kohta ainult üks atribuut, mis sisaldab isikuandmeid. Ideaaljuhul vaid üks, mis sisaldab unikaalset identifikaatorit.
* Ärge sildistage atribuute, mis sisaldavad sõnalisi väärtusi (nt kogu taotluse keha). Kaasamisülevaadete võimalus kasutab täpset stringi sobitamist, kui otsustatakse, milliseid sündmusi kustutada või eksportida.

[!INCLUDE[footer-include](includes/footer-banner.md)]