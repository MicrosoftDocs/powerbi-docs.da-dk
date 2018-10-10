---
title: Opret forbindelse til en PDF-fil i Power BI Desktop (prøveversion)
description: Opret nemt forbindelse til og brug data fra PDF-filer i Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 09/10/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: fe13e5776648342aa4f7e86dce657e6ffcca11b9
ms.sourcegitcommit: c51461690e8faa121a1325957ca79b7a3975e8b8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/12/2018
ms.locfileid: "44512700"
---
# <a name="connect-to-a-pdf-file-in-power-bi-desktop-preview"></a>Opret forbindelse til en PDF-fil i Power BI Desktop (prøveversion)
I Power BI Desktop kan du oprette forbindelse til en **PDF-fil** og bruge dataene fra filen på samme måde som enhver anden datakilde i Power BI Desktop.

![Opret forbindelse til data i PDF-filer](media/desktop-connect-pdf/connect-pdf_04.png)

I følgende afsnit beskrives det, hvordan du opretter forbindelse til en **PDF-fil**, vælger data og indfører disse data i **Power BI Desktop**.

## <a name="enable-the-pdf-connector"></a>Aktivér PDF-connector
PDF-connectoren indgår i prøveversionen til **Power BI Desktop** og skal aktiveres. Du aktiverer PDF-connectoren ved at vælge **Fil > Indstillinger > Indstillinger > Funktioner til eksempelvisning** og derefter markere afkrydsningsfeltet ud for **Hent data fra PDF-filer**. 

![Aktivér PDF-connector fra Indstillinger > Prøveversionsfunktioner](media/desktop-connect-pdf/connect-pdf_01.png)

Du skal genstarte **Power BI Desktop**, når du har markeret indstillingen.

Første gang du bruger **PDF (beta)**-connectoren, bliver du advaret om, at PDF-connectoren stadig er under udvikling og kan ændres senere. Vælg **Fortsæt** for at bruge connectoren.

Vi anbefaler, at du altid opgraderer til den nyeste version af **Power BI Desktop**, hvilket du kan gøre via et link i [Power BI Desktop](desktop-get-the-desktop.md). 

## <a name="connect-to-a-pdf-file"></a>Opret forbindelse til en PDF-fil
Hvis du vil oprette forbindelse til en **PDF-fil**, skal du vælge **Hent data** på båndet **Hjem** i Power BI Desktop. Vælg **Fil** blandt kategorierne til venstre, hvorefter du kan se **PDF (beta)**.

![Vælg PDF i Hent data](media/desktop-connect-pdf/connect-pdf_01.png)

Du bliver bedt om at angive placeringen af den PDF-fil, du vil bruge. Når du har angivet placeringen, og PDF-filen indlæses, vises der et vindue af typen **Navigator**, hvor de data, der er tilgængelige fra filen, vises. Her kan du vælge et eller flere elementer, der skal importeres og bruges i **Power BI Desktop**.

![Opret forbindelse til data i PDF-filer](media/desktop-connect-pdf/connect-pdf_04.png)

Hvis du markerer et afkrydsningsfelt ud for de registrerede elementer i PDF-filen, vises de i ruden til højre. Når du er klar til at importere, skal du vælge knappen **Indlæse** for at overføre dataene til **Power BI Desktop**.


## <a name="next-steps"></a>Næste trin
Du kan oprette forbindelse til mange forskellige typer data ved hjælp af Power BI Desktop. Du kan finde flere oplysninger om datakilder i følgende ressourcer:

* [Hvad er Power BI Desktop?](desktop-what-is-desktop.md)
* [Datakilder i Power BI Desktop](desktop-data-sources.md)
* [Udform og kombiner data med Power BI Desktop](desktop-shape-and-combine-data.md)
* [Opret forbindelse til Excel-projektmapper i Power BI Desktop](desktop-connect-excel.md)   
* [Angiv data direkte i Power BI Desktop](desktop-enter-data-directly-into-desktop.md)   
