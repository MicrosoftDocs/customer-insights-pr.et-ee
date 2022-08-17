---
title: Ühenduste (eelversioon) ülevaade
description: Ühendused muude teenustega Customer Insights kaudu.
ms.date: 08/04/2022
ms.reviewer: nikeller
ms.subservice: audience-insights
ms.topic: overview
author: m-hartmann
ms.author: mhart
manager: shellyha
searchScope:
- ci-connections
- customerInsights
ms.openlocfilehash: 8580dc7d90c75f66f73efc15f8e38f5e10fbb8a7
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245506"
---
# <a name="connections-preview-overview"></a>Ühenduste (eelversioon) ülevaade

Ühendused on võti andmete jagamise lubamiseks Customer Insights kaudu. Iga ühendus loob andmete jagamise konkreetse teenusega. Kasutage ühendusi kolmanda osapoole rikastumiste konfigureerimiseks [ja](enrichment-hub.md) [ekspordi konfigureerimiseks](export-destinations.md). Sama ühendust saab kasutada mitmeid kordi. Näiteks üks ühendus Dynamics 365 Marketing'iga töötab mitme ekspordi jaoks ja ühe Leadspace ühenduse abil saab kasutada mitut rikastamist.

## <a name="export-connections"></a>Ekspordi ühendused

Ainult administraatorid saavad konfigureerida uusi ühendusi, kuid nad saavad [anda kaasautoritele](#allow-contributors-to-use-a-connection-for-exports) juurdepääsu olemasolevate ühenduste kasutamiseks. Administraatorid määravad, kuhu andmed võivad minna, kaastöötajad määratlevad koormuse ja sageduse, mis nende vajadustele vastab.

## <a name="enrichment-connections"></a>Rikastavad ühendused

Uusi ühendusi saavad konfigureerida ainult administraatorid, kuid loodud ühendused on alati saadaval nii administraatoritele kui ka kaasautoritele. Administraatorid haldavad volitusi ja nõustuvad andmete edastamisega. Ühendusi saavad seejärel kasutada rikastamiseks nii administraatorid kui ka kaastöötajad.

## <a name="add-a-new-connection"></a>Uue ühenduse lisamine

### <a name="prerequisites"></a>eeltingimused

- [Administraatori õigused](permissions.md)
- Muud Microsofti teenused (kui neid on) asuvad samas organisatsioonis

1. Minge **Administraator** > **Ühendused**.

1. Valige **Lisa ühendus** ja valige loodava ühenduse tüüp. Või minge vahekaardile **Avastamine** ja valige **Häälesta** ühenduse paanil.

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Sisestage nõutavad üksikasjad. Täpsed väljad sõltuvad sellest, millise teenusega te ühenduse loote. Konkreetse ühendusetüübi kohta leiate üksikasju artiklist sihtteenuse kohta.

1. Kui [kasutate oma võtmehoidlat](use-azure-key-vault.md) saladuste salvestamiseks, aktiveerige **Kasutage võtmehoidlat** ja valige loendist saladus.

1. Vaadake üle andmete privaatsus ja vastavus ning valige **Nõustun**.

1. Ühenduse loomiseks valige **Salvesta**.

### <a name="data-privacy-and-compliance"></a>Andmete privaatsus ja nõuetele vastavus

Kui lubate Dynamics 365 Customer Insights edastada andmeid kolmandatele osapooltele või muudele Microsofti toodetele, lubate edastada andmeid väljaspool nõuetele vastavuse piire, sh potentsiaalselt tundlike andmete, näiteks isikuandmete puhul Dynamics 365 Customer Insights. Microsoft edastab selliseid andmeid teie korraldusel, kuid teie vastutate selle eest, et kolmas osapool täidaks kõiki teie privaatsus- või turbekohustusi. Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).

Teie Dynamics 365 Customer Insights administraator saab funktsiooni kasutamise lõpetamiseks ühenduse igal ajal eemaldada.

