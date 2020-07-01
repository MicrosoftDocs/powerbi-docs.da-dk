---
title: Azure SQL Database med DirectQuery
description: Azure SQL Database med DirectQuery
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: how-to
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.custom: ''
ms.date: 04/28/2020
LocalizationGroup: Data from databases
ms.openlocfilehash: ffdb18927d5b92ecd10eb4b9e3a3b8fcd921dea2
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/23/2020
ms.locfileid: "85230577"
---
# <a name="azure-sql-database-with-directquery"></a>Azure SQL Database med DirectQuery

Få mere at vide om, hvordan du kan oprette direkte forbindelse til Azure SQL Database og oprette rapporter, der bruger livedata. Du kan beholde dine data ved kilden i stedet for i Power IB.

Med DirectQuery sendes forespørgsler tilbage til din Azure SQL Database, mens du udforsker dataene i rapportvisning. Denne oplevelse foreslås til brugere, der kender de databaser og enheder, de opretter forbindelse til.

> [!Important]
> I denne beskrivelse antages det, at Azure SQL-database ikke er i en VNET, eller at der er aktiveret et privat slutpunkt for linket.

**Bemærk!**

* Angiv det fuldt gyldige servernavn, når du opretter forbindelse (se yderligere oplysninger nedenfor).
* Kontrollér, at firewallreglerne for databasen er konfigureret til "[Tillad adgang til Azure-tjenester](https://docs.microsoft.com/azure/sql-database/sql-database-networkaccess-overview#allow-azure-services)".
* Hver handling, f.eks. markering af en kolonne eller tilføjelse af et filter, vil sende en forespørgsel tilbage til databasen.
* Felterne opdateres ca. hver time (opdateringen skal ikke planlægges). Du kan tilpasse, hvor ofte der skal opdateres, i Avancerede indstillinger, når du opretter forbindelse.
* Spørgsmål og svar er ikke tilgængelig for DirectQuery-datasæt.
* Skemaændringer hentes ikke automatisk.

Disse begrænsninger og noter kan ændres, efterhånden som vi fortsat forbedrer oplevelserne. Trinnene til at oprette forbindelse er beskrevet nedenfor.

> [!Important]
> Vi har forbedret vores netværksmuligheder til Azure SQL Database.  For at få den bedste oplevelse og oprette forbindelse til din Azure SQL Database-datakilde kan du bruge Power BI Desktop.  Når du har bygget din model og rapport, kan du udgive den på Power BI-tjenesten.  Den direkte forbindelse til Azure SQL Database i Power BI-tjenesten frarådes nu.

## <a name="power-bi-desktop-and-directquery"></a>Power BI Desktop og DirectQuery

Hvis du vil oprette forbindelse til Azure SQL Database med DirectQuery, skal du bruge Power BI Desktop. Denne metode sikrer yderligere fleksibilitet og funktioner. De rapporter, der oprettes ved hjælp af Power BI Desktop, kan derefter publiceres til Power BI-tjenesten. Du kan få mere at vide om at oprette forbindelse til [Azure SQL Database med DirectQuery](desktop-use-directquery.md) i Power BI Desktop.

## <a name="find-parameter-values"></a>Find parameterværdier

Du kan finde dit fulde gyldige servernavn og databasenavn på Azure Portal.

![Ny opdatering til Azure Portal](media/service-azure-sql-database-with-direct-connect/azureportnew_update.png)

![Opdatering til Azure Portal](media/service-azure-sql-database-with-direct-connect/azureportal_update.png)

[!INCLUDE [direct-query-sso](../includes/direct-query-sso.md)]

## <a name="next-steps"></a>Næste trin

* [Brug DirectQuery i Power BI Desktop](desktop-use-directquery.md)  
* [Hvad er Power BI?](../fundamentals/power-bi-overview.md)  
* [Hent data til Power BI](service-get-data.md)  

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)
