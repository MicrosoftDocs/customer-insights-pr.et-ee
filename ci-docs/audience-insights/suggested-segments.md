---
title: Masinõpe soovitatavad segmendid
description: Las masinõpe aitab teil leida uusi ja huvitavaid segmente, mis põhinevad kliendi atribuutidel.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
ms.openlocfilehash: bbc22adcd7b6e756fa6128abd855795de7480f2d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597087"
---
# <a name="suggested-segments-preview"></a>Soovitatud segmendid (eelvaade)

Tehisintellekti mudeli abil saate avastada oma klientide huvitavaid segmente. See masinõppega funktsioon soovitab mõõdikuid või kliendi atribuute põhinevaid segmente. See võib aidata teie KPI-sid parandada või paremini mõista atribuutide mõju teiste atribuutide kontekstis. 

> [!NOTE]
> Pakutud segmentide funktsioon kasutab andmete hindamiseks ja nende põhjal prognooside tegemiseks automatiseeritud vahendeid ning seetõttu on seda võimalik kasutada profileerimise meetodina, nagu see mõiste on määratletud isikuandmete kaitse üldmääruses (GDPR). Selle funktsiooni kasutamise kohta andmete töötlemisel võib kehtida kas GDPR või muud seadused või määrused. Teie vastutate selle eest, et Dynamics 365 Customer Insightsi kasutades (sh antud funktsiooni kasutades) järgite te kõiki kohaldatavaid seadusi ja määrusi, sh eraelu puutumatuse, isikuandmete, biomeetriliste andmete, andmekaitse ja suhtluse konfidentsiaalsusega seotud seadusi.

:::image type="content" source="media/suggested-segments-details.png" alt-text="Kliendiülevaadete soovitatud segmentide leht, kus kuvatakse külgpaanil soovituse üksikasjad.":::

## <a name="suggested-segments-to-improve-your-kpis"></a>Soovitatavad segmendid KPI-de täiustamiseks

Sihtrühma ülevaadete kasutajana on tõenäoliselt [loodud mitmeid mõõdikuid](measures.md), mis aitavad jälgida oma juhtimismõõdikuid (KPI-sid). Oluline on mõista, kuidas teatud atribuudid mõjutavad seda KPI-d segmentide loomisel ja täpselt sihitud kampaania korraldamisel.   
Näiteks saate jälgida mõõdikut nimega *TotalSpendPerCustomer*. Ettevõttena soovite, et see arv kasvaks. Mõõdiku valimine peamiseks atribuudiks võimaldab teil valida atribuudid, mida soovite mõjutamiseks hinnata. Oletame, et *liikmelisuse aste*, *liikmelisusperiood* ja *hõivamine*. Seejärel saab klientide ülevaade soovitada segmenti, mis ütleb teile, kes mõjutavad seda meedikut enim. Näiteks *Raamatupidajad*, kes on *Kuld* liikmed ja kes on teie äritegevusega *vähemalt viis aastat* olnud, on *TotalspendPerCustomer* suurimaks mõjutaks. Iga soovituse jaoks saate hinnangulise segmendi suuruse. Selle teabe abil saate luua kampaaniaid sihtrühmadele.

## <a name="understand-what-influences-a-customer-attribute"></a>Kliendiatribuudi mõjutamise mõistmine

Esmase atribuudina saate mõõdiku asemel valida kliendi atribuudi. Teie mõjutavate atribuutide valiku põhjal loob tehisintellekti mudel rea ettepanekuid, mis näitavad, kuidas valitud atribuudid mõjutavad peamist atribuuti.   
Näiteks saate esmase atribuudina valida *Preemiate liige (Jah/Ei)*. *Ametiaeg*, *Amet* ja *Tugiteenuste arv* on määratud muudeks mõjutavateks atribuutideks. Tehisintellekti mudel võiks soovitada segmente, mille liikmeteks on enamasti kahe ametiaastaga IT-spetsialistid. Veel üks ettepanek on, et rõhutada võiks raamatupidajaid, kelle ametiaeg on üle ühe aasta ja vähem kui kolm tugipiletit, on preemialiikmed. 

## <a name="artificial-intelligence-usage"></a>Tehisintellekti kasutamine

Kasutades esmast atribuuti ja mõjutavaid atribuute, soovitab otsustuspuu algoritm huvitavaid segmente. Ettepanekud põhinevad reeglitel või mustritel, mille tehisintellekti algoritm üles võttis. Soovitustena kuvatakse ainult keskmisest elanikkonnast oluliselt erinevad segmendid. Võrdlus keskmise populatsiooniga põhineb valitud mõõdikul või põhiatribuudil.

### <a name="responsible-ai"></a>Vastutustundlik tehisintellekt

Soovitatavad segmendid võimaldab valida atribuute uute segmentide loomiseks ja valitud andmete töötlemiseks. Atribuutide, sealhulgas tundlike atribuutide, nagu rass, seksuaalne sättumus või sugu, valimisel peate tagama, et saate ja peaksite neid andmeid töötlema. Vastutate kõigi teie ettevõtte suhtes kohaldatavate õigusaktide täitmise eest ning järgite oma asutuse põhimõtteid ja privaatsuspoliitikaid.

### <a name="different-results-for-primary-attributes-with-categorical-and-numeric-values"></a>Erinevad tulemused peamiste atribuutide jaoks kategooriliste ja arvuliste väärtustega

Segmendisoovitused on erinevad, kui valite esmase atribuudina arvatribuudi või kategorilise atribuudi. Kategoorilise atribuudi väärtused sisaldavad kahte või enamat kategooriat või tüüpi. Numbriline atribuut sisaldab kvantitatiivseid andmeid ja sellega on seotud mõõtmismeel.

