---
title: Ruden Analyse i Power BI-visualiseringer
description: I denne artikel beskrives det, hvordan du opretter dynamiske referencelinjer i Power BI-visualiseringer.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.topic: how-to
ms.subservice: powerbi-custom-visuals
ms.date: 06/18/2019
ms.openlocfilehash: e9d1479b596f563edc37f0c7a72b29c3343fed1e
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/23/2020
ms.locfileid: "85239915"
---
# <a name="the-analytics-pane-in-power-bi-visuals"></a>Ruden Analyse i Power BI-visualiseringer

Ruden **Analyse** blev introduceret til [oprindelige visualiseringer](https://docs.microsoft.com/power-bi/desktop-analytics-pane) i november 2018.
I denne artikel gennemgås det, hvordan Power BI-visualiseringer med API v2.5.0 kan præsentere og administrere deres egenskaber i ruden **Analyse**.

![Ruden Analyse](media/analytics-pane/visualization-pane-analytics-tab.png)

## <a name="manage-the-analytics-pane"></a>Administrer ruden Analyse

På samme måde som du ville administrere egenskaberne i ruden [**Format**](https://docs.microsoft.com/power-bi/developer/visuals/custom-visual-develop-tutorial-format-options), administrerer du ruden **Analyse** ved at definere et objekt i den pågældende visualiserings *capabilities.json*-fil.

Der er følgende forskelle for ruden **Analyse**:

* Under objektets definition skal du tilføje feltet **objectCategory** med værdien 2.

    > [!NOTE]
    > Det valgfrie felt `objectCategory` blev introduceret i API 2.5.0. Det definerer den del af visualiseringen, som objektet styrer (1 = formatering, 2 = analyse). `Formatting` bruges til elementer som f.eks. udseende og funktionalitet, farver, akser og etiketter. `Analytics` bruges til elementer som prognoser, tendenslinjer, referencelinjer og former.
    >
    > Hvis værdien ikke er angivet, bruges "Formatering" som standard af `objectCategory`.

* Objektet skal have følgende to egenskaber:
    * `show` af type `bool` med en standardværdi på `false`.
    * `displayName` af type `text`. Den standardværdi, du vælger, bliver forekomstens indledende viste navn.

```json
{
  "objects": {
    "YourAnalyticsPropertiesCard": {
      "displayName": "Your analytics properties card's name",
      "objectCategory": 2,
      "properties": {
        "show": {
          "type": {
            "bool": true
          }
        },
        "displayName": {
          "type": {
            "text": true
          }
        },
      ... //any other properties for your Analytics card
      }
    }
  ...
  }
}
```

Du kan definere andre egenskaber på samme måde som **Formater** objekter. Du kan også optælle objekter på samme måde som i ruden **Format.**

## <a name="known-limitations-and-issues-of-the-analytics-pane"></a>Kendte begrænsninger og problemer med ruden Analyse

* Ruden **Analyse** understøtter endnu ikke flere forekomster. Objekter kan ikke have en anden [vælger](https://microsoft.github.io/PowerBI-visuals/docs/concepts/objects-and-properties/#selector) end statisk (dvs. "vælger": null), og Power BI-visualiseringer kan ikke have flere brugerdefinerede forekomster på et kort.
* Egenskaber af typen `integer` vises ikke korrekt. Du kan løse problemet ved at bruge typen `numeric` i stedet.

> [!NOTE]
> * Brug kun ruden **Analyse** til objekter, der tilføjer nye oplysninger eller kaster nyt lys over de præsenterede oplysninger (f.eks. dynamiske referencelinjer, der illustrerer vigtige tendenser).
> * Alle indstillinger, der styrer visualiseringens udseende (dvs. formateringen), skal begrænses til ruden **Formatering**.
