---
title: Masinõppe stuudio (klassikaline) eksperimendid
description: Kasutage masinõppe stuudio (klassikaline) mudeleid rakenduses Dynamics 365 Customer Insights.
ms.date: 12/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: ameetj
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 71881f7e1f9448fe0a7d6d92b8102b8b42de7c2a
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598334"
---
# <a name="use-models-based-on-azure-machine-learning-studio-classic"></a>Kasutage Azure'i masinõppe stuudio (klassikaline) põhiseid mudeleid

Dynamics 365 Customer Insightsis olevad koondatud andmed on allikaks masinõppemudelite loomisele, mis võivad luua täiendavaid äriülevaateid. Customer Insights integreerub masinõppe stuudioga (klassikaline), et saaksite kasutada omaenda kohandatud mudeleid. Selleks et näha, kuidas Azure'i masinõppe abil arendatud mudelid integreeruvad Customer Insightsiga, lugege teemat [Azure'i masinõppe eksperimendid](azure-machine-learning-experiments.md).

## <a name="prerequisites"></a>Eeltingimused

- Juurdepääs Customer Insightsi
- Aktiivne Azure Enterprise'i tellimus
- [Kliendi koondprofiilid](data-unification.md)
- [Olemi eksportimine Azure'i bloobi salvestusruumi](export-azure-blob-storage.md) seadistatud

## <a name="set-up-machine-learning-studio-classic"></a>Klassikalise masinõppe stuudio seadistamine

Esimese sammuna peame looma masinõppe stuudio (klassikaline) jaoks tööruumi ja stuudio avama.

1. Avage[https://www.portal.azure.com](https://www.portal.azure.com/) ja logige sisse.

1. Valige **Loo ressurss**.

1. OTsige **Masinõppe stuudio tööruum** ja valige **Loo**.

1. Sisestage nõutavad üksikasjad, et [luua tööruum](/azure/machine-learning/studio/create-workspace). Valige **Veebiteenuse plaani hinnajärk** imporditavate andmete hulga alusel. Parima tulemuse saamiseks valige **Asukoht**, mis on teile geograafiliselt kõige lähemal.

1. Pärast ressursi loomist kuvatakse masinõppe stuudio tööruumi armatuurlaud. Valige **Käivita masinõppe stuudio**.

   ![Azure'i masinõppe stuudio kasutajaliides](media/azure-machine-learning-studio.png)

## <a name="work-with-azure-machine-learning-studio"></a>Azure'i masinõppe stuudioga töötamine

Nüüd saate luua uue eksperimendi või importida olemasoleva eksperimendi malli näidiste galeriist. Näidiseksperimendid on olemas kolme tavalise stsenaariumi jaoks.

- [Voolavuse prognoos](#churn-analysis)

- [Kliendi eluea väärtus](#customer-lifetime-value-prediction)

- [Tootesoovitus või järgmine parim toiming](#productrecommendation-or-next-best-action)

1. Kui loote uue katse või kasutate galeriist katsemalli, peate konfigureerima valiku **Impordi andmed** atribuudid. Kasutage juhendatud kogemust või sisestage otse üksikasjad, et pääseda juurde Azure'i bloobimälule, mis sisaldab teie andmeid.  

   ![Azure'i masinõppe stuudio katse](media/azure-machine-learning-studio-experiment.png)

1. Nüüd saate ehitada kohandatud töötlemiskonveieri andmete puhastamiseks ja eeltöötlemiseks, funktsioonide ekstraheerimiseks ja sobiva mudeli treenimiseks.

1. Testige ja optimeerige mudeli jõudlust.

1. Kui olete mudeli kvaliteediga rahul, valige **Seadistage veebiteenus** > **Ennustatav veebiteenus**. See suvand impordib treenitud mudeli ja featuriseerimiskonveieri treenitud katsest ennustavasse teenindusse. Ennustav teenus võib prognooside tegemiseks treeningukatses kasutatud skeemi abil võtta veel ühe sisendandmete komplekti.

   ![Ennustava veebiteenuse seadistamine](media/predictive-webservice-control.png)

1. Kui ennustava veebiteenuse katse on edukas, saate selle juurutada automaatseks ajastamiseks. Kui soovite, et veebiteenus töötaks rakendusega Customer Insights, valige käsk **Juuruta veebiteenus** > **Juuruta veebiteenus [uus] eelversioon**. [Lisateave veebiteenuse juurutamise kohta](/azure/machine-learning/studio/deploy-a-machine-learning-web-service).

   ![Ennustava veebiteenuse juurutamine](media/predictive-webservice-deploy.png)

## <a name="sample-models-from-the-gallery"></a>Mudelite näidised galeriist

Selle artikli mudelite jaoks kasutame Contoso hotelli väljamõeldud stsenaariumi. Contoso hotell kogub järgmisi andmeid:

- Hotellis viibimise tegevusest koosnevad CRM-i andmed. Andmekogum sisaldab teavet iga registreeritud kliendi peatumise kuupäevade kohta. See sisaldab ka teavet broneeringu, tubade tüüpide, kulutamise üksikasjade kohta ja nii edasi. Andmed ulatuvad üle nelja aasta, alates jaanuarist 2014 kuni jaanuarist 2018.
- Hotellikülaliste kliendiprofiilid. Need profiilid sisaldavad teavet iga kliendi kohta, sh nime, sünnikuupäev, postiaadress, sugu ja telefoninumber.
- Hotelli pakutavate teenuste kasutus, näiteks spaa, pesumaja, WiFi või kuller. See teave logitakse iga registreeritud kliendi jaoks. Tavaliselt on teenuste kasutamine seotud hotellis peatumisega. Kliendid saavad teenust kasutada ka ilma hotellis viibimata.

## <a name="churn-analysis"></a>Voolavuse analüüs

Voolavuse analüüs rakendub erinevatele ärialadele. Selles näites käsitleme teenuste voolavust, eriti ülalkirjeldatud hotelliteenuste kontekstis. See on toimiv näide otsast lõpuni kasutatava mudeli konveieri kohta, mida saab kasutada lähtepunktina mis tahes muud tüüpi voolavusmudeli jaoks.

### <a name="definition-of-churn"></a>Voolavuse määratlus

Voolavuse määratlus võib stsenaariumi põhjal erineda. Selles näites peab külaline, kes pole viimase aasta jooksul hotelli külastanud, olema märgistatud voolavana.  

Eksperimendi malli saab importida galeriist. Esiteks veenduge, et impordiksite valikud **Hotellis viibimise tegevus**, **Kliendiandmed** ja **Teenusekasutuse andmed** Azure'i bloobimälust.

   ![Andmete importimine voolavuse mudeli jaoks](media/import-data-azure-blob-storage.png)

### <a name="featurization"></a>Featuriseerimine

Vastavalt voolavuse määratlusele, tuvastame kõigepealt algsed funktsioonid, mis mõjutavad silti. Seejärel töötleme need algsed funktsioonid numbrilisteks funktsioonideks, mida saab kasutada masinõppe mudelitega. Andmete integreerimine toimub Customer Insightsis, nii et saame need tabelid ühendada üksuse *Kliendi ID* abil.

   ![Liituge imporditud andmetega](media/join-imported-data.png)

Voolavusanalüüsi mudeli ehitamise featuriseerimine võib olla pisut keeruline. Andmed on aja funktsioon, mis algab iga päev registreeritud hotelli tegevusega. Featuriseerimise ajal soovime dünaamilistest andmetest genereerida staatilisi funktsioone. Siinjuhul loome hotellitegevuste alusel mitu funktsiooni, millel on aastane liikuv ajavahemik. Laiendame ka kategooriafunktsioone, näiteks toa tüüp või broneeringutüüp eraldi funktsioonideks, kasutades ühe korraga kodeerimist.  

Lõplik loend funktsioonidest:

| **Arv**  | **Original_Column**          | **Tuletatud funktsioonid**                                                                                                                      |
|-------------|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 1           | Ruumi tüüp                    | RoomTypeLargeCount, RoomTypeSmallCount                                                                                                    |
| 2           | Broneeringu tüüp                 | BookingTypeOnlineCount, BookingTypePhoneCallCount                                                                                         |
| 3           | Reisi kategooria              | TravelCategoryBusinessCount, TravelCategoryLeisureCount                                                                                   |
| 4           | Kulutatud dollarit                | TotalDollarSpent                                                                                                                          |
| 5           | Sisse- ja väljaregistreerimise kuupäevad  | StayDayCount, StayDayCount2016, StayDayCount2015, StayDayCount2014, StayCount, StayCount2016. StayCount2015, StayCount2014                |
| 6           | Teenusekasutus                | UsageTenure, ConciergeUsage, CourierUsage, DryCleaningUsage, GymUsage, PhoneUsage, RestaurantUsage, SpaUsage, TelevisionUsage, WifiUsage  |

### <a name="model-selection"></a>Mudeli valik

Nüüd tuleb valida optimaalne algoritm, mida kasutada. Sel juhul põhinevad enamik funktsioone kategooriafunktsioonidel. Tavaliselt toimivad otsusepuupõhised mudelid hästi. Kui funktsioonid on ainult numbrilised, võivad neurovõrgud olla parem valik. Tugivektormasin (SVM) on sellistes olukordades samuti hea kandidaat; parima jõudluse saamiseks on vaja üsna palju häälestamist. Valime esimesena mudeli **Kahe klassiga võimendusega otsusepuu** ja seejärel teise mudelina **Kahe klassiga SVM**. Azure'i masinõppe stuudio võimaldab teil teha A/B-testimist, seega on kasulik alustada kahe mudeliga ühe asemel.

Järgmine pilt näitab mudeli treenimise ja hindamise konveierit Azure'i masinõppe stuudiost.

![Azure'i masinõppe stuudio voolavusmudel](media/azure-machine-learning-model.png)

Rakendame ka meetodit nimega **Permutatsiooni funktsiooni olulisus**, mis on oluline mudeli optimeerimise korral. Sisseehitatud mudelitel on vähe või puudub täielik ülevaade mõne konkreetse funktsiooni mõjust lõplikule prognoosile. Funktsiooni olulisuse kalkulaator kasutab kohandatud algoritmi, et arvutada üksikute funktsioonide mõju konkreetse mudeli tulemusele. Funktsiooni olulisus normaliseeritakse vahemikus +1 kuni -1. Negatiivne mõju tähendab, et asjaomasel funktsioonil on tulemusele mittesoovitav mõju ja see tuleks mudelist eemaldada. Positiivne mõju näitab, et funktsioon aitab prognoosimisele palju kaasa. Need väärtused pole korrelatsiooni koefitsiendid, kuna need on erinevad mõõdikud. Lisateavet leiate teemast [Permutatsiooni funktsiooni olulisus](/azure/machine-learning/studio-module-reference/permutation-feature-importance).

Kogu [voolavuse eksperiment on saadaval Azure'i AI galeriis](https://gallery.azure.ai/Experiment/Hotel-Churn-Predictive-Exp).

## <a name="customer-lifetime-value-prediction"></a>Kliendi eluea väärtuse prognoos

Kliendi eluea väärtuse (CLTV) arvutamine on üks olulisemaid mõõdikuid, mida ettevõte saab kasutada oma klientide hindamiseks ja segmentimiseks. Hotelliettevõtte jaoks on ülioluline tunda oma kliente. Näiteks on oluliseks teabeks häid kliente moodustavate tegurite mõistmine. See aitab hotelli juhtkonnal hinnata, millistele funktsioonidele nad peavad keskenduma ja mida tuleks tasuvamate klientide rahuldamiseks parandada. Need otsused võivad otseselt mõjutada müüki ja töötasu.  

### <a name="definition-of-cltv"></a>CLTV määratlus

Selle näite puhul määratleme kliendi CLTV kui kogu dollarisumma, mille klient eeldatavalt järgmise 365 päeva jooksul kulutab. Selle väärtuse prognoosimiseks kasutame kõigi klientide viimase kolme aasta andmeid.

### <a name="featurization"></a>Featuriseerimine

Sellisel juhul saab featuriseerimine olema päris sarnane voolavuse stsenaariumiga. Sildid ja prognoositavad väärtused erinevad aga ülalmääratletutest.

### <a name="model-selection"></a>Mudeli valik

CLTV prognoosimine on regressiooniprobleem, kuna prognoositav väärtus on positiivse väärtusega pidev muutuja. Funktsiooni atribuutide põhjal valime mudeli treenimiseks esimesena algoritmi **Võimendatud otsusepuu regressioon** ja teisena **Neurovõrgu regressioon**.

## <a name="product-recommendation-or-next-best-action"></a>Tootesoovitus või järgmine parim tegevus

Tootesoovitust hotelli stsenaariumis tõlgendatakse kui hotelli poolt klientidele pakutavate teenuste soovitamist. Eesmärk on valida klientidele sobivad teenused nii, et nende kasutamine oleks maksimaalne. See sarnaneb filmisoovitustega video voogesituse teenuse kasutajatele.

### <a name="definition-of-product-recommendation-or-next-best-action"></a>Toote soovituse või järgmise parima toimingu määratlus

Määratleme eesmärgi kui teenusekasutuse maksimeerimine dollarisummas, pakkudes hotelliklientidele nende huvidele vastavaid parimaid teenuseid.

### <a name="featurization"></a>Featuriseerimine

Nagu voolavusmudeli puhul, ühendame hotelli ServiceCustomerID kliendi ID-ga, et luua järjepidevalt soovitusi kliendi ID alusel.

![Featuriseerimise soovituse näidis](media/azure-machine-learning-model-featurization.png)

Andmed pärinevad kolmest erinevast olemist ja funktsioonid on neist tuletatud. Soovituseprobleemi kirjeldus on erinev võrreldes voolavuse või CLTV stsenaariumidega. Soovitusmudel vajab sisendandmeid kolme tunnuste komplekti kujul.

### <a name="model-selection"></a>Mudeli valik

Prognoosime tooteid või teenuseid kasutades algoritmi nimega **Tikutoosialgoritmipõhise soovitaja treenimine**, et treenida soovitusmudelit.

![Tootesoovituse algoritm](media/azure-machine-learning-model-recommendation-algorithm.png)

Mudeli **Tikutoosialgoritmipõhise soovitaja treenimine** kolm sisendporti kasutavad koolitusteenuse kasutamise andmeid, kliendi kirjeldust (valikuline) ja teenuse kirjeldust. Mudeli hindamiseks on kolm erinevat viisi. Üks on mõeldud mudeli hindamiseks, kus normaliseeritud diskonteeritud kumulatiivse kasvu (NDCG) skoor arvutatakse hinnanguga objektide järjestamiseks. Selles katses on meil NDCG skoor AS 0,97. Kaks muud võimalust on mudeli hindamine kogu soovitatava teenusekataloogi põhjal või ainult selliste kaupade põhjal, mida kasutajad pole varem kasutanud.

Vaadates edasi kogu teenusekataloogi soovituste jaotust, märkame, et telefon, WiFi ja kuller on kõige populaarsemad teenused, mida soovitatakse. See on kooskõlas sellega, mida leidsime teenuse tarbimise andmete jaotustest.

![Soovitusmudeli väljund](media/azure-machine-learning-model-output.png)

Kogu [tootesoovituse eksperimendile pääseb juurde Azure'i AI galerii kaudu.](https://gallery.azure.ai/Experiment/Recommendation-4)

## <a name="integrate-custom-models"></a>Kohandatud mudelite integreerimine

Nende prognooside kasutamiseks Customer Insightsis peate **eksportima** prognoosid koos kliendi ID-dega. [Eksportige need samasse Azure'i boobimällu](/azure/storage/common/storage-import-export-data-from-blobs), kuhu te lähteandmeid ekspordite. Ennustavat veebiteenust saab ajastada regulaarselt käitamiseks ja skooride värskendamiseks.

Kohandatud mudeli loodud andmeid saab kasutada kliendiandmete edasiseks rikastamiseks. Lisateavet vt teemast [Kohandatud masinõppemudelid](custom-models.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]