## <a name="allow-contributors-to-use-a-connection-for-exports"></a>Luba kaastöötajatel kasutada ühendust ekspordi jaoks

Ekspordiühenduse seadistamisel või redigeerimisel valige, millistel kasutajatel on lubatud seda konkreetset ühendust ekspordi [määratlemiseks](export-destinations.md) kasutada. Vaikimisi on ühendus saadaval administraatori rolliga kasutajatele. **Muutke sätet Valige, kes saab seda ühendust** kasutada, et lubada kaasautorirolliga kasutajatel seda ühendust kasutada.

- Kaastöötajad ei saa ühendust vaadata ega redigeerida. Nad näevad ekspordi loomisel ainult kuvatavat nime ja selle tüüpi.
- Ühenduse jagamisel lubate kaastöötajatel ühendust kasutada. Kaastöötajad näevad ekspordi seadistamisel ühisühendusi. Nad saavad hallata igat eksporti, mis kasutab seda kindlat ühendust.
- Saate seda sätet muuta, hoides ekspordi alles, mille kaastöötajad on juba määratlenud.

## <a name="manage-existing-connections"></a>Olemasolevate ühenduste haldamine

1. Minge **Administraator** > **Ühendused**.

1. **Valige vahekaart Rikastamine** või **Eksport**, et vaadata rikastus- või ekspordiühenduste loendit, ühenduse tüüpi, loomise aega ja juurdepääsu omavat isikut. Ühenduste loendit saate sortida mis tahes veeru järgi.

1. Valige ühendus saadaolevate toimingute vaatamiseks.

   - **Redigeerige** ühendust.
   - [**Ühenduse eemaldamine**](#remove-a-connection).

### <a name="remove-a-connection"></a>Eemaldage ühendus

Kui eemaldatavat ühendust kasutatakse rikastumiseks või eksportimiseks, eemaldage need kõigepealt või eemaldage need. Eemaldamisdialoog juhatab teid asjakohaste rikastuste või ekspordite juurde.

> [!TIP]
> Deaktiveeritud rikastumised ja eraldatud eksport muutuvad passiivseks. Aktiveerite need uuesti, lisades neile teise ühenduse [Rikastamised](enrichment-hub.md) või [Ekspordid](export-destinations.md) lehel.

1. Minge **Administraator** > **Ühendused**.

1. Valige **vahekaart Rikastamine** või **Eksport**.

1. Valige ühendus, mille soovite eemaldada.

1. Valige rippmenüüst **Eemalda**. Ilmub kinnituse dialoog.

   1. Kui seda ühendust kasutatakse rikastamiseks või eksportimiseks, valige nupp, et näha, mis seda ühendust kasutab.
      - **Ekspordid:** valige kas **eemaldage** eksport või **eemaldage ühendus**. Ühenduse eemaldamine säilitab ekspordikonfiguratsiooni, kuid seda ei käivitata enne, kui sellele on lisatud uus ühendus.
      - **Rikastamine:** valige kas **rikastumise kustutamine** või **inaktiveerimine**.
   1. Kui ühendusel pole rohkem sõltuvusi, minge tagasi **Administraator** > **Ühendused** ja proovige ühendus uuesti eemaldada.

1. Valige käsk **Eemalda**, et kinnitada kustutamine.

## <a name="set-up-connections-with-secrets-managed-by-your-own-key-vault"></a>Saate seadistada ühendusi saladustega, mida haldab teie oma võtmehoidla.

Mõne ühenduse puhul on vaja saladusi, nagu API-võtmed või paroolid. Mõned ühendused toetavad saladusi, mis on talletatud teie enda võtmehoidlasse. Lugege lisateavet toetatud ühenduste ja selle kohta, kuidas seadistada [oma võtmehoidlas Customer Insightsi](use-azure-key-vault.md) jaoks.

[!INCLUDE [footer-include](includes/footer-banner.md)]
