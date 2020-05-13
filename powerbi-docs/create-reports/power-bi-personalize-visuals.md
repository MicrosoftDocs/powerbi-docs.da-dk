---
title: Lad brugerne tilpasse visualiseringer i en rapport
description: Lad læserne af en rapport oprette deres egen visning af en rapport uden at redigere den.
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/09/2020
ms.author: maggies
LocalizationGroup: Reports
ms.openlocfilehash: abc936c6ea4b61e4837e05fbde110e5159296815
ms.sourcegitcommit: a199dda2ab50184ce25f7c9a01e7ada382a88d2c
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/06/2020
ms.locfileid: "82867110"
---
# <a name="let-users-personalize-visuals-in-a-report"></a>Lad brugerne tilpasse visualiseringer i en rapport

[!INCLUDE [applies-to](../includes/applies-to.md)] [!INCLUDE [yes-desktop](../includes/yes-desktop.md)] [!INCLUDE [yes-service](../includes/yes-service.md)]

Når du deler en rapport med en bred målgruppe, vil nogle af brugerne måske gerne se en lidt anden visning af bestemte visualiseringer. Måske vil de gerne bytte om på aksen, ændre visualiseringstype eller føje noget til værktøjstippet. Det er svært at lave én visualisering, der opfylder alles krav. Med denne nye funktionalitet giver du dine forbrugere mulighed for at udforske og tilpasse visualiseringer – alt sammen i læsevisningen af rapporten. De kan tilpasse visualiseringen, lige som de vil, og gemme den som et bogmærke, så de kan vende tilbage til den. De behøver ikke at have redigeringstilladelser til rapporten eller henvende sig til rapportforfatteren med en ændring.

:::image type="content" source="media/power-bi-personalize-visuals/power-bi-personalize-visual.png" alt-text="Tilpas en visualisering":::
 
## <a name="what-report-consumers-can-change"></a>Hvad kan forbrugere af rapporter ændre?

Denne funktion giver forbrugerne mulighed for at få yderligere indsigt via ad hoc-udforskning af visualiseringer i en Power BI-rapport. Funktionen er ideel til rapportudviklere, der gerne vil aktivere grundlæggende udforskningsscenarier for læserne af deres rapport. Læserne af rapporten kan udføre følgende ændringer:

- Ret visualiseringstypen
- Udskift en måling eller dimension
- Tilføj eller fjern en forklaring
- Sammenlign to eller flere målinger
- Skift sammenlægninger osv.

Denne funktion muliggør ikke kun nye udforskningsegenskaber. Den omfatter også måder for forbrugerne at registrere og dele deres ændringer på:

- Registrer deres ændringer
- Del deres ændringer
- Nulstil alle deres ændringer af en rapport
- Nulstil alle deres ændringer af en visualisering
- Ryd deres seneste ændringer

## <a name="turn-on-the-preview-feature"></a>Aktivér prøveversionsfunktionen

Da denne funktion er en prøveversion, skal du først slå funktionskontakten til. Gå til **Filer** > **Indstillinger** > **Indstillinger**. Under **Globale** indstillinger > **Prøveversionsfunktioner** skal du sørge for, at **Tilpas visualiseringer** er valgt.

:::image type="content" source="media/power-bi-personalize-visuals/power-bi-preview-personalize-visual.png" alt-text="Slå Tilpas visualiseringer til":::

Du skal måske genstarte Power BI Desktop for at se den under indstillingerne for den aktuelle fil.

## <a name="enable-personalization-in-a-report"></a>Aktivér tilpasning i en rapport

Når du har slået prøveversionskontakten til, skal du aktivere den specifikt for de rapporter, som forbrugerne skal kunne tilpasse visualiseringer for.

Du kan aktivere denne funktion enten i Power BI Desktop eller Power BI-tjenesten.

### <a name="in-power-bi-desktop"></a>I Power BI Desktop

