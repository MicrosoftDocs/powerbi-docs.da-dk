---
title: Distribuer indhold til eksterne gæstebrugere med Azure AD B2B
description: Power BI gør det muligt at dele indhold med eksterne gæstebrugere gennem Azure Active Directory Business-to-business (Azure AD B2B).
author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 09/09/2019
ms.author: kfollis
LocalizationGroup: Administration
ms.openlocfilehash: 25b136bfa15b00333400b80781d968d0b40d9779
ms.sourcegitcommit: a72567f26c1653c25f7730fab6210cd011343707
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/19/2020
ms.locfileid: "83564489"
---
# <a name="distribute-power-bi-content-to-external-guest-users-with-azure-ad-b2b"></a>Distribuer Power BI-indhold til eksterne gæstebrugere med Azure AD B2B

Power BI gør det muligt at dele indhold med eksterne gæstebrugere gennem Azure Active Directory Business-to-business (Azure AD B2B).
Når du bruger Azure AD B2B, kan din organisation aktivere og styre deling med eksterne brugere på et centralt sted. Eksterne gæster har som standard kun erfaring på forbrugerniveau. Du kan desuden give gæstebrugere uden for din organisation adgang til at redigere og administrere indhold i din organisation.

Denne artikel indeholder en grundlæggende introduktion til Azure AD B2B i Power BI. Du kan finde flere oplysninger under [Distribuer Power BI-indhold til eksterne gæster ved hjælp af Azure Active Directory B2B](../guidance/whitepaper-azure-b2b-power-bi.md).

## <a name="enable-access"></a>Aktivér adgang

