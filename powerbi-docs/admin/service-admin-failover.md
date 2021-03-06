---
title: Ofte stillede spørgsmål om høj tilgængelighed, failover og it-katastrofeberedskab i Power BI
description: Forstå, hvordan Power BI-tjenesten leverer høj tilgængelighed og sikrer forretningskontinuitet og it-katastrofeberedskab for brugerne.
author: kfollis
ms.author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 06/18/2020
LocalizationGroup: Administration
ms.openlocfilehash: 09e215dbb32dcb93b2ae8ca51953eb636e1aad81
ms.sourcegitcommit: e8c3f327ac0fc73c118874a24d2601733f8f9e45
ms.translationtype: MT
ms.contentlocale: da-DK
ms.lasthandoff: 01/23/2021
ms.locfileid: "98718479"
---
# <a name="power-bi-high-availability-failover-and-disaster-recovery-faq"></a>Ofte stillede spørgsmål om høj tilgængelighed, failover og it-katastrofeberedskab i Power BI

Denne artikel omhandler, hvordan Power BI-tjenesten leverer høj tilgængelighed og sikrer forretningskontinuitet og it-katastrofeberedskab for brugerne. Når du har læst denne artikel, bør du have en bedre forståelse af, hvordan høj tilgængelighed opnås, under hvilke omstændigheder Power BI udfører en failover, og hvad du kan forvente af tjenesten, når der udføres failover.

## <a name="what-does-high-availability-mean-for-power-bi"></a>Hvad betyder "høj tilgængelighed" for Power BI?

Power BI er fuldt administreret software som en service (SaaS).  Microsoft udvikler og styrer denne software, så den er modstandsdygtigt over for fejl i infrastrukturer, og så brugerne altid kan få adgang til deres rapporter.  Tjenesten understøttes af en [SLA på 99,9 %](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=37).

Power BI bruger **Azure Tilgængelighedszoner** til at beskytte Power bi rapporter, programmer og data fra datacenter fejl, og de anvendes automatisk og bruges til Power bi. Tilgængelighedszoner er fejlbehæftede placeringer i et Azure-område, der giver tre eller flere forskellige og entydige placeringer i et Azure-område, der har redundant strøm, køling og netværk. Tilgængelighedszoner give Power BI kunder mulighed for at køre missionskritiske programmer med høj tilgængelighed og fejltolerance for datacenter fejl. Tilgængelighedszoner giver kunderne mulighed for at modstå fejl i datacentret via redundans og logisk isolering af tjenester. 