Du aktiverer funktionen i Power BI Desktop ved at gå til **Filer** > **Indstillinger** > **Indstillinger** > **Aktuel fil** > **Rapportindstillinger**. Sørg for, at **Tilpas visualiseringer (prøveversion)** er slået til.

:::image type="content" source="media/power-bi-personalize-visuals/power-bi-report-settings-personalize-visual.png" alt-text="Aktivér tilpasning i en rapport":::

### <a name="in-the-power-bi-service"></a>I Power BI-tjenesten

Du aktiverer funktionen i Power BI-tjenesten ved at gå til **Indstillinger** for din rapport.

:::image type="content" source="media/power-bi-personalize-visuals/power-bi-report-service-settings-personalize-visual.png" alt-text="Rapportindstillinger i Power BI-tjenesten":::

Slå **Tilpas visualiseringer (prøveversion)** til  > **Gem**.

:::image type="content" source="media/power-bi-personalize-visuals/power-bi-report-service-personalize-visual.png" alt-text="Slå Tilpas visualiseringer i tjenesten til":::

## <a name="select-visuals-that-can-be-personalized"></a>Vælg de visualiseringer, der kan tilpasses

Når du aktiverer denne indstilling for en given rapport, kan alle visualiseringer i denne rapport som standard tilpasses. Hvis du ikke ønsker, at alle visualiseringer skal kunne tilpasses, kan du slå indstillingen til eller fra for hver visualisering.

Vælg visualiseringen > vælg **Formatér** i ruden **Visualiseringer** > udvid **Overskrift i visualisering**.

:::image type="content" source="media/power-bi-personalize-visuals/power-bi-format-visual-header-personalize.png" alt-text="Vælg overskrift i visualisering":::
 
Slå skyderen for **Tilpas visualisering** >  **Til** eller **Fra**.

:::image type="content" source="media/power-bi-personalize-visuals/power-bi-format-visual-personalize-on-off.png" alt-text="Skyder for tilpasning af visualisering til eller fra":::

## <a name="personalize-visuals-in-the-power-bi-service"></a>Tilpas visualiseringer i Power BI-tjenesten

Når en visualisering tilpasses, kan forbrugerne udforske dine data på mange måder uden at forlade læsevisningen af rapporten. I følgende eksempler vises forskellige måder, som brugerne kan redigere en visualisering på for at få opfyldt deres behov. 

1. Åbn en rapport i læsevisning i Power BI-tjenesten.

2. I øverste højre hjørne af visualiseringen skal du vælge ikonet **Tilpas denne visualisering** ![ikonet Tilpas denne visualisering](media/power-bi-personalize-visuals/power-bi-personalize-visual-icon.png). 

### <a name="change-the-visualization-type"></a>Ret visualiseringstypen

Du kan få vist visualiseringen i en anden repræsentation ved at ændre **visualiseringstypen**.

:::image type="content" source="media/power-bi-personalize-visuals/power-bi-personalize-change-visual-type.png" alt-text="Skift visualiseringstype":::
 
### <a name="swap-out-a-measure-or-dimension"></a>Udskift en måling eller dimension
Du kan udskifte en måling eller dimension på X-aksen ved at vælge det felt, du vil udskifte, og derefter vælge en anden måling eller dimension.

:::image type="content" source="media/power-bi-personalize-visuals/power-bi-personalize-change-axis.png" alt-text="Skift akse":::
 
### <a name="add-or-remove-a-legend"></a>Tilføj eller fjern en forklaring
Når du tilføjer en forklaring, kan du farvekode en visualisering baseret på en kategori. Du kan fjerne farvekodningen for kategorien ved at rydde feltet **Forklaring** i ruden **Tilpas**. 

:::image type="content" source="media/power-bi-personalize-visuals/power-bi-personalize-change-legend.png" alt-text="Tilføj eller fjern forklaringen":::

### <a name="compare-two-or-more-different-measures"></a>Sammenlign to eller flere forskellige målinger
Du kan sammenligne værdier for forskellige målinger ved hjælp af ikonet + for at tilføje flere målinger for en visualisering.

