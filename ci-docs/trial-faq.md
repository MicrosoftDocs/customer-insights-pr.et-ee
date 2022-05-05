---
title: Prooviversioon FAQ - Dynamics 365 Customer Insights
description: Vastused kõige levinumatele rakenduse Customer Insights prooviversiooni seadistamise ja haldamisega seotud küsimustele. Vaadake, kuidas lahendada platvormi ja rakendusega seotud probleeme.
author: m-hartmann
ms.author: mhart
ms.date: 02/10/2022
ms.topic: get-started
ms.custom: template-trial-faq
ms.reviewer: jeffhar
manager: shellyha
ms.openlocfilehash: 4a269a223efa08f71db09eef2ec9a8f8a077f7a7
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8641803"
---
# <a name="dynamics-365-customer-insights-trial-faq"></a>Dynamics 365 Customer Insights’i prooviversiooni KKK

## <a name="sign-up"></a>Registreerumine

### <a name="what-are-the-system-requirements-for-the-trial"></a>Millised on süsteeminõuded prooviversiooni jaoks?

See rakendus on pilvepõhine teenus, mis ei nõua spetsiaalset tarkvara peale ajakohase veebibrauseri, kuigi mõned piirangud siiski rakenduvad. Parima prooviversiooni kogemuse jaoks vältige sisenemist proovisaidile inkognito režiimis ja valige teile kõige lähima prooviversiooni asukoht. [Lisateave veebirakenduse nõuete kohta.](/power-platform/admin/web-application-requirements)

### <a name="how-do-i-sign-up-for-the-trial-without-a-microsoft-365-tenant"></a>Kuidas registreeruda prooviversiooni kasutajaks ilma Microsoft 365 rentnikuta?

Saate sisestada muu kui tööga seotud meiliaadressi ning me loome teile konto ja rentniku.

### <a name="can-i-sign-up-for-multiple-dynamics-365-apps-such-as-sales-marketing-and-customer-service"></a>Kas saan registreeruda mitme Dynamics 365 rakenduse kasutajaks (nt Sales, Marketing ja Customer Service)?

