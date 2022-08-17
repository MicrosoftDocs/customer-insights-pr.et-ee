---
title: Kogemuste isikupärastamine teadaolevate ja tundmatute kasutajate andmetega
description: Lisage teave varem tundmatute kasutajate kohta, kui teate nende identiteeti.
ms.date: 07/07/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 8e3477750d82f965dc2d62174fb35554d9447b7b
ms.sourcegitcommit: 52eca81c36e93d553140f5a37cf6013aaa42623a
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 08/03/2022
ms.locfileid: "9224290"
---
# <a name="personalize-your-experiences-with-data-about-known-and-unknown-users"></a>Kogemuste isikupärastamine teadaolevate ja tundmatute kasutajate andmetega

Kliendiandmete haldamine ei ole uus väljakutse, kuid see muutub üha keerulisemaks, kuna kasutajad navigeerivad erinevates digitaalsetes kanalites, mida kaubamärgid pakuvad. Ühes kanalis tuntud (autenditud) kasutaja muutub teises kanalis tundmatuks (autentimata), kui ta pole sisse logitud. Probleem on sageli selles, et autentimata (tundmatutel) kasutajatel pole ühist ID-d. Seda saab kasutada tähendusrikaste profiiliatribuutide seostamiseks ja ühtsete kliendiprofiilide loomiseks. Customer Insights aitab seda probleemi lahendada, neelates andmeid teie lähtesüsteemide jälgimismeetoditest. Tundmatute ja teadaolevate profiilide konsolideerimine annab organisatsioonidele täieliku ülevaate ajakohastest profiilidest ning nende ajaloolistest kannetest, käitumisest ja demograafiast. See läheb isegi sammu kaugemale, pakkudes identiteedi eraldusvõimet, mis võimaldab teil ühendada klientide tegevust mitmes kanalis, sealhulgas teie veebisaidil, poes ostmisel, lojaalsusprogrammidel jne.

## <a name="sample-scenario"></a>Näidisstsenaarium

Mõelgem kohviketile, millel on lai kliendibaas, mis ostab kauplustest kohvi ja toitu ning tellib tooteid veebist. Sageli ei autendita veebikülastajaid toodete sirvimisel, muutes nad "tundmatuteks kasutajateks". Kohviketil on raske pakkuda isikupärastatud pakkumisi ja kogemusi, kui kasutajad pole teada. Teisest küljest saavad kliendid oma kontole sisse logida ja saada ettevõttele "tuntud kasutajateks", liitudes lojaalsussüsteemiga, mis omakorda võimaldab isikupärasemaid kogemusi. Customer Insights aitab kohviketil saada ülevaateid teadaolevate ja varem tundmatute kasutajate kohta.

Customer Insightsi abil saab ettevõte kombineerida kliendiprofiile tegevusandmetega autentimata (tundmatutest) seanssidest pärast seda, kui kasutaja on sisse loginud ja teada saanud. Kohvikett võib tuua andmeid teistest andmeallikatest, kasutades Customer Insightsi sisseehitatud konnektoreid, et ühendada erinevate kanalite klientide identiteedid.

## <a name="prerequisites"></a>eeltingimused

- Veebiandmeid kogutakse ja need sisaldavad kõigi külastajate "külastaja ID-sid".
- Veebiandmed sisaldavad sisselogitud külastajate jaoks "autenditud kasutaja ID-sid". Need ID-d on seotud lojaalsussüsteemiga.
- Suure väärtusega sündmuste andmed, nagu "Tootevaade" ja "Kassa", määratletakse ja lisatakse lähteandmetesse koos sündmuse ajatempli ja sündmuse ID-ga.

Järgmises tabelis on toodud lihtsustatud näide sellest, kuidas väärtuslikke veebisündmusi võidakse jäädvustada.

|Sündmuse ID|EventTimeStamp|Kasutajatunnus|Püsikliendi ID|Sündmuse nimi|
|--|--|--|--|--|
|1|07-23-2022 10:00:00|abc123|--|Toote vaade|
|2|07-23-2022 10:05:00|abc123|707|Püsikliendi sisselogimine|
|3|07-23-2022 10:10:00|abc123|707|Maksma siirdumine|
|4|07-23-2022 10:20:00|xyz789|--|Toote vaade|

## <a name="data-ingestion"></a>Andmete valmendamine

Klientide andmed võivad pärineda teie veebisaidilt sündmuse andmetena ja neid saab salvestada teie enda ettevõttesisestes või kolmanda osapoole andmeanalüüsi teenustes. Veebiandmed sisaldavad teadaolevaid ja tundmatuid kasutajaid, kui veebisaidil on autentimisvoog, mis integreerub autentimisteenusega. Näiteks e-kaubanduse süsteem, mis nõuab kasutajatelt ostutehingu lõpuleviimiseks oma täielike üksikasjade esitamist. Või püsikliendisüsteem, mis nõuab autentimist, et kinnitada preemiate allahindluste kehtiv saaja.