:::image type="content" source="media/power-bi-personalize-visuals/power-bi-personalize-compare-measures.png" alt-text="Sammenlign målinger":::

### <a name="change-aggregations"></a>Skift sammenlægninger
Du kan ændre, hvordan en måling beregnes ved at ændre sammenlægningerne i ruden **Tilpas**.

:::image type="content" source="media/power-bi-personalize-visuals/power-bi-personalize-change-aggregation.png" alt-text="Skift sammenlægninger":::

### <a name="capture-changes"></a>Registrer ændringer 
Ved hjælp af personlige bogmærker kan du registrere dine ændringer, så du kan vende tilbage til din tilpassede visning. 

:::image type="content" source="media/power-bi-personalize-visuals/power-bi-personalize-bookmark.png" alt-text="Opret et bogmærke":::
 
Du kan også gøre bogmærket til din standardvisning.

### <a name="share-changes"></a>Del ændringer 
Hvis du har tilladelse til at læse og dele igen, kan du vælge at inkludere dine ændringer, når du deler rapporten.

:::image type="content" source="media/power-bi-personalize-visuals/power-bi-personalize-share-changes.png" alt-text="Del ændringer":::
 
### <a name="reset-all-your-changes-to-a-report"></a>Nulstil alle dine ændringer af en rapport

Vælg **Nulstil til standard** for at fjerne alle dine ændringer af rapporten og vende tilbage til forfatterens seneste gemte visning af rapporten.

:::image type="content" source="media/power-bi-personalize-visuals/power-bi-personalize-reset-all.png" alt-text="Nulstil alle ændringer":::
 
### <a name="reset-all-your-changes-to-a-visual"></a>Nulstil alle dine ændringer af en visualisering

Vælg **Nulstil denne visualisering** for at fjerne alle dine ændringer af en bestemt visualisering og vende tilbage til forfatterens seneste gemte visning af den pågældende visualisering.

:::image type="content" source="media/power-bi-personalize-visuals/power-bi-personalize-reset-visual.png" alt-text="Nulstil alle ændringer af visualiseringer":::
 
### <a name="clear-recent-changes"></a>Ryd seneste ændringer

Vælg viskelæderikonet for at rydde alle seneste ændringer, du har foretaget, siden du åbnede ruden **Tilpas**.  

:::image type="content" source="media/power-bi-personalize-visuals/power-bi-personalize-revert-changes.png" alt-text="Omdan seneste ændringer":::

## <a name="limitations-and-known-issues"></a>Begrænsninger og kendte problemer

Der er i øjeblikket nogle få begrænsninger for funktionen, som du skal være opmærksom på.

- Denne funktion understøttes ikke i integrerede scenarier, herunder publicer på internettet.
- Brugerudforskninger bevares ikke automatisk. Du skal gemme din visning som et personligt bogmærke for at registrere dine ændringer.
- Du kan ikke ændre visualiseringer i Power BI-mobilapps. Ændringer af visualiseringer, som du gemmer som et personligt bogmærke, mens du er i Power BI-tjenesten, bevares i mobilapps.

Der er også nogle kendte problemer, som vi er i gang med at håndtere:

- Tilføjelse af hierarki understøttes ikke. Du skal tilføje de enkelte underordnede elementer.
- Du kan ikke ændre et datohierarki til en dato eller omvendt. 
- Med personlige bogmærker får du måske resultater, der er lidt anderledes, afhængigt af den valgte sekvens. Der kan være uoverensstemmelser, fordi vi ikke registrerer den fulde stilstand af rapporten, men kun de foretagne ændringer. Du kan løse problemet ved at vælge **Nulstil til standard** og derefter vælge det bogmærke, du vil have vist. 

## <a name="next-steps"></a>Næste trin

Prøv den nye funktionalitet til tilpasning af visualiseringer. Giv os din feedback på denne funktion, og hvordan vi fortsat kan forbedre den, på [webstedet med Power BI-ideer](https://ideas.powerbi.com/forums/265200-power-bi). 

Har du flere spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)