Du kan finde flere oplysninger om **Tilgængelighedszoner** i følgende artikel, som går i detaljer om [områder og Tilgængelighedszoner i Azure](https://docs.microsoft.com/azure/availability-zones/az-overview).

## <a name="what-is-a-power-bi-failover"></a>Hvad er en Power BI-failover?

Power BI opretholder flere forekomster af hver komponent i Azure-datacentre (også kendt som områder) for at sikre forretningskontinuitet. Hvis der er et nedbrud eller et problem, som medfører, at Power BI bliver utilgængelig eller ikke fungerer i et område, udfører Power BI failover for alle sine komponenter i dette område til en sikkerhedskopi. I forbindelse med denne failover gendannes tilgængeligheden og funktionaliteten til forekomsten af Power BI-tjenesten i et nyt område (som regel inden for samme geografiske placering, som noteret i [Microsofts Center for sikkerhed og rettighedsadministration](https://www.microsoft.com/trust-center/product-overview)).

Der understøttes kun _læsehandlinger_ for en forekomst af Power BI-tjenesten med failover, hvilket betyder, at følgende handlinger ikke understøttes under failover: opdateringer, publiceringshandlinger for rapporter, ændringer af dashboards eller rapporter og andre handlinger, der kræver ændringer af Power BI-metadata (f.eks. indsætning af en kommentar i en rapport).  Læsehandlinger, f.eks. visning af dashboards og rapporter, der ikke er baseret på DirectQuery eller Live Connect til datakilder i det lokale miljø, fungerer fortsat normalt.

## <a name="how-are-backup-instances-kept-in-sync-with-my-data"></a>Hvordan bliver sikkerhedskopien synkroniseret med mine data?

Alle Power BI-tjenestekomponenter synkroniserer jævnligt deres sikkerhedskopier. Vi går efter et 15-minutters interval for alt indhold, der uploades eller ændres i Power BI. I tilfælde af en failover bruger Power BI [geo-redundant replikering af Azure-lager](/azure/storage/common/storage-redundancy-grs) og [geo-redundant replikering af Azure SQL](/azure/sql-database/sql-database-active-geo-replication) for at garantere, at der findes sikkerhedskopier i andre områder, som kan bruges i tilfælde af failover.

## <a name="where-are-the-failover-clusters-located"></a>Hvor er failoverklyngerne placeret?

Sikkerhedskopier befinder sig inden for den samme geografiske placering (geo), som du valgte, da din organisation tilmeldte sig Power BI undtagen de undtagelser, der er nævnt i [Microsofts Center for sikkerhed og rettighedsadministration](https://www.microsoft.com/trust-center/product-overview). En geografisk placering kan indeholde flere områder, og Microsoft kan replikere data til et hvilket som helst område inden for en bestemt geografisk placering for at sikre datarobusthed. Microsoft replikerer og flytter ikke kundedata uden for den geografiske placering. Du kan finde en kortoversigt over de geografiske placeringer, der tilbydes af Power BI, og områderne i dem i [Microsofts Center for sikkerhed og rettighedsadministration](https://www.microsoft.com/trust-center/product-overview).

## <a name="how-does-microsoft-decide-to-fail-over"></a>Hvordan beslutter Microsoft sig for at udføre failover?

Der er to forskellige systemer, som angiver, hvornår en failover kan være nødvendig:

- Vores eksterne og interne overvågningstest indikerer manglende tilgængelighed eller manglende evne til at fungere korrekt. Sådanne indikationer kan være baseret på udfald, der er registreret i Power BI-komponenter eller i en eller flere af de tjenester, som Power BI afhænger af i et område.
- Microsoft Azures team for central drift informerer os om et kritisk nedbrud i et område.

I begge tilfælde træffer medlemmer af Power BI's overordnede team beslutningen om at udføre failover. Selve beslutningen er ikke automatiseret. Når beslutningen er truffet, udføres processen for failover automatisk.

## <a name="how-do-i-know-power-bi-is-now-in-failover-mode"></a>Hvordan ved jeg, at Power BI nu er i failovertilstand?

Der slås en meddelelse op på Power BI-supportsiden ([https://powerbi.microsoft.com/support/](https://powerbi.microsoft.com/support/)). Meddelelsen indeholder de overordnede handlinger, der ikke er tilgængelige under failover, herunder publicering, opdatering, oprettelse af dashboard, duplikering af dashboard og ændringer af tilladelser.

## <a name="how-long-does-it-take-power-bi-to-fail-over"></a>Hvor lang tid tager det for Power BI at udføre failover?

Det tager ca. 15 minutter for Power BI at komme op og køre igen, når programmet har registreret, at en failover er nødvendig. Den tid, det tager at registrere, at en failover er nødvendig, afhænger af det scenarie, der er ødelagt. 

Når en failover udføres, bruger Power BI Azure Storage GEO-replikering til at udføre failover. Sådanne replikeringer har normalt et returpunkt på 15 minutter, men [Azure Storage garanterer ikke denne tidsramme](/azure/storage/common/storage-redundancy) med en SLA, og Power BI kan derfor heller ikke garantere en tidsramme. 

## <a name="what-happens-to-workspaces-and-reports-if-my-premium-capacity-becomes-unavailable"></a>Hvad sker der med arbejdsområder og rapporter, hvis min Premium-kapacitet bliver utilgængelig? 

Hvis en Premium-kapacitet bliver utilgængelig, forbliver arbejdsområder og rapporter tilgængelige og synlige for alle Power BI Pro-licenserede brugere, der tidligere har fået adgang til dem.

## <a name="when-does-my-power-bi-instance-return-to-the-original-region"></a>Hvornår vender min Power BI-forekomst tilbage til det oprindelige område?

Forekomster af Power BI-tjenesten vender tilbage til deres oprindelige område, når problemet, der forårsagede en failover, er løst. Se Power BI-supportsiden: Når problemet er løst, fjerner Power BI-teamet meddelelsen, der beskriver den pågældende failover. På dette tidspunkt bør driften være tilbage til normal.

## <a name="am-i-responsible-for-the-availability-of-my-power-bi-solution"></a>Er jeg ansvarlig for tilgængeligheden af min Power BI-løsning?

Hvis den Power BI-løsning, der bruges i din organisation, omfatter en af følgende elementer, skal du udføre nogle foranstaltninger for at garantere, at løsningen forbliver lettilgængelig:

- Hvis din organisation bruger Power BI Premium, skal du sikre, at størrelsen af Premium-kapaciteten er fastsat, så den imødekommer indlæsningskravene for din udrulning.  Du kan finde hjælp til at planlægge og opfylde dette krav i [Hvidbog om planlægning og udrulning i Power BI Premium](https://aka.ms/Premium-Capacity-Planning-Deployment) og [appen Power BI Premium Capacity Metrics ](service-admin-premium-monitor-capacity.md). Vi føjer jævnligt nye funktioner til Metrics-appen og administrationsportalen i Power BI som en hjælp.
- Hvis din organisation tilgår datakilder i det lokale miljø ved hjælp af datagatewayen i det lokale miljø, skal du konfigurere gatewayen, [som beskrevet i denne artikel](/data-integration/gateway/service-gateway-high-availability-clusters), for at kunne understøtte høj tilgængelighed. Følg denne vejledning, uanset om du er ved at opdatere rapporter i importtilstand, eller du tilgår data eller datamodeller ved hjælp af DirectQuery eller Live Connect.

## <a name="will-gateways-function-when-in-failover-mode"></a>Fungerer gateways i failovertilstand?

Nej. Data, der kræves fra datakilder i det lokale miljø (alle rapporter og dashboards, der er baseret på DirectQuery og Live Connect), fungerer ikke under en failover. Konfigurationen af gatewayen ændres dog ikke. Når forekomsten af Power BI vender tilbage til sin oprindelige tilstand, vender de pågældende gateways tilbage til deres normale funktioner.

I tilfælde af en ekstrem katastrofe i et primært område, der forhindrer, at den kan sættes online i en lang periode, muliggør den fejlbehæftede primære region både læse-og skrivehandlinger, og kunderne kan genudrulle og konfigurere gateways i forhold til det nye område.

Kunderne kan vælge at installere en ny gateway på en anden computer eller overtage den eksisterende gateway. Det bør være nemmere at overtage den eksisterende gateway, da alle de datakilder, der er knyttet til den gamle gateway, overføres til den nye.
