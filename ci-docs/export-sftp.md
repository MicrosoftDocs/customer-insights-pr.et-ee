---
title: Andmete eksportimine SFTP hostidesse (eelvaade) (sisaldab videot)
description: Lugege, kuidas konfigureerida ühendust ja eksportida SFTP asukohta.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b12d25ecbd2e5fb31d7d5a6bb775dc3e7c1bf007
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207224"
---
# <a name="export-data-to-sftp-hosts-preview"></a>Andmete eksportimine SFTP hostidesse (eelvaade)

Kliendiandmete kasutamiseks muude tootjate rakendustes eksportige need turvalise failiedastuse protokolli (SFTP) asukohta.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO94X]

## <a name="prerequisites"></a>eeltingimused

- SFTP-hosti saadavus ja vastav identimisteave.

## <a name="known-limitations"></a>Teadaolevad piirangud

- Tulemüüride taga olevaid SFTP sihtkohti praegu ei toetata.
- Ekspordi käitusaeg sõltub teie süsteemi jõudlusest. Soovitame teie serveri minimaalseks konfiguratsiooniks kahte protsessori tuuma ja 1 GB mälu.
- Kuni 100 miljonit kliendiprofiili, mis võib võtta 90 minutit, kui kasutate kahe CPU südamiku ja 1 Gb mälu soovitatavat minimaalset konfiguratsiooni.
- Kui kasutate autentimiseks SSH-võtit, veenduge, et [loote privaatvõtme](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) PEM- või SSH.COM vormingus. Kui kasutate Puttyt, teisendage oma privaatvõti eksportimise teel kui Open SSH. Toetatakse järgmisi privaatvõtme vorminguid.
  - RSA OpenSSL PEM- ja ssh.com-vormingus
  - DSA OpenSSL PEM- ja ssh.com-vormingus
  - ECDSA 256/384/521 OpenSSL PEM-vormingus
  - ED25519 ja RSA OpenSSH võtmevormingus

## <a name="set-up-connection-to-sftp"></a>SFTP ühenduse loomine

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Minge **Administraator** > **Ühendused**.

1. Valige **Lisa ühendus** ja valige **SFTP**.

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Vaikimisi on see ainult Administraatorid. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Valige, kas soovite autentida oma ühenduse SSH või kasutajanime /parooli kaudu, ja esitage vajalikud üksikasjad. Kui kasutate autentimiseks SSH-võtit, veenduge, et [loote privaatvõtme](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) PEM- või SSH.COM vormingus. Kui kasutate Puttyt, teisendage oma privaatvõti eksportimise teel kui Open SSH. Toetatakse järgmisi privaatvõtme vorminguid.
   - RSA OpenSSL PEM- ja ssh.com-vormingus
   - DSA OpenSSL PEM- ja ssh.com-vormingus
   - ECDSA 256/384/521 OpenSSL PEM-vormingus
   - ED25519 ja RSA OpenSSH võtmevormingus

1. Valige ühenduse testimiseks **Kinnita**.

1. [Vaadake üle andmete privaatsus ja vastavus](connections.md#data-privacy-and-compliance) ning valige **Nõustun**.

1. Ühenduse loomiseks valige **Salvesta**.

## <a name="configure-an-export"></a>Ekspordi konfigureerimine

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Minge **Andmed** > **Ekspordid**.

1. Valige **Lisa eksport**.

1. Valige **Ekspordiühendus** väljal ühendus SFTP jaotisest. Kui ühendusi pole saadaval, pöörduge administraatori poole.

1. Sisestage ekspordi nimi.

1. Valige, kas soovite eksportida oma andmed **Gzipped** või **Unzipped** ja **väljaeraldaja** eksporditavate failide jaoks.

1. Valige olemid (nt segmendid), mida soovite eksportida.

   > [!NOTE]
   > Iga valitud olem jagatakse eksportimisel maksimaalselt viieks väljundfailiks.

1. Valige **Salvesta**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!TIP]
> Suurt hulka andmeid sisaldavate olemite eksportimine võib viia iga ekspordi puhul mitme CSV-failini samas kaustas. Ekspordi tükeldamine toimub jõudlusega seotud põhjustel, et minimeerida ekspordi lõpuleviimiseks kuluvat aega.

[!INCLUDE [footer-include](includes/footer-banner.md)]
