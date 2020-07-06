---
title: Sideinddelte rapportdatakilder på Power BI-rapportserver
description: Få mere at vide om datakilder, som sideinddelte rapporter (.rdl) kan oprette forbindelse til på Power BI Report Server.
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 06/26/2020
ms.author: maggies
ms.openlocfilehash: 531c0ab2bb797e1ad5aaa4d974e51963f7c3e2ad
ms.sourcegitcommit: a453ba52aafa012896f665660df7df7bc117ade5
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/27/2020
ms.locfileid: "85485386"
---
# <a name="paginated-report-data-sources--in-power-bi-report-server"></a>Sideinddelte rapportdatakilder på Power BI-rapportserver
Sideinddelte Reporting Services-rapporter på Power BI Report Server understøtter de samme datakilder som dem, der understøttes i SQL Server Reporting Services. Se listen [Datakilder, der understøttes af Reporting Services](https://docs.microsoft.com/sql/reporting-services/report-data/data-sources-supported-by-reporting-services-ssrs).

## <a name="connect-to-oracle-data-sources-with-useinstalleduiculture"></a>Opret forbindelse til Oracle-datakilder med UseInstalledUICulture

Power BI-rapportserver bruger Oracle-dataprovideren til .NET (ODP.NET), som er NLS-agnostisk, for at oprette forbindelse til Oracle-datakilder.

Rapportserveren bruger som standard den første klients kultur for brugergrænsefladen til at indlæse ODP.NET.  Det resulterer i, at alle efterfølgende forbindelser til Oracle fra rapportserveren vil foregå i denne indledende kultur for brugergrænsefladen, indtil tjeneste genstartes.  Denne tilgang kan medføre problemer med gengivelse af en rapport pga. uoverensstemmelser i formateringen af kulturen for brugergrænsefladen.

Vi har introduceret en konfigurationsindstilling med navnet UseInstalledUICulture for at tilbyde en bedre oplevelse i Power BI-rapportserver. Når UseInstalledUICulture angives til sand, indlæser rapportserveren altid ODP.NET i serverens kultur for brugergrænsefladen i stedet for klientens kultur.
Denne indstilling er tilgængelig i Power BI-rapportserver fra udgivelsen af tjenesten i marts 2020.

Du aktiverer funktionen ved at redigere posten for ORACLE-udvidelsen i rsreportserver.config-filen, som beskrevet nedenfor.
```xml
<Extension Name="ORACLE" Type="Microsoft.ReportingServices.DataExtensions.OracleClientConnectionWrapper,Microsoft.ReportingServices.DataExtensions">
    <Configuration>
        <UseInstalledUICulture>true</UseInstalledUICulture>
    </Configuration>
</Extension>
```

## <a name="next-steps"></a>Næste trin
Nu, hvor du har oprettet forbindelse til datakilden, kan du [oprette en sideinddelt rapport](quickstart-create-paginated-report.md).  


Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)
