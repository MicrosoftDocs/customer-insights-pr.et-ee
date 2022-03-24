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
ms.openlocfilehash: 418575f724090628da8bd01e2569a4cb9e646337
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376503"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>Tooge oma Azure võtmehoidla (eelversioon)

Kui linkite [Azure'i võtmehoidla](/azure/key-vault/general/basic-concepts) sihtrühma ülevaadete keskkonda, aitab see organisatsioonidel täita vastavuse nõudeid.
Sihtotstarbelise võtmehoidla abil saab etappe luua ja kasutada saladusi organisatsiooni vastavuse piirides. Sihtrühma ülevaated saavad kasutada Azure'i võtmehoidla saladusi [ühenduste loomiseks](connections.md) muude tootjate süsteemidega.

## <a name="link-the-key-vault-to-the-audience-insights-environment"></a>Linkige võtmehoidla sihtrühma ülevaadete keskkonda

### <a name="prerequisites"></a>eeltingimused

Sihtrühma ülevaadete võtmehoidla konfigureerimiseks peavad olema täidetud järgmised eeltingimused:

- Teil peab olema aktiivne Azure tellimus.

- Teil on [Administraatori](permissions.md#admin) roll publiku ülevaadetes. Lisateave [kasutajaõiguste kohta sihtrühma ülevaadetes](permissions.md#assign-roles-and-permissions).

- Teil on võtmehoidlas või ressursirühmas, kuhu võtmehoidla kuulub, [Kaastöötaja](/azure/role-based-access-control/built-in-roles#contributor) ja [Kasutaja juurdepääsu administraatori](/azure/role-based-access-control/built-in-roles#user-access-administrator) rollid. Lisateabe jaoks minge [Azure'i rollimäärangute lisamine või eemaldamine Azure portaalist](/azure/role-based-access-control/role-assignments-portal). Kui teil pole võtmehoidlas kasutajajuurdepääsu administraatori rolli, peate Azure'i teenuse subjekti jaoks eraldi seadistama rollipõhised Dynamics 365 Customer Insights juurdepääsu õigused. Järgige samme, et [kasutada Azure'i teenuse printsipaali](connect-service-principal.md) lingitava võtmehoidla jaoks.

- Võtmehoidlal peab olema võtmehoidla tulemüür **keelatud**.

- Azure'i võtmehoidla asub samas [Azure'i kohas](https://azure.microsoft.com/global-infrastructure/geographies/#overview), kus on sihtrühma ülevaadete keskkond. Keskkonna piirkond sihtrühma ülevaadetes on toodud jaotises **Administraator** > **Süsteem** > **Teave** > **Piirkond**.

### <a name="link-a-key-vault-to-the-environment"></a>Võtmehoidla linkimine keskkonnaga

1. Minge **Admin** > **Süsteem** ja siis valige **Turvalisus** vahekaart.
1. Tehke paanil **Võtmehoidla** valik **Seadistus**.
1. Valige **Kordustellimus**.
1. Valige võtmehoidla ripploendist **Võtmeloend**. Kui kuvatakse liiga palju võtmehoidlaid, valige otsingutulemite piiramiseks ressursirühm.
1. Nõustuge **Andmete privaatsuse ja privaatsusavaldusega**.
1. Valige **Salvesta**.

:::image type="content" source="media/set-up-azure-key-vault.png" alt-text="Sammud lingitud võtmehoidla häälestamiseks sihtrühma ülevaadetes.":::

Paanil **Võtmehoidla** on nüüd lingitud võtmehoidla nimi, ressursirühm ja kordustellimus. See on valmis ühenduse seadistamiseks.
Lisateabe saamiseks selle kohta, millised õigused antakse võtmehoidlas sihtrühma ülevaadetele, minge [Võtmehoidlas antud õigused sihtrühma ülevaadetele](#permissions-granted-on-the-key-vault-to-audience-insights) selles artiklis.

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

## <a name="permissions-granted-on-the-key-vault-to-audience-insights"></a>Võtmehoidlas sihtrühma ülevaadetele antud õigused

Kui [Võtmehoidla juurdepääsu poliitika](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) või [Azure'i rollipõhine juurdepääsu juhtelement](/azure/key-vault/general/rbac-guide?tabs=azure-cli) on lubatud, antakse sihtrühma ülevaadetele lingitud võtmehoidlas järgmised õigused.

### <a name="key-vault-access-policy"></a>Key Vault'i juurdepääsu poliitika

| Tüüp        | Õigused          |
| ----------- | -------------------- |
| Klahv         | [Too võtmed](/rest/api/keyvault/get-keys), [Too võti](/rest/api/keyvault/get-key)                                 |
| Saladus      | [Hankige saladused](/rest/api/keyvault/get-secrets), [Hankige saladus](/rest/api/keyvault/get-secret)                     |
| Sert | [Hankige sertifikaadid](/rest/api/keyvault/get-certificates), [Hankige sertifikaat](/rest/api/keyvault/get-certificate) |

Eelnevad väärtused on miinimum, mida soovite käivitamise ajal loetleda ja lugeda.

### <a name="azure-role-based-access-control"></a>Azure'i rollipõhine juurdepääsu juhtelement

Key Vault'i luger ja Key Vault'i saladuste kasutaja rollid lisatakse sihtrühma ülevaadetele. Nende rollide kohta lisateabe saamiseks minge [Azure'i sisseehitatud rollid võtmehoidla andmete analüüsitoimingute jaoks](/azure/key-vault/general/rbac-guide?tabs=azure-cli).

## <a name="recommendations"></a>Soovitused

- Kasutage eraldi või eraldatud võtmehoidlat, mis sisaldab ainult sihtrühma ülevaadete jaoks vajalikke saladusi. Lugege lisateavet selle kohta, miks [eraldi võtmehoidlad on soovitatavad](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults).

- Järgige [parimaid tavasid, et kasutada võtmehoidlat](/azure/key-vault/general/best-practices#turn-on-logging) juurdepääsu-, varundus-, auditeerimis- ja proovihoidla suvandite auditeerimiseks.

## <a name="frequently-asked-questions"></a>Korduma kippuvad küsimused

### <a name="can-audience-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>Kas sihtrühma ülevaated saavad kirjutada või üle kirjutada saladusi võtmehoidlasse?

Ei. Ainult lugemise ja nimekirja õigused, mis on välja toodud [antud õigused](#permissions-granted-on-the-key-vault-to-audience-insights) jaotises selles artiklis on lubatud sihtrühma ülevaadetele. Süsteem ei saa võtmehoidlasse saladusi lisada, kustutada ega üle kirjutada. Samuti on põhjus, miks te ei saa sisestada mandaati, kui ühendus kasutab Key Vault'i.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>Kas ma saan muuta ühenduse Key Vault'i saladuste kasutamisest vaikeautentimise vastu?

Ei. Pärast selle konfigureerimist ei saa te enam vaikeühenduse peale muuta, kasutades lingitud võtmehoidla saladust. Looge eraldi ühendus ja kustutage vana, kui te seda enam ei vaja.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-audience-insights"></a>Kuidas tühistada sihtrühma ülevaadete juurdepääs võtmehoidlasse?

Sõltuvalt sellest, kas [Key Vault juurdepääsu poliitika](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) või [Azure'i rollipõhine juurdepääsu juhtelement](/azure/key-vault/general/rbac-guide?tabs=azure-cli) on lubatud, peate eemaldama teenuse `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` subjekti õigused nimega `Dynamics 365 AI for Customer Insights`. Kõik võtmehoidlat kasutavad ühendused lõpetavad töötamise.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>Saladus, mida ühenduse puhul kasutatakse, eemaldati võtmehoidlast. Mida ma saan teha?

Sihtrühma ülevaadetes kuvatakse teade, kui võtmehoidla konfigureeritud saladus ei ole enam juurdepääsetav. Lubage [pehme kustutamine](/azure/key-vault/general/soft-delete-overview) võtmehoidlas saladuste taastamiseks kui need on kogemata eemaldatud.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>Ühendus ei tööta, kuid minu saladus on võtmehoidlas. Mis võib olla põhjus?

Teatis kuvatakse sihtrühma ülevaadetes, kui see ei pääse võtmehoidlasse. Põhjus võib olla:

- Sihtrühma ülevaadete teenuse subjekti õigused on eemaldatud. Need tuleb käsitsi taastada.

- Võtmehoidla tulemüür on lubatud. Tulemüür tuleb keelata, et muuta võtmehoidla uuesti sihtrühma ülevaadetele kättesaadavaks.