Meie ülaltoodud näites toodud sündmuse andmed sisaldavad teadaolevate ja tundmatute kasutajate erinevaid profiili ID-sid. Juhtudel 1 ja 4 ei ole kasutajad teada, samas kui sündmustel 2 ja 3 registreerub ID-ga abc123 kasutaja lojaalsusprogrammi.

:::image type="content" source="media/website-data-source.png" alt-text="Andmeallikad, sealhulgas Contoso veebisait.":::

Lisateavet andmete allaneelamiseks saadaolevate suvandite kohta leiate teemast [Andmeallikate ülevaade](data-sources.md).

## <a name="data-unification"></a>Andmete koondamine

Tundmatute identiteetide ja teadaolevate identiteetide lähendamine aitab võimaldada isikupärastamist kasutaja käitumise põhjal, olenemata nende profiili olekust (teada või teadmata). Kõigile kasutajatele mõeldud isikupärastatud sisu aitab klientidel kiiresti jõuda kõige asjakohasemate toodete või teenusteni, millest nad sel hetkel huvitatud on.

Kuna mõned meie andmete kasutajad on teada, saame kasutada Customer Insightsi, et kombineerida need andmed kasutaja profiiliga. Lisateavet kliendiprofiilide ühendamise kohta leiate teemast [Andmete ühendamise ülevaade](data-unification.md).

1. Valige veebiandmete olemist lähteväljad. Kasutage oma veebiandmetesse salvestatud profiiliandmeid ja valige väljad, mis esindavad demograafiliste andmetega ID-sid.

   :::image type="content" source="media/website-source-fields.png" alt-text="Veebi allikaväljad andmeallikas.":::

1. Lisage reegleid duplikaatkirjete ühendamiseks. Veebiandmete puhul valige kõige paremini täidetud andmed.

1. Vastendusreeglite ja -tingimuste konfigureerimine. Selles näites toodud veebiprofiilide sündmuse andmed vastendatakse ID-del muudest andmeallikatest pärit profiilidega, mis sisaldavad klienditeavet. Seadistage ID-de täpse vaste reeglid eraldi reeglitena kõigi teiste profiiliolemitega, millel on vastav primaarvõtme või ID vaste. Näites kasutatakse veebisündmuse profiili andmeid viimase vastava olemina, nii et muud profiiliandmed ühendatakse esimesena.
   1. Märkimata ruut **Kaasa kõik kirjed** loob teadaolevatele kasutajatele ühtsed profiilid ja sisaldab nende vastavaid tundmatuid kasutaja ID-sid. See on abiks stsenaariumide korral, kui olete huvitatud teadaolevate kasutajate varasemate käitumistegevuste vaatamisest, kui nad olid veel tundmatud.
   1. Ruut **Kaasa kõik kirjed** loob tundmatutele kasutajatele eraldi profiilikirjed. Tundmatud kasutajad saavad unikaalse kliendi ID. Tulevikus, kui veebisündmuste profiiliandmetes on seostatud teadaolev profiil, saab äsja tuntud kasutaja teekonda vaadata ja kasutada isikupärastamiseks ka varasemate tundmatute käitumisandmete põhjal.

:::image type="content" source="media/website-match-rule.png" alt-text="Vastendusreegel veebisaidi andmeallikas olemi jaoks.":::

## <a name="get-insights"></a>Hangi ülevaateid

Kui kliendiprofiilid luuakse tundmatutele ja teadaolevatele kasutajatele, saab väärtuslikke veebisündmuse andmeid kasutada [tegevustena](activities.md). Neid tegevusi saab kasutada rohkemate ülevaadete loomiseks. Näiteks kliendid, kes külastasid veebisaiti kuus kuud tagasi (kui nad olid veel tundmatud) või kliendid, kellel pole püsikliendi ID-d, ei sooritanud kunagi kassat.

:::image type="content" source="media/website-known-unknown.png" alt-text="Kuvatõmmis teadaolevate ja tundmatute klientidega kliendilehest.":::

[Rikastage](enrichment-hub.md) oma andmeid, koostage [mõõtühikuid](measures.md) ja looge [segmente](segments.md) edasiseks aktiveerimiseks.

Näiteks saate luua segmente teadaolevatest kasutajatest, kes vaatasid mõnda toodet, kuid ei lõpetanud kunagi kassat.

Lisateavet leiate teemast [Segmentide ülevaade](segments.md).

## <a name="activate-insights"></a>Ülevaadete aktiveerimine

Andmete eksportimiseks ja aluseks oleva statistika põhjal toimingute tegemiseks on mitu võimalust.

Lisateavet vaadake jaotisest [Ekspordi ülevaade](export-destinations.md).