Sørg for at aktivere funktionen [Del indhold med eksterne brugere](service-admin-portal.md#export-and-sharing-settings) på Power BI-administrationsportalen, før du inviterer gæstebrugere. Selv når denne indstilling er aktiveret, skal brugeren have tilladelse i Azure Active Directory til at invitere gæstebrugere, hvilket tildeles via rollen, der giver mulighed for at invitere gæster. 

Muligheden for at [give eksterne gæstebrugere tilladelse til at redigere og administrere indhold i organisationen](service-admin-portal.md#allow-external-guest-users-to-edit-and-manage-content-in-the-organization) lader dig give gæstebrugere mulighed for at se og oprette indhold i arbejdsområder, herunder gennemse organisationens Power BI.

> [!NOTE]
> Indstillingen [Del indhold med eksterne brugere](service-admin-portal.md#export-and-sharing-settings) styrer, om Power BI giver mulighed for at invitere eksterne brugere til din organisation. Når eksterne brugere accepterer invitationen, bliver de Microsoft Azure Active Directory B2B-gæstebrugere i din organisation. De vises i personvælgere i hele Power BI-oplevelsen. Når indstillingen er deaktiveret, har eksisterende gæstebrugere i din organisation fortsat adgang til alle de elementer, de havde adgang til, og vises fortsat i personvælgere. Hvis gæster er tilføjet via en [planlagt invitation](#planned-invites), vises de desuden i personvælgere. Brug en politik for betinget adgang til Azure Active Directory, hvis du vil forhindre gæstebrugere i at få adgang til Power BI.

## <a name="who-can-you-invite"></a>Hvem kan du invitere?

Gæstebrugere med de fleste mailadresser, inklusive personlige konti som gmail.com, outlook.com og hotmail.com, kan inviteres til din organisation. I Azure AD B2B kaldes disse adresser for *sociale identiteter*.

Du kan ikke invitere brugere, der er knyttet til en offentlig Cloud, f. eks. [Power BI til US Government](service-govus-overview.md).

## <a name="invite-guest-users"></a>Inviter gæstebrugere

Gæstebrugere kræver kun en invitation, første gang du inviterer dem ind i organisationen. Hvis du vil invitere brugere, skal du bruge planlagte invitationer eller ad hoc-invitationer.

Hvis du vil bruge ad hoc-invitationer, skal du bruge følgende funktioner:
* Deling af rapporter og dashboards
* Appadgangsliste

Ad hoc-invitationer understøttes ikke for adgangslister for arbejdsområder. Brug [planlagte invitationer](#planned-invites) til at føje disse brugere til din organisation. Når de eksterne brugere er gæster i din organisation, kan du føje dem til adgangslisterne for arbejdsområder.

### <a name="planned-invites"></a>Planlagte invitationer

Brug en planlagt invitation, hvis du ved, hvilke brugere du vil invitere. Du kan sende invitationen ved hjælp af Azure Portal eller PowerShell. Du skal være en lejeradministrator for at invitere brugere.

Følg disse trin for at sende en invitation via Azure Portal.

1. På [Azure Portal](https://portal.azure.com) skal du vælge **Azure Active Directory**.

1. Under **Administrer** skal du vælge **Brugere** > **Alle brugere** > **Ny gæstebruger**.

    ![Skærmbillede af Azure-portalen, hvor indstillingen Ny gæstebruger fremhævet.](media/service-admin-azure-ad-b2b/azure-ad-portal-new-guest-user.png)

1. Angiv en **mailadresse** og **personlig meddelelse**.

    ![Skærmbillede af dialogboksen Ny gæstebruger på Azure AD-portalen.](media/service-admin-azure-ad-b2b/azure-ad-portal-invite-message.png)

1. Vælg **Inviter**.

Hvis du vil invitere mere end én gæstebruger, skal du bruge PowerShell. Du kan finde flere oplysninger i [Azure AD B2B-samarbejdskode og PowerShell-eksempler](/azure/active-directory/b2b/code-samples/).

Gæstebrugeren skal vælge **Introduktion** i den invitation, de får på mail. Gæstebrugeren føjes derefter til lejeren.

![Skærmbillede af Mailinvitation til gæstebruger.](media/service-admin-azure-ad-b2b/guest-user-invite-email.png)

### <a name="ad-hoc-invites"></a>Ad hoc-invitationer

Du kan når som helst invitere en ekstern bruger ved at føje personen til dit dashboard eller din rapport via delingsgrænsefladen eller til din app via adgangssiden. Her er et eksempel på, hvad du skal gøre, når du inviterer en ekstern bruger til at anvende en app.

![Skærmbillede af Ekstern bruger, der er føjet til Appens adgangsliste i Power BI.](media/service-admin-azure-ad-b2b/power-bi-app-access.png)

Gæstebrugeren modtager en mail med besked om, at du har delt appen med vedkommende.

![Skærmbillede af mail om, at appen er delt med gæstebrugeren](media/service-admin-azure-ad-b2b/guest-user-invite-email-2.png)

Gæstebrugeren skal logge på med sin mailadresse for organisationen. Gæstebrugeren vil blive bedt om at acceptere invitationen, når vedkommende har logget på. Efter logon åbnes appen for gæstebrugeren. For at vende tilbage til appen skal vedkommende tilføje linket som bogmærke eller gemme mailen.


## <a name="licensing"></a>Licensering

Gæstebrugeren skal have den korrekte licens for at få vist det indhold, du har delt. Der er tre muligheder for at sikre, at brugeren har den korrekte licens: Brug Power BI Premium, tildel en Power BI Pro-licens, eller brug gæstens Power BI Pro-licens.

[Gæstebrugere, der kan redigere og administrere indhold i organisationen](service-admin-portal.md#allow-external-guest-users-to-edit-and-manage-content-in-the-organization) skal bruge en Power BI Pro-licens til at bidrage med indhold til arbejdsområder eller dele indhold med andre.

### <a name="use-power-bi-premium"></a>Brug Power BI Premium

Tildeling af arbejdsområdet til [Power BI Premium-kapacitet](service-premium-what-is.md) giver gæstebrugeren mulighed for at bruge appen uden at have en Power BI Pro-licens. Med Power BI Premium kan apps også drage fordel af andre funktioner, f.eks. øget opdateringshastighed, dedikeret kapacitet og store modelstørrelser.

![Diagram over gæstebrugerens oplevelse med Power BI Premium.](media/service-admin-azure-ad-b2b/license-approach-1.png)

### <a name="assign-a-power-bi-pro-license-to-guest-user"></a>Tildel en Power BI Pro-licens til en gæstebruger

Tildeling af en Power BI Pro-licens til en gæstebruger i din lejer giver gæstebrugeren mulighed for at få vist indholdet i lejeren. Du kan finde flere oplysninger om tildeling af licenser under [Tildel licenser til brugere på siden Licenser](/office365/admin/manage/assign-licenses-to-users#assign-licenses-to-users-on-the-licenses-page). Før du tildeler Pro-licenser til gæstebrugere, skal du kontakte din Microsoft-kontorepræsentant for at sikre, at du overholder vilkårene i din aftale med Microsoft.

![Diagram over gæstebrugerens oplevelse med en tildelt Pro-licens fra din lejer.](media/service-admin-azure-ad-b2b/license-approach-2.png)

### <a name="guest-user-brings-their-own-power-bi-pro-license"></a>Gæstebrugeren medtager sin egen Power BI Pro-licens

Gæstebrugeren har allerede en Power BI Pro-licens, der er tildelt i deres lejer.

![Diagram over gæstebrugerens oplevelse, når vedkommende bruger sin egen licens.](media/service-admin-azure-ad-b2b/license-approach-3.png)

## <a name="guest-users-who-can-edit-and-manage-content"></a>Gæstebrugere, der kan redigere og administrere indhold

Når du bruger funktionen [Tillad, at eksterne gæstebrugere kan redigere og administrere indhold i organisationen](service-admin-portal.md#allow-external-guest-users-to-edit-and-manage-content-in-the-organization), får de angivne gæstebrugere yderligere adgang til din organisations Power BI. Gæster med tilladelse kan se alt indhold, de har tilladelse til, få adgang til startsiden, gennemse arbejdsområder, installere apps, se, hvor de er på adgangslisten, og bidrage med indhold til arbejdsområder. De kan oprette eller være administrator af arbejdsområder, der bruger den nye arbejdsområdeoplevelse. Der er visse begrænsninger. Du finder en liste over disse begrænsninger i afsnittet Overvejelser og begrænsninger.
 
Du kan hjælpe gæster med tilladelse med at logge på Power BI ved at give dem lejerens URL-adresse. Du kan finde lejerens URL-adresse ved at følge disse trin.

1. Vælg hjælp ( **?** ) i den øverste menu i Power BI, og vælg derefter **Om Power BI**.

2. Søg efter værdien ud for **Lejerens URL-adresse**. Del lejerens URL-adresse med de gæstebrugere, du har givet tilladelse.

    ![Skærmbillede af dialogboksen Om Power BI, hvor URL-adressen for lejeren til gæstebrugere er fremhævet.](media/service-admin-azure-ad-b2b/power-bi-about-dialog.png)

## <a name="considerations-and-limitations"></a>Overvejelser og begrænsninger

* Med ekstern Azure AD B2B begrænses gæster som standard til udelukkende at kunne forbruge indhold. Eksterne Azure AD B2B-gæster kan få vist apps, dashboards og rapporter samt eksportere data og oprette mailabonnementer på dashboards og rapporter. De kan ikke få adgang til arbejdsområder eller udgive deres eget indhold. Hvis du vil fjerne disse begrænsninger, kan du bruge funktionen [Tillad, at eksterne brugere kan redigere og administrere indhold i organisationen](service-admin-portal.md#allow-external-guest-users-to-edit-and-manage-content-in-the-organization).

* Hvis du vil invitere gæstebrugere, kræves der en Power BI Pro licens. Brugere af Pro-prøveversioner kan ikke invitere gæstebrugere til Power BI.

* Nogle oplevelser er ikke tilgængelige for [gæstebrugere, der kan redigere og administrere indhold i organisationen](service-admin-portal.md#allow-external-guest-users-to-edit-and-manage-content-in-the-organization). Hvis de skal opdatere eller publicere rapporter, skal de bruge Power BI-tjenestens webgrænseflade, herunder Hent Data for at overføre Power BI Desktop-filer.  Følgende funktioner understøttes ikke:
    * Direkte publicering fra Power BI Desktop til Power BI-tjenesten.
    * Gæstebrugere kan ikke bruge Power BI Desktop til at oprette forbindelse til tjenestedatasæt i Power BI-tjenesten
    * Klassiske arbejdsområder, der er knyttet til Microsoft 365 Grupper:
        * Gæstebrugeren kan ikke oprette eller være administrator af disse arbejdsområder
        * Gæstebrugere kan være medlemmer
    * Afsendelse af ad hoc-invitationer understøttes ikke for adgangslister for arbejdsområder
    * Power BI Publisher til Excel understøttes ikke for gæstebrugere
    * Gæstebrugere kan ikke installere en Power BI Gateway og forbinde den med din organisation
    * Gæstebrugere kan ikke installere apps, der publiceres til hele organisationen
    * Gæstebrugere kan ikke bruge, oprette, opdatere eller installere organisationsindholdspakker
    * Gæstebrugere kan ikke anvende Analysér i Excel
    * Gæstebrugere må ikke være @mentioned i kommentarer
    * Gæstebrugere kan ikke bruge abonnementer
    * Gæstebrugere, der bruger denne funktion, skal have en arbejds- eller skolekonto. 
    
* Der er flere begrænsninger for de gæstebrugere, der bruger personlige konti, på grund af logonbegrænsninger.
    * De kan bruge forbrugsoplevelser i Power BI-tjenesten via en webbrowser
    * De kan ikke bruge apps til Power BI – Mobil.
    * De kan ikke logge på for at angive legitimationsoplysninger, hvor der kræves en arbejds- eller skolekonto.

* Denne funktion er i øjeblikket ikke tilgængelig med rapportwebdelen til Power BI SharePoint Online.

* Der findes Active Directory-indstillinger, der kan begrænse, hvad eksterne gæstebrugere kan foretage sig overordnet i organisationen. Dette gælder også for dit Power BI-miljø. I følgende dokumentation beskrives indstillingerne:
    * [Administrer indstillinger for eksternt samarbejde](/azure/active-directory/b2b/delegate-invitations#configure-b2b-external-collaboration-settings)
    * [Tillad eller bloker invitationer til B2B-brugere fra bestemte organisationer](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)
    * [Tillad eller bloker gæstebrugeres adgang til Power BI-tjenesten](/azure/active-directory/conditional-access/overview)
    
* Deling uden for organisationen understøttes ikke i nationale cloudmiljøer. I stedet skal du oprette brugerkonti i din organisation, som eksterne brugere kan bruge til at få adgang til indholdet. 

* Hvis du deler direkte med en gæstebruger, sender Power BI en mail til dem med linket. Hvis du vil undgå at sende en mail, skal du føje gæstebrugeren til en sikkerhedsgruppe og dele med sikkerhedsgruppen.  

## <a name="next-steps"></a>Næste trin

Du kan finde flere oplysninger, herunder hvordan sikkerhed på rækkeniveau fungerer, i dette whitepaper: [Distribuer Power BI-indhold til eksterne gæstebrugere med Azure AD B2B](https://aka.ms/powerbi-b2b-whitepaper).

Du kan finde oplysninger om Azure AD B2B i [Hvad er Azure AD B2B-samarbejde?](/azure/active-directory/active-directory-b2b-what-is-azure-ad-b2b/).
