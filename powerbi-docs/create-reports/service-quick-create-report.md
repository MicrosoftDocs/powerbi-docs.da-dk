---
title: Opret hurtigt rapporter i Power BI-tjenesten
description: Der er en ny måde, hvorpå du kan oprette rapporter hurtigt i Power BI-tjenesten. Indsæt data direkte i Power BI på internettet, så opretter Power BI automatisk visualiseringer for dig.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
ms.service: powerbi
ms.subservice: pbi-reports-dashboards
ms.topic: how-to
ms.date: 12/16/2020
LocalizationGroup: Reports
ms.openlocfilehash: 689c15994528df253de7d3d1b844ec0ef979d6da
ms.sourcegitcommit: 0711972326521944fdd8572403c0b15f31b916da
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 12/22/2020
ms.locfileid: "97729820"
---
# <a name="create-quick-reports-in-the-power-bi-service"></a>Opret hurtigt rapporter i Power BI-tjenesten 

Der er en ny måde, hvorpå du kan oprette rapporter hurtigt i Power BI-tjenesten. I stedet for at downloade Power BI Desktop-appen og importere dataene, kan du indsætte data direkte i Power BI på internettet, så genererer Power BI automatisk visualiseringer for dig.  

Er du ikke erfaren med at oprette i Power BI? Prøv at læse [Rapporter i Power BI](../consumer/end-user-reports.md) for at få lidt baggrundsoplysninger.

:::image type="content" source="media/service-quick-create-report/quick-create.gif" alt-text="Brug Hurtig oprettelse i Power BI til at oprette en rapport hurtigt.":::

## <a name="create-a-quick-report"></a>Opret en rapport hurtigt
I navigationsruden i Power BI-tjenesten kan du vælge knappen **Opret**, der åbner en side, hvor du kan vælge din datakilde. Den er også tilgængelig via knappen **Ny rapport** på startsiden.

:::image type="content" source="media/service-quick-create-report/create-entry-point.png" alt-text="Ikonet Opret indgangspunkt i Power BI-tjenesten."::: 

I øjeblikket understøtter vi kun oprettelse af en rapport baseret på et eksisterende datasæt, eller hvis du skriver eller indsætter data direkte i en tabel. Med tiden kan du se andre kilder, f.eks. upload af en Excel-fil.  

:::image type="content" source="media/service-quick-create-report/create-source-options.png" alt-text="Tilføj data for at oprette en rapport, kildeindstillinger.":::

Når du vælger at skrive eller indsætte data, får du vist et gitter, som du kan begynde at skrive i. Du kan også indsætte data ved hjælp af Ctrl + V eller genvejsmenuen.

:::image type="content" source="media/service-quick-create-report/create-enter-data-window.png" alt-text="Skriv eller indsæt i vinduet Angiv data.":::

Du kan bruge genvejsmenuen for tilføjelse og fjernelse af kolonner. Hvis dine indsatte data indeholder en rækkeoverskrift, skal du vælge **Brug første række som overskrift** for automatisk at hæve den første række til rækkeoverskriften. Power BI registrerer automatisk datatyperne, men du har mulighed for at angive dem manuelt. Vælg knappen **Datatype** ud for kolonnenavnet. 

:::image type="content" source="media/service-quick-create-report/change-data-type.png" alt-text="Skift kolonnens datatype."::: 

Når du gennemgår oprettelsesprocessen, opretter Power BI et nyt datasæt for dig, og der genereres automatisk en opsummeret visning af dine data. Disse automatisk genererede visualiseringer hjælper dig fra rådata til indsigt hurtigere end nogensinde før.  

:::image type="content" source="media/service-quick-create-report/autogenerated-report.png" alt-text="Power BI opretter automatisk visualiseringer baseret på dine data.":::

Det er også nemt at ændre de data, du kan se i rapporten. Brug ruden **Opsummer** til at tilføje eller fjerne felter fra rapporten. Markér og fjern markeringen af felter for at opdatere det, du vil måle og analysere. Power BI tilføjer eller fjerner automatisk diagrammer for at vise de nye kombinationer.  

I øjeblikket kan du maksimalt se tre målinger, der vises som rækker i rapporten, og fire kategorier, der vises som kolonner i rapporten. 

:::image type="content" source="media/service-quick-create-report/summarize-pane.png" alt-text="Rediger den måde, hvorpå Power BI opsummerer dataene i ruden Opsummer.":::

Hvis du vil se et felt, der er opsummeret på en anden måde, skal du bruge genvejsmenuen for feltet i ruden **Opsummer** til at skifte mellem sum, gennemsnit, maksimum, minimum osv. 

