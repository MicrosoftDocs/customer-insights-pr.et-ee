---
title: Tooge oma Azure võtmehoidla (eelversioon)
description: Siit saate teada, kuidas konfigureerida Customer Insightsi kasutama saladuste haldamiseks oma Azure’i võtmehoidlat.
ms.date: 08/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 229fb5698a02d1d73c30442f61c7b1b5fce918bf
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246150"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>Tooge oma Azure võtmehoidla (eelversioon)

Spetsiaalse [Azure’i võtmehoidla](/azure/key-vault/general/basic-concepts) linkimine Customer Insightsi keskkonnaga aitab organisatsioonidel täita vastavusnõudeid.

## <a name="link-the-key-vault-to-the-customer-insights-environment"></a>Võtmehoidla linkimine Customer Insightsi keskkonnaga

Seadistage spetsiaalne võtmehoidla, et lavastada ja kasutada saladusi organisatsiooni vastavuspiiril.

### <a name="prerequisites"></a>eeltingimused

- Töötav Azure -i tellimus.

- [Customer Insightsis määratud](permissions.md#admin) administraatoriroll [...](permissions.md#add-users).

- [Kaasautori](/azure/role-based-access-control/built-in-roles#contributor) ja [kasutaja juurdepääsuadministraatori](/azure/role-based-access-control/built-in-roles#user-access-administrator) rollid võtmehoidlas või ressursirühmas, kuhu võtmehoidla kuulub. Lisateabe jaoks minge [Azure'i rollimäärangute lisamine või eemaldamine Azure portaalist](/azure/role-based-access-control/role-assignments-portal). Kui teil pole võtmehoidlas kasutaja juurdepääsuadministraatori rolli, seadistage Azure’i teenuse printsipaali Dynamics 365 Customer Insights rollipõhised juurdepääsu juhtimise õigused eraldi. Järgige samme, et [kasutada Azure'i teenuse printsipaali](connect-service-principal.md) lingitava võtmehoidla jaoks.

- Võtmehoidlal peab olema Key Vault tulemüür **keelatud**.

- Võtmehoidla asub samas [Azure’i asukohas](https://azure.microsoft.com/global-infrastructure/geographies/#overview) kui Customer Insightsi keskkond. Avage Customer Insightsis **keskkonnapiirkonna vaatamiseks haldussüsteem** > **ja** **vahekaart Teave**.

### <a name="recommendations"></a>Soovitused

- [Kasutage eraldi või spetsiaalset võtmehoidlat](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults), mis sisaldab ainult Customer Insightsi jaoks vajalikke saladusi.

- Järgige [parimaid tavasid, et kasutada võtmehoidlat](/azure/key-vault/general/best-practices#turn-on-logging) juurdepääsu-, varundus-, auditeerimis- ja proovihoidla suvandite auditeerimiseks.

### <a name="link-a-key-vault-to-the-environment"></a>Võtmehoidla linkimine keskkonnaga

1. Avage **jaotis Administraatori** > **turve** ja seejärel valige **vahekaart Võtmehoidla**.
1. Tehke paanil **Võtmehoidla** valik **Seadistus**.
1. Valige **Kordustellimus**.
1. Valige võtmehoidla ripploendist **Võtmeloend**. Kui saadaval on liiga palju võtmehoidlaid, valige otsingutulemite piiramiseks ressursirühm.
1. Vaadake üle [Andmete privaatsus ja vastavaus](connections.md#data-privacy-and-compliance) ja valige **Nõustun**.
1. Valige **Salvesta**.

**Paanil Võtmehoidla** kuvatakse lingitud võtmehoidla nimi, tellimus ja ressursirühm. See on valmis ühenduse seadistamiseks.
Lisateavet selle kohta, millised võtmehoidla õigused Customer Insightsile antakse, leiate teemast [Võtmehoidlas](#permissions-granted-on-the-key-vault) antud õigused.

## <a name="use-the-key-vault-in-the-connection-setup"></a>Kasutage ühenduse seadistamisel võtmehoidlat

Toetatud kolmandate osapoolte [süsteemidega](connections.md)[ühenduste loomisel](#supported-connection-types) kasutage ühenduste konfigureerimiseks lingitud võtmehoidla saladusi.

1. Minge **Administraator** > **Ühendused**.
1. Valige **Lisa ühendus**.
1. Toetatud ühendusetüüpide puhul on saadaval funktsiooni **Kasuta võtmehoidlat** ümberlülitus, kui linkite võtmehoidla.
1. Selle asemel, et saladust käsitsi sisestada, valige salajane nimi, mis osutab võtmehoidla salajasele väärtusele.

   :::image type="content" source="media/use-key-vault-secret.png" alt-text="Ühenduspaan SFTP-ühenduse abil, mis kasutab Key Vault saladust.":::

1. Ühenduse loomiseks valige **Salvesta**.

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

## <a name="permissions-granted-on-the-key-vault"></a>Võtmehoidlale antud õigused

Järgmised õigused antakse Customer Insightsile lingitud võtmehoidlas, kui kas [võtmehoidla juurdepääsupoliitika](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) või [Azure’i rollipõhine juurdepääsukontroll](/azure/key-vault/general/rbac-guide?tabs=azure-cli) on lubatud.

### <a name="key-vault-access-policy"></a>Key Vault'i juurdepääsu poliitika

| Tüüp        | Õigused          |
| ----------- | -------------------- |
| Klahv         | [Too võtmed](/rest/api/keyvault/keys/get-keys/get-keys), [Too võti](/rest/api/keyvault/keys/get-key/get-key)                                 |
| Saladus      | [Hankige saladused](/rest/api/keyvault/secrets/get-secrets/get-secrets), [Hankige saladus](/rest/api/keyvault/secrets/get-secret/get-secret)                     |
| Sert | [Hankige sertifikaadid](/rest/api/keyvault/certificates/get-certificates/get-certificates), [Hankige sertifikaat](/rest/api/keyvault/certificates/get-certificate/get-certificate) |

Eelnevad väärtused on miinimum, mida soovite käivitamise ajal loetleda ja lugeda.

### <a name="azure-role-based-access-control"></a>Azure'i rollipõhine juurdepääsu juhtelement

[Key Vault Reader ja Key Vault Secrets Kasutaja rollid](/azure/key-vault/general/rbac-guide?tabs=azure-cli) lisatakse Customer Insightsi jaoks.

## <a name="frequently-asked-questions"></a>Korduma kippuvad küsimused

### <a name="can-customer-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>Kas Customer Insights saab võtmehoidlasse saladusi kirjutada või saladusi üle kirjutada?

Ei. Customer Insightsile antakse ainult antud õigustes kirjeldatud lugemis [- ja loendiõigused](#permissions-granted-on-the-key-vault). Süsteem ei saa võtmehoidlasse saladusi lisada, kustutada ega üle kirjutada. Samuti on põhjus, miks te ei saa sisestada mandaati, kui ühendus kasutab Key Vault'i.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>Kas ma saan muuta ühenduse Key Vault'i saladuste kasutamisest vaikeautentimise vastu?

Ei. Pärast selle konfigureerimist ei saa te enam vaikeühenduse peale muuta, kasutades lingitud võtmehoidla saladust. Looge eraldi ühendus ja kustutage vana, kui te seda enam ei vaja.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-customer-insights"></a>Kuidas tühistada juurdepääsu Customer Insightsi võtmehoidlale?

[Kui võtmehoidla juurdepääsupoliitika](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) või [Azure’i rollipõhine juurdepääsukontroll](/azure/key-vault/general/rbac-guide?tabs=azure-cli) on lubatud, eemaldage teenuse printsipaali `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` õigused nimega `Dynamics 365 AI for Customer Insights`. Kõik võtmehoidlat kasutavad ühendused lõpetavad töötamise.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>Saladus, mida ühenduse puhul kasutatakse, eemaldati võtmehoidlast. Mida ma saan teha?

Customer Insightsis kuvatakse teatis, kui võtmehoidla konfigureeritud saladus pole enam juurdepääsetav. Lubage [pehme kustutamine](/azure/key-vault/general/soft-delete-overview) võtmehoidlas saladuste taastamiseks kui need on kogemata eemaldatud.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>Ühendus ei tööta, kuid minu saladus on võtmehoidlas. Mis võib olla põhjus?

Customer Insightsis kuvatakse teatis, kui see ei pääse võtmehoidlale juurde. Põhjus võib olla:

- Customer Insightsi teenindaja õigused eemaldati. Need tuleb käsitsi taastada.

- Võtmehoidla tulemüür on lubatud. Tulemüür peab olema keelatud, et võtmehoidla oleks Customer Insightsi jaoks uuesti juurdepääsetav.
