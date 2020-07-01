---
title: Datakategorisering i Power BI Desktop
description: Datakategorisering i Power BI Desktop
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: how-to
ms.date: 01/15/2020
ms.author: davidi
LocalizationGroup: Model your data
ms.openlocfilehash: 723869023824f7841eaaa895ab551b719a69c0e2
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/23/2020
ms.locfileid: "85236290"
---
# <a name="specify-data-categories-in-power-bi-desktop"></a>Angiv datakategorier i Power BI Desktop
I Power BI Desktop kan du angive *datakategorien* for en kolonne, så Power BI Desktop ved, hvordan dens værdier skal behandles i en visualisering.

Når Power BI Desktop importerer data, modtages andre oplysninger end selve dataene, f.eks. tabel- og kolonnenavne, og om dataene er en primær nøgle. Med disse oplysninger angiver Power BI Desktop nogle forudsætninger for, hvordan du får en god standardoplevelse, når du opretter en visualisering.
Når en kolonne f.eks. indeholder numeriske værdier, vil du muligvis samle dem på en måde, så Power BI Desktop placerer dem i området **Værdier** i ruden **Visualiseringer**. Eller for en kolonne med dato- og klokkeslætsværdier i et kurvediagram forudsætter Power BI Desktop, at du muligvis vil bruge den som en akse med tidshierarki.

Men der er nogle tilfælde, der er lidt mere udfordrende, f.eks. geografi. Se nærmere på følgende tabel fra et Excel-regneark:

![](media/desktop-data-categorization/datacategorizationtable.png)

Skal Power BI Desktop behandle koderne i kolonnen **GeoCode** som en forkortelse for et land eller en stat i USA?  Det er ikke klart, da en kode som denne kan betyde begge dele. AL kan f.eks. betyde Alabama eller Albanien, AR kan betyde Arkansas eller Argentina og CA kan betyde Californien eller Canada. Det gør en forskel, når vi vil oprette et GeoCode-felt på et kort. 

Skal Power BI Desktop vise et billede af verden med landene fremhævet? Eller skal der vises et billede af USA med de staterne fremhævet?  Du kan angive en datakategori for data som disse. Datakategorisering finjusterer oplysningerne, som kan bruges i Power BI Desktop, så du kan få de bedste visualiseringer.  

**Sådan angiver du en datakategori**

1. I visningen **Rapport** eller **Data** på listen **Felter** skal du vælge det felt, der skal sorteres efter en anden kategorisering.
2. På båndet skal du i området **Egenskaber** under fanen **Udformning** vælge rullepilen ud for **Datakategori**.  Dermed får du vist listen over de datakategorier, du kan vælge imellem til kolonnen. Nogle valgmuligheder kan være deaktiveret, hvis de ikke fungerer med den aktuelle datatype for kolonnen.  Hvis en kolonne f.eks. er en dato- eller klokkeslætsdatatype, kan du ikke vælge geografiske datakategorier i Power BI Desktop. 
3. Vælg den ønskede kategori.

   ![](media/desktop-data-categorization/desktop-data-categorization.png)

Du vil måske også være interesseret i at få mere at vide om [geografisk filtrering af Power BI-mobilapps](desktop-mobile-geofiltering.md).

