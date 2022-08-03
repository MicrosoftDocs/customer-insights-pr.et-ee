---
title: Segmentide eksportimine LiveRamp (eelversioon)
description: Lugege, kuidas konfigureerida ühendust ja eksportida LiveRampi.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 55eacea3af83f46583a3a43797d625479f56586b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196711"
---
# <a name="export-segments-to-liverampreg-preview"></a>Segmentide eksportimine LiveRamp&reg; (eelversioon)

Aktiveerige oma andmed LiveRampis, et luua ühendus üle 500 platvormiga nii digitaalmeedias, sotsiaalmeedias kui ka televisioonis. Töötage LiveRampis oma andmetega, et sihistada, tõkestada ja isikupärastada reklaamikampaaniaid.

## <a name="prerequisites"></a>eeltingimused

- LiveRampi tellimus selle konnektori kasutamiseks. Tellimuse hankimiseks võtke otse [LiveRampiga ühendust](https://liveramp.com/contact/). [Lisateave LiveRampi kasutuselevõtu kohta](https://liveramp.com/our-platform/data-onboarding/).

## <a name="known-limitations"></a>Teadaolevad piirangud

- LiveRamp eksport kasutab SFTP eksporti. Tulemüüride taga olevaid SFTP sihtkohti praegu ei toetata.
- Kui kasutate autentimiseks SSH-võtit, veenduge, et [loote privaatvõtme](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) PEM- või SSH.COM vormingus. Kui kasutate Puttyt, teisendage oma privaatvõti eksportimise teel kui Open SSH. Toetatakse järgmisi privaatvõtme vorminguid.
  - RSA OpenSSL PEM- ja ssh.com-vormingus
  - DSA OpenSSL PEM- ja ssh.com-vormingus
  - ECDSA 256/384/521 OpenSSL PEM-vormingus
  - ED25519 ja RSA OpenSSH võtmevormingus
- Ekspordi käitusaeg sõltub teie süsteemi jõudlusest. Soovitame teie serveri minimaalseks konfiguratsiooniks kahte protsessori tuuma ja 1 GB mälu.
- Kuni 100 miljoni kliendiprofiiliga olemite eksportimiseks võib kuluda 90 minutit, kui kasutate soovitatud minimaalset kahe protsessori tuuma ja 1 GB mäluga konfiguratsiooni.
- Tegelik profiilide (või andmete) arv, mida saate LiveRampi eksportida, sõltub teie LiveRampi tellimusest.

## <a name="set-up-connection-to-liveramp"></a>Ühenduse loomine LiveRampiga

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Minge **Administraator** > **Ühendused**.

1. Valige **Lisa ühendus** ja valige **LiveRamp**.

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Vaikimisi on see ainult Administraatorid. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Valige, kas soovite autentida oma ühenduse SSH või kasutajanime /parooli kaudu, ja esitage vajalikud üksikasjad.

1. Valige suvand **Kinnita**, et testida LiveRampi ühendust.

1. Pärast edukat kontrollimist vaadake üle [andmete privaatsus ja vastavus](connections.md#data-privacy-and-compliance) ning valige **Nõustun**.

1. Ühenduse loomiseks valige **Salvesta**.

## <a name="configure-an-export"></a>Ekspordi konfigureerimine

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Minge **Andmed** > **Ekspordid**.

1. Valige **Lisa eksport**.

1. Valige **Ekspordiühendus** väljal ühendus LiveRamp jaotisest. Kui ühendusi pole saadaval, pöörduge administraatori poole.

1. Sisestage ekspordi nimi.

1. Valige väljal **Andmete** ühendamine suvand **E-post**, **Nimi ja aadress** või **Telefon**, mille soovite saata Teenusesse LiveRamp identiteedi lahendamiseks.

   :::image type="content" source="media/export-liveramp-segments.png" alt-text="LiveRampi konnektor atribuutide kaardistamiseks.":::

1. Vastendage oma *Kliendi* olemi vastavad atribuudid valitud võtmeidentifikaatori jaoks.

1. Valige **Lisa atribuut**, et kaardistada rohkem atribuute LiveRampile saatmiseks.

   > [!TIP]
   > Rohkemate põhiidentifikaatorite LiveRampi saatmisel on vastete määr tõenäoliselt suurem.

1. Valige segmendid, mille soovite eksportida.

1. Valige **Salvesta**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
