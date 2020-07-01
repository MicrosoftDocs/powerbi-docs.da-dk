---
title: Hent data fra filer med kommaseparerede værdier (.CSV)
description: Få mere at vide om, hvordan du kan hente data fra CSV-filer til Power BI
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: how-to
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Data from files
ms.openlocfilehash: 4827049ee8eff86b2ce71ee9befd3d01760c0840
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/23/2020
ms.locfileid: "85230470"
---
# <a name="get-data-from-comma-separated-value-csv-files"></a>Hent data fra filer med kommaseparerede værdier (.CSV)
![](media/service-comma-separated-value-files/csv_icon.png)

Filer med kommaseparerede værdier, også kaldet CSV-filer, er simple tekstfiler med rækker med data, hvor de enkelte værdier er adskilt af semikolon. Disse filtyper kan indeholde meget store mængder data i en relativt lille filstørrelse, hvilket gør dem til en ideel datakilde for Power BI. Du kan downloade et eksempel på en .CSV-fil [her](https://go.microsoft.com/fwlink/?LinkID=619356).

Hvis du har en .CSV-fil, skal du hente den ind på dit Power BI-websted som et datasæt, hvor du så kan begynde at udforske dine data, oprette nogle dashboards og dele din indsigt med andre.

>[!TIP]
>Mange organisationer udsender en .CSV-fil med opdaterede data hver dag. For at sikre at dit datasæt i Power BI forbliver synkroniseret med din opdaterede fil, skal du sørge for, at filen er gemt i OneDrive med det samme navn.

## <a name="where-your-file-is-saved-makes-a-difference"></a>Det gør en forskel, hvor du gemmer din fil
**Lokal** – Hvis du gemmer din .CSV-fil på et lokalt drev på din computer eller en anden placering i din organisation fra Power BI, kan du *importere* filen til Power BI. Filen bliver på den lokale harddisk, så det er ikke hele filen, der importeres til Power BI. I virkeligheden sker der det, at der oprettes et nyt datasæt i Power BI, og data fra .CSV-filen indlæses i datasættet.

**OneDrive – erhverv** – Hvis du har OneDrive for Business, og du logger på med den samme konto, du bruger til at logge på Power BI, er det den klart mest effektive metode til at holde din .CSV-fil synkroniseret med datasæt, rapporter og dashboards i Power BI. Da både Power BI og OneDrive findes i skyen, *opretter Power BI forbindelse* til din fil på OneDrive ca. hver time. Hvis der findes ændringer, opdateres datasættet, rapporter og dashboards automatisk i Power BI.

**OneDrive – personlig** – Hvis du gemmer dine filer på din egen OneDrive-konto, får du mange af de samme fordele som med OneDrive for Business. Den største forskel er, at når du første gang opretter forbindelse til din fil (med funktionen Hent data > Filer > OneDrive - personlig), skal du logge på OneDrive med din Microsoft-konto, hvilket normalt er anderledes, end hvad du bruger til at logge på Power BI. Når du logger på dit OneDrive med din Microsoft-konto, skal du sørge for at vælge indstillingen Forbliv logget på. På denne måde kan Power BI oprette forbindelse til din fil ca. hver time og sikre, at dit datasæt i Power BI er synkroniseret.

**SharePoint – teamwebsteder** – Lagring af dine Power BI Desktop-filer på SharePoint – Teamwebsteder er stort set det samme som at gemme på OneDrive for Business. Den største forskel er, hvordan du opretter forbindelse til filen fra Power BI. Du kan angive en URL-adresse, eller du kan oprette forbindelse til rodmappen.

## <a name="import-or-connect-to-a-csv-file"></a>Importér eller opret forbindelse til en .CSV-fil
>[!IMPORTANT]
>Den maksimale filstørrelse, du kan importere til Power BI, er 1 GB.

1. I Power BI skal du klikke på **Hent data** i navigationsruden.
   
   ![](media/service-comma-separated-value-files/csv_get_data_button.png)
2. I **Filer** skal du klikke på **Hent**.
   
   ![](media/service-comma-separated-value-files/csv_files_get.png)
3. Find din fil.
   
   ![](media/service-comma-separated-value-files/csv_find_your_file.png)

## <a name="next-steps"></a>Næste trin
**Udforsk dine data** – Når du har hentet data fra din fil til Power BI, er det tid til at udforske dem. Du skal blot højreklikke på det nye datasæt og derefter klikke på **Udforsk**.

**Planlæg opdatering** – Hvis din fil gemmes på et lokalt drev, kan du konfigurere planlagte opdateringer, så dine datasæt og rapporter i Power BI holdes opdateret. Du kan få mere at vide under [Opdatering af data i Power BI](refresh-data.md). Hvis din fil gemmes i OneDrive, synkroniserer Power BI automatisk med den ca. en gang i timen.