:::image type="content" source="media/service-quick-create-report/summarize-options.png" alt-text="Skift mellem sum, gennemsnit, maksimum, minimum osv.":::

Du kan gemme denne rapport i det arbejdsområde, du var i, da du først valgte **Opret**. Herfra kan du dele den på samme måde som med enhver anden rapport. Næste gang du eller andre med redigeringstilladelser åbner rapporten, lander I direkte i denne funktionalitet til hurtig redigering.  

Hvis du vil skifte til funktionaliteten til fuld redigering, skal du vælge knappen **Rediger** på menulinjen. Vær dog opmærksom på, at du ikke kan vende tilbage til visningen med hurtig redigering, når du først har gemt rapporten via funktionaliteten til fuld redigering.  

:::image type="content" source="media/service-quick-create-report/edit-entry-point.png" alt-text="Vælg knappen Rediger på menulinjen.":::

Denne funktionalitet burde gøre det lettere at oprette rapporter med dine data og dermed åbne døren til oprettelse af rapporter for helt nye brugere. Prøv den nye oprettelsesfunktionalitet i dag.

## <a name="considerations-and-limitations"></a>Overvejelser og begrænsninger

### <a name="licenses"></a>Licenser

Du skal bruge samme licens til at oprette en rapport hurtigt, som når du opretter en hvilken som helst anden rapport i Power BI. Hvis du har en gratis Power BI-licens, og Mit arbejdsområde er tildelt en Premium-kapacitet, kan du oprette rapporter hurtigt dér. Hvis du har en Power BI Pro-licens, kan du oprette rapporter hurtigt hvor som helst i Power BI-tjenesten. Se flere oplysninger under [Funktioner i Power BI-tjenesten efter licenstype](../fundamentals/service-features-license-type.md).


### <a name="get-data-limitations"></a>Se databegrænsninger 

- Hvis du bruger indstillingen **Indsæt eller angiv data manuelt**, er det i øjeblikket ikke muligt at opdatere dataene senere. Hvis du vil tilføje, redigere eller slette data senere, skal du gennemgå arbejdsprocessen **Opret** igen og få en ny rapport.  
- Hvis du har en CSV- eller Excel-fil, skal du bruge indstillingen Indsæt for at tilføje dine data. Der kommer en indstilling til filupload senere. 
- Når du kopierer data til vinduet **Angiv data**, må størrelsen af de data, du indsætter, ikke overstige 512 KB. 
- Tabelnavnet må ikke indeholde mere end 80 tegn, og kolonnenavne må ikke være længere end 512 tegn.  
- Tabel- og kolonnenavne må ikke indeholde dobbelte anførselstegn ("), punktummer (.) eller foranstillede eller efterstillede blanktegn.  

### <a name="model-limitations"></a>Modelbegrænsninger

Når du gennemgår denne oprettelsesproces, opretter du en model bag kulisserne på internettet. Disse webudviklede modeller svarer til dem, der oprettes i Power BI Desktop, men har nogle få begrænsninger.

| Udvalgt | Status  | Detaljer |
|---------|---------|---------|
| ALM | Understøttes ikke i øjeblikket | ALM fungerer ikke for webudviklede datasæt. |
| BYOK (Bring Your Own Key) | Understøttes ikke i øjeblikket | Du kan ikke bruge din egen krypteringsnøgle til webudviklede datasæt. |
| Skabelonapps | Understøttes ikke i øjeblikket | Du kan ikke oprette apps til arbejdsområder med webudviklede datasæt. |  
| Offentlige administrator-API'er | Understøttes delvist | De fleste offentlige administrator-API'er understøttes. Der er dog et kendt problem med følgende handling **Administrator – GetGroupsAsAdmin for grupper med udvidede datasæt**. I forbindelse med denne handling returneres webudviklede datasæt, men ContentProviderType er forkert markeret som "RealTime". |

### <a name="report-limitations"></a>Begrænsninger for rapporter  

Hvis du bruger indstillingen **Rediger** til at skifte til fuld redigeringstilstand og gemmer rapporten, kan du ikke længere skifte tilbage til den automatisk genererede visning med opsummeringsruden. Power BI minder dig om dette, når du vælger **Rediger**.  

:::image type="content" source="media/service-quick-create-report/quick-create-switch-edit-mode.png" alt-text="Skift til Redigeringstilstand fra tilstanden Hurtig oprettelse.":::

## <a name="next-steps"></a>Næste trin

* [Rapporter i Power BI](../consumer/end-user-reports.md)
* Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)
