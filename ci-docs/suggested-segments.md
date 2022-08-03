---
title: Mõõtudel põhinevad soovitatud segmendid (eelvaade)
description: Las masinõpe aitab teil leida uusi ja huvitavaid segmente, mis põhinevad kliendi atribuutidel.
ms.date: 10/15/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
searchScope:
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: e3f504827029afa12c65ec6f065a62606aaa823f
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170952"
---
# <a name="suggested-segments-based-on-measures-preview"></a>Mõõtudel põhinevad soovitatud segmendid (eelvaade)

Tehisintellekti mudeli abil saate avastada oma klientide huvitavaid segmente. See masinõppega funktsioon soovitab mõõdikuid või kliendi atribuute põhinevaid segmente. See võib aidata parandada teie tulemuslikkuse põhinäitajaid (KPI-sid) või paremini mõista atribuutide mõju teiste atribuutide kontekstis.

> [!NOTE]
> Soovitatud segmentide funktsioon kasutab andmete hindamiseks ja nende põhjal prognooside tegemiseks automatiseeritud vahendeid. Seetõttu on seda võimalik kasutada profiilianalüüsi meetodina, kuna see mõiste on määratletud isikuandmete kaitse üldmääruses ("GDPR"). Selle funktsiooni kasutamise kohta andmete töötlemisel võib kehtida kas GDPR või muud seadused või määrused. Teie vastutate selle eest, et Dynamics 365 Customer Insightsi kasutades (sh antud funktsiooni kasutades) järgite te kõiki kohaldatavaid seadusi ja määrusi, sh eraelu puutumatuse, isikuandmete, biomeetriliste andmete, andmekaitse ja suhtluse konfidentsiaalsusega seotud seadusi.

:::image type="content" source="media/suggested-segments.png" alt-text="Soovitatavate segmentide leht, kus kuvatakse külgpaanil soovituse üksikasjad.":::

## <a name="suggested-segments-to-improve-your-kpis"></a>Soovitatavad segmendid KPI-de täiustamiseks

Kui kasutate [KPI-de jälgimiseks loodud](measures.md) mõõtühikuid, looge segmendid, et vaadata KPI mõjutusi. Selle teabe abil saate käitada väga sihitud kampaaniat.

Näiteks saate jälgida mõõdikut nimega *TotalSpendPerCustomer*. Ettevõttena soovite, et see arv kasvaks. Valides mõõdu esmaseks atribuudiks, valige atribuudid, mille mõju soovite hinnata. Oletame, et *liikmelisuse aste*, *liikmelisusperiood* ja *hõivamine*. Seejärel saab klientide ülevaade soovitada segmenti, mis ütleb teile, kes mõjutavad seda meedikut enim. Näiteks *Raamatupidajad*, kes on *Kuld* liikmed ja kes on teie äritegevusega *vähemalt viis aastat* olnud, on *TotalspendPerCustomer* suurimaks mõjutaks. Iga soovituse jaoks saate hinnangulise segmendi suuruse. Selle teabe abil saate luua kampaaniaid sihtrühmadele.

## <a name="understand-what-influences-a-customer-attribute"></a>Kliendiatribuudi mõjutamise mõistmine

Esmase atribuudina saate mõõdiku asemel valida kliendi atribuudi. Teie mõjutavate atribuutide valiku põhjal loob tehisintellekti mudel rea ettepanekuid, mis näitavad, kuidas valitud atribuudid mõjutavad peamist atribuuti.

Näiteks saate esmase atribuudina valida *Preemiate liige (Jah/Ei)*. *Ametiaeg*, *Amet* ja *Tugiteenuste arv* on määratud muudeks mõjutavateks atribuutideks. Tehisintellekti mudel võiks soovitada segmente, mille liikmeteks on enamasti kahe ametiaastaga IT-spetsialistid. Veel üks ettepanek on, et rõhutada võiks raamatupidajaid, kelle ametiaeg on üle ühe aasta ja vähem kui kolm tugipiletit, on preemialiikmed.

## <a name="artificial-intelligence-usage"></a>Tehisintellekti kasutamine

Kasutades esmast atribuuti ja mõjutavaid atribuute, soovitab otsustuspuu algoritm huvitavaid segmente. Ettepanekud põhinevad reeglitel või mustritel, mille tehisintellekti algoritm üles võttis. Soovitustena kuvatakse ainult keskmisest elanikkonnast oluliselt erinevad segmendid. Võrdlus keskmise populatsiooniga põhineb valitud mõõdikul või põhiatribuudil.

### <a name="responsible-ai"></a>Vastutustundlik tehisintellekt

Soovitatud segmentide puhul saate valida atribuudid uute segmentide loomiseks ja valitud andmete töötlemiseks. Atribuutide, sealhulgas tundlike atribuutide, nagu rass, seksuaalne sättumus või sugu, valimisel peate tagama, et saate ja peaksite neid andmeid töötlema. Vastutate kõigi teie ettevõtte suhtes kohaldatavate õigusaktide täitmise eest ning järgite oma asutuse põhimõtteid ja privaatsuspoliitikaid.

### <a name="different-results-for-primary-attributes-with-categorical-and-numeric-values"></a>Erinevad tulemused peamiste atribuutide jaoks kategooriliste ja arvuliste väärtustega