Kui süsteemi põhiatribuudiks on arvatribuut, näiteks *aastane sissetulek* või *liikmesperiood*, soovitab süsteem segmente, mille arvatribuudi keskmine väärtus on kõigi klientidega võrreldes suurem või väiksem.

Kategoriseeriv atribuut, nagu *kliendi rahulolu* esmase atribuudina, hõlmab soovitatavaid segmente, mille protsent teatud kategooriasse kuuluvate klientide seas on suurem või väiksem, võrreldes kõigi sellesse kategooriasse kuuluvate klientide protsendiga. Näiteks valitakse esmaseks atribuudiks *kliendi rahulolu* ja see koosneb kolmest kategooriast (*Madal*, *Keskmine* ja *Kõrge*). Iga kategooria puhul soovitatakse segmente, mille protsent sellesse kategooriasse kuuluvate klientide seas on oluliselt suurem või väiksem, võrreldes kõigi sama kategooria klientide osaga. Kui 22% klientidest on *hea* rahuloluga, siis soovitatakse selles kategoorias kasutada ainult segmente, mille klientide osa on oluliselt suurem või väiksem osa *kõrge* kliendirahuloluga osa, võrreldes 22%-ga, mida antud kategoorias soovitatakse. Sarnaselt soovitatakse segmente iga teise kategooria puhul (*Madal* ja *Keskmine*), kui need on statistiliselt olulised.

> [!NOTE]
> Praegu toetame ainult esmaseid kategoorilisi atribuute, millel on kuni 10 kategooriat. Kui soovite näha segmendisoovitusi, mis põhinevad enam kui 10 kategooriat omaval põhiatribuudil, soovitame grupeerida mõned kategooriad, et vähendada kategooriate arvu 10-le või vähemale. See piirang kehtib ainult esmaste atribuutide puhul. Mõjutavate kategoriseeritavate atribuutide puhul toetame praegu maksimaalselt 100 kategooriat.

## <a name="generate-suggested-segments"></a>Soovitatud segmentide genereerimine

1. Liikuge jaotisse **Segmendid**.

1. Valige vahekaart **Soovitused (eelvaade)**.

1. Juhendatud kogemuse saamiseks valige **Uute soovituste hankimine**.

1. Valige peamiseks atribuudiks mõõdik või kliendi atribuut ja valige **Järgmine**.

   :::image type="content" source="media/suggested-segments-primary-attribute.png" alt-text="Soovitatavate segmentide soovituste jaoks esmase atribuudi valimine.":::

1. Valige mõjutatavad atribuudid ja seejärel **Salvesta**.
   
   > [!TIP]
   > Mitme mõjutava atribuudi valimine parandab võimalusi hinnata, kuidas need mõjutavad esmast atribuuti. Ärge lisage atribuute, mis ei mõjuta esmast atribuuti. Näiteks kui kõik teie kliendid on pärit konkreetsest riigist, ärge lisage *riigi* atribuuti, kuna see ei mõjuta väljundit.

1. Sõltuvalt kliendiprofiilide arvust ja valitud atribuutidest võib valitud atribuutide töötlemine võtta paar minutit. 

## <a name="view-details-of-a-suggested-segment"></a>Vaadake soovitatud segmendi üksikasju

Kui AI-mudel on soovitusi loonud, leiate need jaotisest **Segmendid** > **Soovitused (eelvaade)**.
 
Valige soovitatud segment, et vaadata selle soovituse üksikasju, sealhulgas keskmise väärtuse ja segmendi liikmete arvu võrdlust. Saate vaadata ka atribuudiväärtusi või reegleid, mille tehisintellekti mudel õppis valitud lõiku soovitama.

## <a name="save-a-suggestion-as-a-segment"></a>Salvestage soovitus segmendina

1. Minge jaotisesse **Segmendid** > **Soovitused (eelvaade)**.

1. Valige segment, mille soovite salvestada. 

1. Valige külgpaanil käsk **Salvesta segmendina**. 

1. Pärast segmendi salvestamist kuvatakse see segmentide loendis vahekaardil **Kõik segmendid**. Seda saab nüüd [värskendada, redigeerida või kustutada nagu mis tahes muud segmenti](segments.md).

## <a name="refresh-or-edit-a-set-of-suggestions"></a>Värskendage või muutke soovituste komplekti

1. Minge jaotisesse **Segmendid** > **Soovitused (eelvaade)**.

1. Valige suvand **Värskenda soovitused**, et värskendada soovitusi konfigureeritud atribuutide säilitamise ajal. Või valige **Redigeeri atribuute**, et muuta konfigureeritud atribuute. Süsteem taaskäivitab tehisintellekti mudeli, genereerib uusimate andmete põhjal segmentide soovitused ja asendab praegused ettepanekud.

## <a name="limitations"></a>Piirangud

1. Segmendi hinnanguline sobimatus: kui valite tühjasid väärtusi sisaldava esmase atribuudi, võib see mõjutada segmendisoovitustes segmendi hinnangulist mahtu. Sellise segmendi salvestamisel võib segmendi tegelik suurus erineda esialgsest hinnangust.
 
2. Tõeväärtuse tüüpi peamised atribuudid ei tööta: praegu toetame peamise atribuudina ainult sõnede ja numbrite tüüpi andmeid.

3. Soovitatud segmendid pole piisavalt erinevad: pidage meeles, et valitud atribuudid ja nende omaduste väärtuste jaotus mõjutavad tulemusi. Erinevate tulemuste saamiseks võite muuta oma mõjutavaid atribuute või isegi peamist atribuuti.



[!INCLUDE[footer-include](../includes/footer-banner.md)]