Jah, saate. Kõigi saadaolevate prooviversioonide nägemiseks [külastage prooviversioonide keskuse lehte](https://dynamics.microsoft.com/dynamics-365-free-trial). Saate eri prooviversioonide kasutajaks registreerumisel kasutada sama meilikontot. Küll aga ei saa samal proovisaidil olla mitu rakendust. Iga prooviversioon on erineval organisatsioonil ja URL-il. Prooviversiooni andmeid ei jagata rakenduste vahel.

## <a name="trial-app"></a>Rakenduse prooviversioon

### <a name="i-didnt-receive-the-trial-details-email-after-signing-up-what-should-i-do"></a>Mida pean tegema, kui ma ei saanud pärast registreerumist prooviversiooni üksikasjade meili?

Kui registreerute prooviversiooni kasutajaks, saadetakse teile e-kiri prooviversiooni üksikasjadega. Kui te ei näe e-kirja oma sisendkaustas, kontrollige rämpsposti kausta. Teise võimalusena võite rakendusele juurdepääsemiseks teha järgmist.

1. Minge proovisaidile ja valige suvand **Proovi tasuta**.
1. Sisestage meiliaadressi ID, mida kasutasite prooviversiooni kasutajaks registreerimisel. Teid suunatakse proovirakendusse.

### <a name="how-do-i-add-more-users-to-a-trial"></a>Kuidas saan prooviversiooni rohkem kasutajaid lisada?

Kasutajate lisamiseks minge [Microsoft 365 halduskeskusesse](https://admin.microsoft.com), kasutades prooviversiooni administraatori kontot. Kasutajate lisamiseks (maksimaalselt prooviversiooni litsentsile kehtestatud piirarvu järgi) järgige [halduskeskuse juhiseid](/microsoft-365/admin/add-users/add-users). Kui lisataval kasutajal Microsoft 365 on juba konto, määrake talle prooviorganisatsioonis sobiv turberoll. Lisateavet leiate teemast [Kasutajale turberoll määramine](/power-platform/admin/create-users-assign-online-security-roles#assign-a-security-role-to-a-user).

### <a name="how-many-users-can-i-add-to-my-trial-environment"></a>Mitu kasutajat saab proovikeskkonda lisada?

Proovikeskkonda saate lisada piiramata arvu kasutajaid.

### <a name="how-do-i-reset-the-trial-environment"></a>Kuidas proovikeskkonda lähtestada?

Proovikeskkonda ei saa lähtestada. Küll aga võite ära oodata prooviperioodi lõpu ja seejärel registreeruda uuesti uue prooviversiooni saamiseks.

## <a name="trial-expiration-and-extension"></a>Prooviversiooni aegumine ja pikendamine

### <a name="how-do-i-extend-the-trial"></a>Kuidas prooviversiooni pikendada?

Prooviversiooni saate rakenduse sees laiendada. Saate prooviversiooni ühe korra pikendada.

### <a name="can-i-convert-the-trial-to-a-paid-license"></a>Kas prooviversiooni saab teisendada tasuliseks litsentsiks?

Üldiselt soovitame Customer Insights tasulisele versioonile üleminekul alustada värskelt oma andmetega. 

Soovi korral, kui kasutate ainult Customer Insightsi, saate kopeerida oma andmed proovikeskkonnast, kui ostate Customer Insightsi. Sätete migreerimiseks proovikeskkonnast tasulisesse keskkonda peate olema Customer Insightsi prooviversiooni administraator ja rentniku Microsoft 365 üldadministraator või dynamics 365 administraator teie asutuses. 

Pärast esmakordset Customer Insights -i tasulisesse eksemplari sisselogimist palutakse teil luua uus keskkond. Selle protsessi käigus saate kopeerida konfiguratsiooni olemasolevast keskkonnast ja migreerida enamiku sätetest. Kui teil on ülal nimetatud õigused, kuvatakse selles loendis proovikeskkond. Lisateavet leiate teemast [Keskkonna konfiguratsiooni kopeerimine](manage-environments.md#copy-the-environment-configuration).

### <a name="what-are-the-trial-limits-and-quotas"></a>Millised on prooviversiooni piirangud ja kvoodid?

- Customer Insightsi prooviversiooni ajal väljundandmete talletamiseks ei saa kasutada oma Azure Data Lake'i salvestuskontot. Siiski saate andmeid tuua Data Lake Storage -i kontolt.
- Saate talletada kuni 3 GB andmeid Dataverse-i keskkonnas, mis luuakse automaatselt Customer Insights'i prooviversiooni käivitamisel.

## <a name="customer-insights-specific-questions"></a>Konkreetsed küsimused Customer Insights’i kohta

### <a name="how-do-i-start-using-the-trial"></a>Kuidas alustada prooviversiooni kasutamist?

Pärast prooviversiooni kasutajaks registreerimist jõuate rakenduse põhikuvale. Põhikuval on kasutusjuhendite ja õpetuste lingid. Lisateabe saamiseks külastage prooviversiooni seadistuslehel jaotises [Täiendavad materjalid](trial-signup.md#additional-resources) olevaid linke.

### <a name="what-features-are-available-in-the-trial"></a>Millised funktsioonid on prooviversioonis saadaval?

Enamik Customer Insights'i võimaluste funktsioone on saadaval prooviversioonis.

Järgmised funktsioonid **pole saadaval**. 
- Te ei saa luua uusi keskkondi, mis kasutavad teie enda Azure Data Lake salvestuskontot.
- Proovikeskkonda ei saa kustutada. 

### <a name="how-long-does-the-trial-last"></a>Kui kaua prooviversioon kestab?

Customer Insights'i prooviversioon kestab 30 päeva. Kui te proovikeskkonda sisse logite, siis saate prooviperioodi pikendada ühe korra pärast 23 päeva möödumist.

### <a name="how-do-i-remove-sample-data-from-the-trial"></a>Kuidas saan prooviversioonist eemaldada näidisandmed?

Prooviversioonist te ei saa näidisandmeid eemaldada.
