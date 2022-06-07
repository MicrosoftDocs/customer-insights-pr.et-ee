---
title: Saladuste haldamiseks tooge oma Azure'i võtmehoidla
description: Lugege, kuidas konfigureerida Customer Insights'i kasutama oma Azure'i võtmehoidlat.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: d4f2d5ebc828053c40e22065f4915c4d0f84153f
ms.sourcegitcommit: 6ec4626a185892dfb781d3c7af4384f9c13f3723
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 05/17/2022
ms.locfileid: "8763574"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>Tooge oma Azure võtmehoidla (eelversioon)

Spetsiaalse [Azure'i võtmehoidla](/azure/key-vault/general/basic-concepts) linkimine Customer Insightsi keskkonnaga aitab organisatsioonidel täita vastavusnõudeid.
Sihtotstarbelise võtmehoidla abil saab etappe luua ja kasutada saladusi organisatsiooni vastavuse piirides. Customer Insights saab kasutada Azure Key Vault'i saladusi, et [luua ühendusi](connections.md) kolmandate osapoolte süsteemidega.

## <a name="link-the-key-vault-to-the-customer-insights-environment"></a>Võtmehoidla linkimine Customer Insightsi keskkonnaga

### <a name="prerequisites"></a>eeltingimused

Customer Insightsi võtmehoidla konfigureerimiseks peavad olema täidetud järgmised eeltingimused.

- Teil peab olema aktiivne Azure tellimus.

- Teil on [Customer Insightsis administraatori](permissions.md#admin) roll. Lisateavet kasutajaõiguste kohta [leiate teemast Customer Insights](permissions.md#assign-roles-and-permissions).

- Teil on võtmehoidlas või ressursirühmas, kuhu võtmehoidla kuulub, [Kaastöötaja](/azure/role-based-access-control/built-in-roles#contributor) ja [Kasutaja juurdepääsu administraatori](/azure/role-based-access-control/built-in-roles#user-access-administrator) rollid. Lisateabe jaoks minge [Azure'i rollimäärangute lisamine või eemaldamine Azure portaalist](/azure/role-based-access-control/role-assignments-portal). Kui teil pole võtmehoidlas kasutajajuurdepääsu administraatori rolli, peate Azure'i teenuse subjekti jaoks eraldi seadistama rollipõhised Dynamics 365 Customer Insights juurdepääsu õigused. Järgige samme, et [kasutada Azure'i teenuse printsipaali](connect-service-principal.md) lingitava võtmehoidla jaoks.

- Võtmehoidlal peab olema võtmehoidla tulemüür **keelatud**.

- Võtmehoidla asub Customer Insightsi keskkonnaga samas [Azure'i asukohas](https://azure.microsoft.com/global-infrastructure/geographies/#overview). Customer Insightsi keskkonnapiirkond on loetletud jaotises **Administraatorisüsteem** > **·** > **regiooni** > **kohta**.

### <a name="link-a-key-vault-to-the-environment"></a>Võtmehoidla linkimine keskkonnaga

1. **Avage administraatori** > **turbesüsteem** ja seejärel valige **vahekaart Võtmehoidla**.
1. Tehke paanil **Võtmehoidla** valik **Seadistus**.
1. Valige **Kordustellimus**.
1. Valige võtmehoidla ripploendist **Võtmeloend**. Kui kuvatakse liiga palju võtmehoidlaid, valige otsingutulemite piiramiseks ressursirühm.
1. Nõustuge **Andmete privaatsuse ja privaatsusavaldusega**.
1. Valige **Salvesta**.

:::image type="content" source="media/set-up-azure-key-vault.png" alt-text="Juhised lingitud võtmehoidla seadistamiseks Customer Insightsis.":::

Paanil **Võtmehoidla** on nüüd lingitud võtmehoidla nimi, ressursirühm ja kordustellimus. See on valmis ühenduse seadistamiseks.
Lisateavet selle kohta, millised õigused võtmehoidlas customer Insightsile antakse, leiate [sellest artiklist](#permissions-granted-on-the-key-vault) võtmehoidlas antud õigused.

## <a name="use-the-key-vault-in-the-connection-setup"></a>Kasutage ühenduse seadistamisel võtmehoidlat

[Ühenduste seadistamisel](connections.md) muude tootjate süsteemidega saab lingitud võtmehoidla saladusi kasutada ühenduste konfigureerimiseks.

1. Minge **Administraator** > **Ühendused**.
1. Valige **Lisa ühendus**.
1. Toetatud ühendusetüüpide puhul on saadaval funktsiooni **Kasuta võtmehoidlat** ümberlülitus, kui linkite võtmehoidla.
1. Selle asemel, et saladust käsitsi sisestada, võite valida saladuse nime, mis viitab võtmehoidla saladusse väärtusele.

:::image type="content" source="media/use-key-vault-secret.png" alt-text="Ühenduspaan SFTP-ühenduse abil, mis kasutab Key Vault saladust.":::

## <a name="supported-connection-types"></a>Toetatud ühenduse tüübid

Toetatakse järgmisi [ekspordiühendusi](export-destinations.md):

* [ActiveCampaign](export-active-campaign.md)
* [Autopiloot](export-autopilot.md)
* [DotDigital](export-dotdigital.md)
* [Google Ads](export-google-ads.md)
* [Klaviyo](export-klaviyo.md)
* [LiveRamp](export-liveramp.md)
* [Marketo](export-marketo.md)
* [Omnisend](export-omnisend.md)
* [Salesforce Marketing Cloud](export-salesforce.md)
* [Sendgrid](export-sendgrid.md)
* [Sendinblue](export-sendinblue.md)
* [SFTP](export-sftp.md)

## <a name="permissions-granted-on-the-key-vault"></a>Võtmehoidlas antud õigused

Kui key vault'i juurdepääsupoliitika või [Azure'i rollipõhine juurdepääsukontroll](/azure/key-vault/general/assign-access-policy?tabs=azure-portal)[on lubatud, antakse lingitud võtmehoidla](/azure/key-vault/general/rbac-guide?tabs=azure-cli) customer Insightsile järgmised õigused.

### <a name="key-vault-access-policy"></a>Key Vault'i juurdepääsu poliitika

| Tüüp        | Õigused          |
| ----------- | -------------------- |
| Klahv         | [Too võtmed](/rest/api/keyvault/keys/get-keys/get-keys), [Too võti](/rest/api/keyvault/keys/get-key/get-key)                                 |
| Saladus      | [Hankige saladused](/rest/api/keyvault/secrets/get-secrets/get-secrets), [Hankige saladus](/rest/api/keyvault/secrets/get-secret/get-secret)                     |
| Sert | [Hankige sertifikaadid](/rest/api/keyvault/certificates/get-certificates/get-certificates), [Hankige sertifikaat](/rest/api/keyvault/certificates/get-certificate/get-certificate) |

Eelnevad väärtused on miinimum, mida soovite käivitamise ajal loetleda ja lugeda.

### <a name="azure-role-based-access-control"></a>Azure'i rollipõhine juurdepääsu juhtelement

Customer Insightsi jaoks lisatakse võtmevõlvilugeja ja võtmevõlvi saladuste kasutajarollid. Nende rollide kohta lisateabe saamiseks minge [Azure'i sisseehitatud rollid võtmehoidla andmete analüüsitoimingute jaoks](/azure/key-vault/general/rbac-guide?tabs=azure-cli).

## <a name="recommendations"></a>Soovitused

- Kasutage eraldi või spetsiaalset võtmehoidlat, mis sisaldab ainult Customer Insightsi jaoks vajalikke saladusi. Lugege lisateavet selle kohta, miks [eraldi võtmehoidlad on soovitatavad](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults).

- Järgige [parimaid tavasid, et kasutada võtmehoidlat](/azure/key-vault/general/best-practices#turn-on-logging) juurdepääsu-, varundus-, auditeerimis- ja proovihoidla suvandite auditeerimiseks.

## <a name="frequently-asked-questions"></a>Korduma kippuvad küsimused

### <a name="can-customer-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>Kas Customer Insights saab kirjutada saladusi või kirjutada saladusi võtmehoidlasse?

Ei. Customer Insightsile antakse ainult selle artikli varem antud õiguste jaotises antud õigused [kirjeldatud](#permissions-granted-on-the-key-vault) lugemis- ja loendiõigused. Süsteem ei saa võtmehoidlasse saladusi lisada, kustutada ega üle kirjutada. Samuti on põhjus, miks te ei saa sisestada mandaati, kui ühendus kasutab Key Vault'i.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>Kas ma saan muuta ühenduse Key Vault'i saladuste kasutamisest vaikeautentimise vastu?

Ei. Pärast selle konfigureerimist ei saa te enam vaikeühenduse peale muuta, kasutades lingitud võtmehoidla saladust. Looge eraldi ühendus ja kustutage vana, kui te seda enam ei vaja.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-customer-insights"></a>Kuidas tühistada juurdepääs Customer Insightsi võtmehoidlale?

Sõltuvalt sellest, kas [Key Vault juurdepääsu poliitika](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) või [Azure'i rollipõhine juurdepääsu juhtelement](/azure/key-vault/general/rbac-guide?tabs=azure-cli) on lubatud, peate eemaldama teenuse `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` subjekti õigused nimega `Dynamics 365 AI for Customer Insights`. Kõik võtmehoidlat kasutavad ühendused lõpetavad töötamise.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>Saladus, mida ühenduse puhul kasutatakse, eemaldati võtmehoidlast. Mida ma saan teha?

Teatis kuvatakse Customer Insightsis, kui võtmehoidla konfigureeritud saladus pole enam juurdepääsetav. Lubage [pehme kustutamine](/azure/key-vault/general/soft-delete-overview) võtmehoidlas saladuste taastamiseks kui need on kogemata eemaldatud.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>Ühendus ei tööta, kuid minu saladus on võtmehoidlas. Mis võib olla põhjus?

Teatis kuvatakse Customer Insightsis, kui see ei pääse võtmehoidlale juurde. Põhjus võib olla:

- Customer Insightsi hooldusdirektori õigused eemaldati. Need tuleb käsitsi taastada.

- Võtmehoidla tulemüür on lubatud. Tulemüür peab olema keelatud, et muuta võtmehoidla Customer Insightsi jaoks uuesti juurdepääsetavaks.