Segmendisoovitused on erinevad, kui valite esmase atribuudina arvatribuudi või kategorilise atribuudi. Kategoorilise atribuudi väärtused sisaldavad kahte või enamat kategooriat või tüüpi. Numbriline atribuut sisaldab kvantitatiivseid andmeid ja sellega on seotud mõõtmismeel.

Kui süsteemi põhiatribuudiks on arvatribuut, näiteks *aastane sissetulek* või *liikmesperiood*, soovitab süsteem segmente, mille arvatribuudi keskmine väärtus on kõigi klientidega võrreldes suurem või väiksem.

Kategoriseeriv atribuut, nagu *kliendi rahulolu* esmase atribuudina, hõlmab soovitatavaid segmente, mille protsent teatud kategooriasse kuuluvate klientide seas on suurem või väiksem, võrreldes kõigi sellesse kategooriasse kuuluvate klientide protsendiga. Näiteks valitakse esmaseks atribuudiks *kliendi rahulolu* ja see koosneb kolmest kategooriast (*Madal*, *Keskmine* ja *Kõrge*). Iga kategooria puhul soovitatakse segmente, millel on suurem või väiksem sellesse kategooriasse kuuluvate klientide protsent võrreldes kõigi samasse kategooriasse kuuluvate klientide osakaaluga. Kui 22% kõigist klientidest on *kõrge* rahuloluga, siis sellesse kategooriasse soovitatakse ainult neid segmente, mille *kõrge* rahuloluga klientide osakaal on suurem või väiksem kui 22%. Sarnaselt soovitatakse segmente iga teise kategooria puhul (*Madal* ja *Keskmine*), kui need on statistiliselt olulised.

> [!NOTE]
> Praegu toetame ainult esmaseid kategoorilisi atribuute, millel on kuni 10 kategooriat. Kui soovite näha segmentisoovitusi, mis põhinevad põhiatribuudil, millel on rohkem kui 10 kategooriat, soovitame mõned kategooriad rühmitada, et vähendada kategooriate arvu 10-ni või vähemani. See piirang kehtib ainult esmaste atribuutide puhul. Mõjutavate kategoriseeritavate atribuutide puhul toetame praegu maksimaalselt 100 kategooriat.

## <a name="generate-suggested-segments"></a>Soovitatud segmentide genereerimine

1. Minge jaotisse **Segmendid** ja valige **vahekaart Soovitused (eelvaade).**

1. Valige **Otsi uusi soovitusi** ja valige **Paranda mõõtu/mõõdikut**. Valige **Start**.

   :::image type="content" source="media/suggested-segments-measure.png" alt-text="Soovitatavate segmentide täiustamismeetme valimine.":::

1. Valige esmaseks atribuudiks kliendi atribuut või mõõt ja valige **Edasi**.

1. Valige mõjutavad atribuudid ja valige **Käivita**.

   > [!TIP]
   > Mitme mõjutava atribuudi valimine parandab võimalusi hinnata, kuidas need mõjutavad esmast atribuuti. Ärge kaasake atribuute, mis ei mõjuta peamist atribuuti. Näiteks kui kõik teie kliendid on pärit konkreetsest riigist, ärge lisage *riigi* atribuuti, kuna see ei mõjuta väljundit.

Sõltuvalt kliendiprofiilide arvust ja valitud atribuutidest võib valitud atribuutide töötlemine võtta paar minutit.

## <a name="manage-suggested-segments"></a>Soovitatud segmentide haldamine

Minge jaotisse **Segmendid** ja valige **vahekaart Soovitused (eelvaade).** **Valige jaotises Atribuudipõhised segmendisoovitused** soovitatud segment saadaolevate toimingute vaatamiseks.

- **Vaadake** soovitatud segmendi üksikasju ja atribuudi väärtusi või reegleid, mida tehisintellekti mudel õppis.
- **Salvestage soovitus segmendina** segmendina. See kuvatakse vahekaardil **Kõik segmendid** ja seda [saab värskendada, redigeerida või kustutada](segments.md).
- **Redigeerige atribuute** ja muutke konfigureeritud atribuute, mis asendavad praegused soovitused.
- **Värskendage soovitusi** soovituste värskendamiseks, säilitades konfigureeritud atribuudid.

## <a name="limitations"></a>Piirangud

1. Segmendi hinnanguline sobimatus: kui valite tühjasid väärtusi sisaldava esmase atribuudi, võib see mõjutada segmendisoovitustes segmendi hinnangulist mahtu. Sellise segmendi salvestamisel võib segmendi tegelik suurus erineda esialgsest hinnangust.

2. Tõeväärtuse tüüpi peamised atribuudid ei tööta: praegu toetame peamise atribuudina ainult sõnede ja numbrite tüüpi andmeid.

3. Soovitatud segmendid pole piisavalt erinevad: pidage meeles, et valitud atribuudid ja nende omaduste väärtuste jaotus mõjutavad tulemusi. Erinevate tulemuste saamiseks võite muuta oma mõjutavaid atribuute või isegi peamist atribuuti.

[!INCLUDE [footer-include](includes/footer-banner.md)]