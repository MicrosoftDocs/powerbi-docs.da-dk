---
title: Skift forbindelsesstrenge til datakilden med PowerShell
description: Skift forbindelsesstrenge til datakilden ved hjælp af API'er i PowerShell – Power BI-rapportserver.
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: how-to
ms.date: 01/21/2020
ms.author: maggies
ms.openlocfilehash: bb769937e99cd3e936d7f5f3967e8f17b939242c
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/23/2020
ms.locfileid: "85236064"
---
# <a name="change-data-source-connection-strings-in-power-bi-reports-with-powershell---power-bi-report-server"></a>Skift forbindelsesstrenge til datakilden i Power BI-rapporter ved hjælp PowerShell – Power BI-rapportserver


Du kan ændre forbindelsesstrenge til datakilden i Power BI-rapporter i Power BI-rapportserver ved hjælp af API'er i PowerShell. 

> [!NOTE]
> Denne funktionalitet fungerer i øjeblikket kun for DirectQuery. Understøttelse af import og dataopdatering er på vej.

1. Installér PowerShell-commandlets for Power BI-rapportserver. Find commandlets og installationsvejledningen på [https://github.com/Microsoft/ReportingServicesTools](https://github.com/Microsoft/ReportingServicesTools). 

2. Hent oplysningerne om den eksisterende datakilde for Power BI-filen via PowerShell-commandlets:

    ```powershell
    Get-RsRestItemDataSource -RsItem '/MyPbixReport'
    ```

    Hvis du vil have vist oplysninger om den første datakilde, der findes i Power BI rapporten: 

    ```powershell
    $dataSources[0]
    ```

3. Opdater oplysningerne om forbindelse og legitimationsoplysninger efter behov. Hvis du opdaterer forbindelsesstrengen, og datakilden anvender gemte legitimationsoplysninger, skal du angive adgangskoden til kontoen. 

    Sådan opdaterer du en forbindelsesstreng til datakilden:

    ```powershell
    $dataSources[0].ConnectionString = 'data source=myCatalogServer;initial catalog=ReportServer;persist security info=False' 
    ```

    Sådan ændrer du typen af legitimationsoplysninger for datakilden:

    ```powershell
    $dataSources[0].DataModelDataSource.AuthType = 'Integrated'
    ```

    Sådan ændrer du brugernavn/adgangskode for datakilden:

    ```powershell
    $dataSources[0].DataModelDataSource.Username = 'domain\user'
    ```
    ```powershell
    $dataSources[0].DataModelDataSource.Secret = 'password'
    ```

4. Gem de opdaterede legitimationsoplysninger på serveren igen.

    ```powershell
    Set-RsRestItemDataSource -RsItem '/MyPbixReport' -RsItemType 'PowerBIReport' -DataSources $dataSources
    ```

## <a name="next-steps"></a>De næste trin

[Sideinddelte rapportdatakilder på Power BI-rapportserver](connect-data-sources.md) 

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)
