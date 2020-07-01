---
title: Övervaka Power BI Premium-kapaciteter med appen Premium Capacity Metrics.
description: Använd Power BI-administratörsportalen och appen Power BI Premium Capacity Metrics
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: how-to
ms.date: 05/18/2020
LocalizationGroup: Premium
ms.openlocfilehash: a8504bcd8045b248968b30b24dd4ff5b3af4cab4
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85228118"
---
# <a name="monitor-premium-capacities-with-the-app"></a>Övervaka Premium-funktioner med appen

Övervakning av dina kapaciteter är viktigt för att fatta välgrundade beslut om hur du bäst använder dina Premium-kapacitetsresurser. Du kan övervaka kapacitet med administratörsportalen eller med appen **Power BI Premium Capacity Metrics**. I den här artikeln beskrivs appen Premium Capacity Metrics. Appen ger den mest djupgående informationen om hur kapaciteterna fungerar. För en översikt på högre nivå över genomsnittliga användningsmått de senaste sju dagarna kan du använda administratörsportalen. Mer information om övervakning i portalen finns i [Övervaka Premium-kapaciteter i administratörsportalen](service-admin-premium-monitor-portal.md).

Appen uppdateras regelbundet med nya funktioner. Se till att du kör den senaste versionen. När en ny version blir tillgänglig får du ett [meddelande](../connect-data/service-template-apps-install-distribute.md#update-a-template-app).

> [!IMPORTANT]
> Om din Power BI Premium-kapacitet har hög resursanvändning, som medför prestanda- och tillförlitlighetsproblem, kan du få e-postmeddelanden för att identifiera och lösa problemet. Detta kan vara ett effektivt sätt att felsöka överbelastade kapaciteter. Mer information finns i [meddelanden om kapacitet och tillförlitlighet](service-interruption-notifications.md#capacity-and-reliability-notifications).

## <a name="install-the-app"></a>Installera appen

Information om hur du installerar appen och ansluter till data finns i [Ansluta till Power BI Premium Capacity Metrics](../connect-data/service-connect-to-pbi-premium-capacity-metrics.md). Du kan också [gå direkt till appen](https://go.microsoft.com/fwlink/?linkid=2114036).

## <a name="get-app-refresh-history"></a>Hämta uppdateringshistorik för appen

Så här kontrollerar du den senaste uppdateringen för appen Premium Capacity Metrics:

1. Gå till arbetsytan som installerades med appen.

   ![Gå till app-arbetsytan](media/service-admin-premium-monitor-capacity/settings-refresh-history.png)

1. Klicka på knappen **Schemalägg uppdatering** på datauppsättningsraden.

   ![Knappen Schemalägg uppdatering](media/service-admin-premium-monitor-capacity/schedule-refresh.png)

   Den senaste uppdateringen visas. Klicka på **Uppdateringshistorik** om du vill se schemalagda och uppdateringar och på begäran-uppdateringar.

   ![Senaste uppdatering](media/service-admin-premium-monitor-capacity/settings-last-refresh.png)

## <a name="monitor-capacities-with-the-app"></a>Övervaka funktioner med appen

Nu när du har installerat appen kan du se mått för kapaciteterna i din organisation. Appen innehåller en instrumentpanel med måttsammanfattningar och detaljerade måttrapporter.

### <a name="dashboard"></a>Instrumentpanel

Se en instrumentpanel som sammanfattar viktiga mått för kapaciteter som du är administratör för, i **Instrumentpaneler** så klickar du på **Power BI Premium-kapacitetsmått**. En instrumentpanel visas.

![Instrumentpanelen med mätvärden för app](media/service-admin-premium-monitor-capacity/app-dashboard.png)

Instrumentpanelen innehåller följande mått:

#### <a name="top"></a>Överkant

| Metric | Beskrivning |
| --- | --- |
| Version | Appversion. | 
| Kapacitet | Antal kapaciteter som du är administratör för. | 
| Arbetsytor | Antal arbetsytor i dina kapaciteter som rapporterar mått.|
|||

#### <a name="system-summary"></a>Systemöversikt

| Metric | Beskrivning |
| --- | --- |
| Högsta utnyttjandekapacitet av processor | Kapacitet med det högsta antalet gånger som processorn översteg 80 % av tröskelvärdena under de senaste sju dagarna. |
| Högsta utnyttjandeantal för processorn | Antal gånger som processorn av den namngivna kapaciteten översteg 80 % av tröskelvärdena under de senaste sju dagarna. | 
| Högsta utnyttjandekapacitet för minne | Kapacitet med det maximala antalet gånger som den högsta minnesgränsen uppnåddes de senaste sju dagarna, uppdelat i treminuters bucketar.  |
| Antal max minnesutnyttjande| Antal gånger som den namngivna kapaciteten uppnådde den högsta minnesgränsen de senaste sju dagarna, uppdelat i treminuters bucketar. |
|||

#### <a name="dataset-summary"></a>Översikt över datamängd

| Metric | Beskrivning |
| --- | --- |
| Datauppsättningar | Totalt antal datauppsättningar för alla arbetsytor i dina kapaciteter.|
| Genomsnittlig storlek på datauppsättningarna (MB) | Genomsnittlig storlek för datauppsättningar för alla arbetsytor i dina kapaciteter.|  
| Genomsnittligt antal inlästa datauppsättningar | Genomsnittligt antal datauppsättningar som lästs in i minnet. |  
| Datauppsättningar – genomsnitt aktiva datauppsättning (%)| Genomsnitt aktiva datauppsättningar under de senaste sju dagarna. En datauppsättning definieras som aktiv om användaren har interagerat med den de senaste tre minuterna. |
| CPU – datauppsättningar max (%)| Max CPU-förbrukning efter datauppsättningens arbetsbelastning under de senaste sju dagarna. |
| CPU – datauppsättningar genomsnitt (%)| Genomsnittlig CPU-förbrukning efter datauppsättningens arbetsbelastning de senaste sju dagarna. |
| Minne – datauppsättningar genomsnitt (%) | Genomsnittlig minnesförbrukning efter datauppsättningens arbetsbelastning de senaste sju dagarna. |
| Minne – datauppsättningar max (GB) | Max minnesförbrukning efter datauppsättningens arbetsbelastning de senaste sju dagarna.|
| Datauppsättningar borttagna | Totalt antal datauppsättningar som tagits bort på grund av minnestryck. |
| DirectQuery/Live högt utnyttjande antal| Antal gånger som DirectQuery/Live-anslutningar har överskridit 80 % av tröskelvärdena under de senaste sju dagarna, uppdelat på treminuters bucketar. |
| DirectQuery/Live max utnyttjande antal| De flesta gånger som DirectQuery/Live-anslutningarna överskridit 80 % under de senaste sju dagarna, uppdelat på entimmes bucketar. |
| DirectQuery/Live max högt utnyttjande | Det maximala antalet gånger som DirectQuery/Live-anslutningar har överskridit 80 % av tröskelvärdena under de senaste sju dagarna, uppdelat på treminuters bucketar.|
| DirectQuery/Live tid när max inträffade | Tid i UTC då DirectQuery/Live-anslutningar överskred 80 % flest gånger under en timme. |
| Uppdateringar totalt | Totalt antal uppdateringar under de senaste sju dagarna. |
| Uppdateringstillförlitlighet (%) | Antal lyckade uppdateringar delat på det totala antalet uppdateringar under de senaste sju dagarna. |
| Genomsnittlig varaktighet för uppdateringar (minuter) | Genomsnittlig mängd tid för att slutföra uppdateringen. |
| Genomsnittlig väntetid för uppdateringar (minuter)| Genomsnittlig tid innan uppdateringen startar. |
| Totalt antal frågor |  Totalt antal frågor som körts under de senaste sju dagarna. |
| Frågor totalt vänteantal | Totalt antal frågor som var tvungen att vänta innan de kördes. |
| Genomsnittlig varaktighet för frågor (ms) | Genomsnittlig tid det tar att slutföra frågor. |
| Genomsnittlig väntetid för frågor (ms) | Genomsnittlig tid som frågor väntade på systemresurser innan de kördes. |
|||

#### <a name="dataflow-summary"></a>Översikt över dataflöde

| Metric | Beskrivning |
| --- | --- |
| Dataflöden |  Totalt antal dataflöden för alla arbetsytor i dina kapaciteter.|
| Uppdateringar totalt | Totalt antal uppdateringar under de senaste sju dagarna.|  
| Genomsnittlig varaktighet för uppdateringar (minuter) | Den tid det tar att slutföra uppdateringen. |
| Genomsnittliga väntetider för uppdateringar (minuter) | Fördröjningen mellan den schemalagda tiden och den faktiska starttiden för uppdateringen.|
| CPU – dataflöden max (%) | Max CPU-förbrukning efter dataflödenas arbetsbelastning under de senaste sju dagarna. |
| CPU – dataflöden genomsnitt (%) | Genomsnittlig CPU-förbrukning efter dataflödenas arbetsbelastning under de senaste sju dagarna. |
| Minne – dataflöden max (GB) | Max minnesförbrukning efter dataflödenas arbetsbelastning under de senaste sju dagarna. |
| Minne – dataflöden genomsnitt (GB) | Genomsnittlig minnesförbrukning efter dataflödenas arbetsbelastning under de senaste sju dagarna. |
|||

#### <a name="paginated-report-summary"></a>Översikt över sidnumrerade rapporter

| Metric | Beskrivning |
| --- | --- |
| Sidnumrerade rapporter |  Totalt antal sidnumrerade rapporter för alla arbetsytor i dina kapaciteter. |
| Totalt antal visningar | Totalt antal gånger som alla rapporter har visats av användare. | 
| Totalt antal rader | Totalt antal rader med data i alla rapporter.|
| Total tid | Total tid det tar för alla faser (datahämtning, bearbetning och återgivning) för alla rapporter, i millisekunder. |
| CPU – sidnumrerade rapporter max (%) | Max CPU-förbrukning efter den sidnumrerade rapportens arbetsbelastning de senaste sju dagarna. |
| CPU – sidnumrerade rapporter genomsnitt (%) | Genomsnittlig CPU-förbrukning efter den sidnumrerade rapportens arbetsbelastning de senaste sju dagarna. |
| Minne – sidnumrerade rapporter max (GB) | Max minnesförbrukning efter den sidnumrerade rapportens arbetsbelastning de senaste sju dagarna. |
| Minne – sidnumrerade rapporter genomsnittligt (GB) | Genomsnittlig minnesförbrukning efter den sidnumrerade rapportens arbetsbelastning de senaste sju dagarna. |
|||

#### <a name="ai-summary"></a>AI-sammanfattning

| Metric | Beskrivning |
| --- | --- |
| Körning av AI-funktion | Totalt antal körningar under de senaste sju dagarna. |
| Tillförlitlighet för AI-funktionskörning (%) | Antal lyckade körningar delat på det totala antalet körningar under de senaste sju dagarna. |
| Max. CPU (%)| Maximal CPU-förbrukning efter AI-arbetsbelastning under de senaste sju dagarna. |
| Max. minne (GB) | Maximal minnesförbrukning efter AI-arbetsbelastning under de senaste sju dagarna.|
| Max. väntetid för AI-funktionskörning (ms) | Maximal tid innan körning startas. |
| Genomsnittlig väntetid för AI-funktionskörning (ms)| Genomsnittlig tid innan körning startas. |
| Maximal varaktighet för AI-funktionskörning (ms) | Maximal tid för att körning ska slutföras. |
| Genomsnittlig varaktighet för AI-funktionskörning (ms)| Genomsnittlig tid för att körning ska slutföras. |
| | |

### <a name="reports"></a>Rapporter

Rapporter ger mer detaljerade mätvärden. Visa rapporter för kapaciteter som du är administratör för genom att gå till **Rapporter** och klicka på **Power BI Premium-kapacitetsmått**. Eller så klickar du på en måttcell från instrumentpanelen för att gå till den underliggande rapporten. 

Längst ned i rapporten finns det fem *flikar*:

[**Datauppsättningar**](#datasets) – Innehåller detaljerade mätvärden om hälsotillståndet för Power BI-datauppsättningarna i dina kapaciteter.
[**Sidnumrerade rapporter**](#paginated-reports) – Innehåller detaljerade mätvärden om hälsotillståndet för de sidnumrerade rapporterna i dina kapaciteter.
[**Dataflöden**](#dataflows) – Innehåller detaljerade uppdateringsmätvärden för dataflöden i dina kapaciteter.
[**AI**](#ai) – Innehåller detaljerade mätvärden om hälsotillståndet för de AI-funktioner som används i din kapacitet.
[**Resursförbrukning**](#resource-consumption) – Innehåller detaljerade resursmått, inklusive minne och hög CPU-användning.
[**ID:n och info**](#ids-and-info) – Namn, ID:n och ägare för kapaciteter, arbetsytor och arbetsbelastningar.

Varje flik öppnar en sida där du kan filtrera mått efter kapacitet och datumintervall. Om inga filter har markerats använder rapporten standardinställningarna för att visa den senaste veckans mått för alla kapaciteter som rapporterar mått. 

### <a name="datasets"></a>Datauppsättningar

Sidan Datauppsättningar har olika *områden* som inkluderar **Uppdateringar**, **Frågevaraktigheter**, **Frågeväntetid** och **Datauppsättningar**. Använd knapparna överst på sidan för att gå till de olika områdena.

#### <a name="refreshes-area"></a>Området Uppdaterar

| Rapportavsnitt | Mått |
| --- | --- |
| Uppdaterar |  Totalt antal: Totalt antal uppdateringar för varje datauppsättning.<br>  Tillförlitlighet: Den procentandel uppdateringar som slutfördes för varje datamängd.<br>  Genomsnittlig väntetid: Den genomsnittliga fördröjningen mellan schemalagda tid och starttid för en uppdatering av datauppsättningen, i minuter.<br>  Maximal väntetid: Den maximala väntetiden för datauppsättningen, i minuter.<br>  Genomsnittlig varaktighet: Den genomsnittliga varaktigheten för uppdateringen för datauppsättningen, i minuter.<br>  Maximal varaktighet: Varaktigheten för den långvarigaste uppdateringen av datauppsättningen, i minuter. |
| De 5 viktigaste datauppsättningarna efter genomsnittlig varaktighet (minuter) |  De fem datauppsättningarna med längst genomsnittlig uppdateringsvaraktighet, i minuter. |
| De viktigaste 5 datauppsättningarna efter genomsnittlig väntetid (minuter) |  De fem datauppsättningarna med den längsta genomsnittliga uppdateringsväntetiden, i minuter. |
| Antal uppdateringar och minnesförbrukning per timma (GB) |  Genomförda, misslyckade och minnesförbrukning, uppdelade i entimmes bucketar, rapporterade i UTC-tid. |
| Genomsnittlig uppdateringsväntetid varje timme (minuter) |  Den genomsnittliga uppdateringsväntetiden, uppdelat i entimmes bucketar, rapporterad i UTC-tid. Många toppar med långa uppdateringsväntetider tyder på att kapaciteten körs för hårt. |
|  |  |

#### <a name="query-durations-area"></a>Frågevaraktighetsområde

| Rapportavsnitt | Mått |
| --- | --- |
| Frågevaraktighet |  Data i det här avsnittet är indelade efter datauppsättningar, arbetsytor och timbucketar under de senaste sju dagarna.<br>  Totalt: Det totala antal frågor som körts för datauppsättningen.<br>  Genomsnitt: Den genomsnittliga frågevaraktigheten för datauppsättningen, mätt i millisekunder<br>  Max: Varaktigheten för den långvarigaste frågan i datauppsättningen, i millisekunder.|
| Frågevaraktighetsfördelning |  Frågevaraktighetens histogram bucketeras efter frågevaraktighet (i millisekunder) i följande kategorier: intervall på < = 30 ms, 30-100 ms, 100-300 ms, 300 ms-1 sek, 1-3 sek, 3-10 sek, 10-30 sek och > 30 sek. Lång frågevaraktighet och långa väntetider är en tydlig indikation på kapaciteten utsätts för mycket hög belastning. Det kan också innebära att en enskild datauppsättning orsakar problem och ytterligare utredning krävs. |
| De 5 främsta datauppsättningarna efter genomsnittlig varaktighet |  De fem datauppsättningarna med den längsta genomsnittliga frågevaraktigheten, i millisekunder. |
| Frågevaraktighetsfördelning per timme |  Antal frågor och genomsnittlig varaktighet (i millisekunder) kontra minnesanvändning i GB, uppdelat i entimmes bucketar, rapporterade i UTC-tid. |
| DirectQuery/Live-anslutningar (> 80 % utnyttjande) |  Tiderna då en DirectQuery eller Live-anslutning överskred 80 % CPU-användning, uppdelat i entimmes bucketar, rapporterat i UTC-tid. |
|  |  |

#### <a name="query-waits-area"></a>Frågeväntansområde

| Rapportavsnitt | Mått |
| --- | --- |
| Frågeväntetider |  Data i det här avsnittet är indelade efter datauppsättningar, arbetsytor och timbucketar under de senaste sju dagarna.<br>  Totalt: Det totala antal frågor som körts för datauppsättningen.<br>  Antal väntande: Det antal frågor i den datauppsättning som väntade på systemresurser innan körningen startades.<br>  Genomsnitt: Den genomsnittliga frågeväntetiden för datauppsättningen, i millisekunder.<br>  Max: Varaktigheten för den längst väntande frågan i datauppsättningen, i millisekunder.|
| De 5 främsta datauppsättningarna efter genomsnittlig väntetid |  De fem datauppsättningarna med den längsta genomsnittliga väntetiden för att börja köra en fråga, i millisekunder. |
| Väntetidsfördelningar |  Histogrammet för frågevaraktighet bucketeras efter frågevaraktigheter (i millisekunder) i följande kategorier: intervall på <= 50 ms , 50-100 ms , 100-200 ms , 200-400 ms 400 ms-1 sek, 1-5 s och > 5 s. |
| Väntetidsfördelningar per timme |  Antal väntande frågor och genomsnittlig väntetid (i millisekunder) jämfört med minnesanvändningen i GB, uppdelat i entimmes bucketar rapporterade i UTC-tid. |
|  |  |

#### <a name="datasets-area"></a>Området Datamängder

| **Rapportavsnitt** | **Mått** |
| --- | --- |
| Datauppsättningsstorlekar  |  Maxstorlek: Maxstorleken för datauppsättningen i MB för perioden som visas. |
| Antal borttagna datauppsättningar |  Totalt: Det totala antalet *avlägsnade* datauppsättningar för respektive kapacitet. När en kapacitet drabbas av minnesbelastning avlägsnar noden en eller flera datauppsättningar från minnet. Datamängder som är inaktiva (utan frågor/uppdateringsåtgärder som körs för tillfället) avlägsnas först. Avlägsnandeordern baseras sedan på ett mått på ”minst nyligen använd” (LRU, Least Recently Used).|
| Inlästa datauppsättningar per timme |  Antal datauppsättningar som lästes in i minnet jämfört med minnesförbrukning i GB, uppdelat i entimmes bucketar, rapporterat i UTC-tid. |
| Antal borttagna datauppsättningar och minnesförbrukning per timme |  Borttagna datauppsättningar jämfört med minnesförbrukning i GB, uppdelat i entimmes bucketar, rapporterat i UTC-tid. |
| Procent förbrukat minne |  Det totala antalet aktiva datauppsättningar i minnet som procent av det totala minnet. Delta mellan aktiva och alla definierade datauppsättningar som kan avlägsnas. Visas per timme, för de sju föregående dagarna. |
|  |  |

### <a name="paginated-reports"></a>Sidnumrerade rapporter

| **Rapportavsnitt** | **Mått** |
| --- | --- |
| Övergripande användning |  Totalt antal visningar: Antalet gånger som rapporten har visats av användare.<br>  Radantal: Antalet rader data i rapporten.<br>  Hämtning (medelvärde): Den genomsnittliga tid det tar att hämta data för rapporten, uttryckt i millisekunder. Långa varaktigheter kan indikera långsamma frågor eller andra problem med datakällan. <br>  Bearbetning (medelvärde): Den genomsnittliga tid det tar att bearbeta data för en rapport, i millisekunder.<br> Återgivning (medelvärde): Den genomsnittliga tid det tar att återge en rapport i webbläsaren, i millisekunder.<br>  Total tid: Den tid det tar för alla faser i en rapport, i millisekunder. |
| De 5 främsta rapporterna efter genomsnittlig datahämtningstid |  De fem rapporterna med den längsta genomsnittliga datahämtningstiden, i millisekunder. |
| De 5 främsta rapporterna efter genomsnittlig rapportbearbetningstid |  De fem rapporterna med den längsta genomsnittliga rapportbearbetningstiden, i millisekunder. |
| Resultat per timma |  Genomförda, misslyckade och minnesförbrukning, uppdelade i entimmes bucketar, rapporterade i UTC-tid. |
| Varaktighet per timma |  Datahämtning jämfört med tiden för bearbetning och återgivning, uppdelat i entimmes bucketar, rapporterat i UTC-tid. |
|  |  |

### <a name="dataflows"></a>Dataflöden

| **Rapportavsnitt** | **Mått** |
| --- | --- |
| Uppdaterar |  Totalt: Totalt antal uppdateringar för varje dataflöde.<br>  Tillförlitlighet: Den procentandel uppdateringar som slutfördes för varje dataflöde.<br>  Genomsnittlig väntetid: Den genomsnittliga fördröjningen mellan schemalagd tid och start av en uppdatering av dataflödet, i minuter.<br>  Maximal väntetid: Maximal väntetid för dataflödet, i minuter.<br>  Genomsnittlig varaktighet: Genomsnittlig varaktighet för uppdatering för dataflödet, i minuter.<br>  Maximal varaktighet: Varaktigheten för den långvarigaste uppdateringen av dataflödet, i minuter. |
| De 5 viktigaste dataflödena efter genomsnittlig uppdateringsvaraktighet |  De fem dataflöden med den längsta genomsnittliga uppdateringsvaraktigheten, i minuter. |
| De 5 viktigaste dataflödena efter genomsnittlig väntetid |  De fem dataflödena med den längsta genomsnittliga uppdateringsväntetiden, i minuter. |
| Genomsnittlig uppdateringsväntetid uppdelad i timmar |  Den genomsnittliga uppdateringsväntetiden, uppdelat i entimmes bucketar, rapporterad i UTC-tid. Många toppar med långa uppdateringsväntetider tyder på att kapaciteten körs för hårt. |
| Antal uppdateringar och minnesförbrukning per timma |  Genomförda, misslyckade och minnesförbrukning, uppdelade i entimmes bucketar, rapporterade i UTC-tid. |
|  |  |

### <a name="ai"></a>AI

| **Rapportavsnitt** | **Mått** |
| --- | --- |
| AI-minnesförbrukning | Minnesförbrukning i GB, uppdelat i entimmes bucketar, rapporterat i UTC-tid. |
| Timbaserad AI-funktionskörning och genomsnittlig väntetid | AI-körningar och genomsnittlig väntetid i millisekunder, uppdelat i entimmes bucketar, rapporterat i UTC-tid. |
| Total användning | Totalt antal: Antalet AI-funktioner på en arbetsyta eller i ett dataflöde. <br> Systemtillförlitlighet: Den procentandel körningar som slutfördes.<br> Genomsn. Väntetid: Den genomsnittliga fördröjningen mellan schemalagda tid och starttid för en det körning, i millisekunder.<br> Maximal väntetid: Maximal väntetid, i millisekunder.<br> Genomsn. Varaktighet: Den genomsnittliga varaktigheten för en körning, i millisekunder.<br> Maximal varaktighet: Varaktigheten för den långvarigaste körningen, i millisekunder.<br> Genomsnittlig total storlek: Den genomsnittliga storleken i byte för indata och utdata för AI-funktionen. |
| | |

### <a name="resource-consumption"></a>Resursförbrukning

| **Rapportavsnitt** | **Mått** |
| --- | --- |
| CPU-förbrukning |  Maximal CPU-förbrukning per timme, beräknat på arbetsbelastning som procentandel av total CPU-kapacitet. Visas per timme, för de sju föregående dagarna. |
| Minnesförbrukning |  Maximal minnesförbrukning per timme, i GB per arbetsbelastning (heldragna linjer) och med arbetsbelastningsgränser (streckad linje) överst. Visas per timme, för de sju föregående dagarna. |
|  |  |

### <a name="ids-and-info"></a>ID:n och info

Fliken **ID:n och information** innehåller områden för **Kapaciteter**, **Arbetsytor**, **Datauppsättningar**, **Sidnumrerade rapporter**, och **Dataflöden**.

#### <a name="capacities-area"></a>Kapaciteter-området

| Rapportavsnitt | Mått |
| --- | --- |
| SKU och information för arbetsbelastning | Inställningar för SKU och arbetsbelastning för kapaciteten. |
| Administratörer | Namnen på administratörerna för kapaciteten. |
|||

#### <a name="workspaces-area"></a>Arbetsytor-området

| Rapportavsnitt | Mått |
| --- | --- |
| Arbetsytor | Namn och ID:n för alla arbetsytor. |
|||

#### <a name="datasets-area"></a>Området Datamängder

| Rapportavsnitt | Mått |
| --- | --- |
| Datauppsättningar | Arbetsytenamn och ID:n för alla datauppsättningar. |
|||

#### <a name="paginated-reports-area"></a>Sidnumrerade rapporter-området

| Rapportavsnitt | Mått |
| --- | --- |
| Sidnumrerade rapporter | Namn, arbetsytenamn och ID:n för alla sidnumrerade rapporter. |
|||

#### <a name="dataflows-area"></a>Dataflöden-området

| Rapportavsnitt | Mått |
| --- | --- |
| Dataflöden | Dataflödesnamn, arbetsytenamn och ID:n för alla dataflöden. |
|||

## <a name="monitor-power-bi-embedded-capacity"></a>Övervaka Power BI Embedded-kapacitet

Du kan använda appen Power BI Premium Capacity Metrics för att övervaka *A SKU*-kapaciteter i Power BI Embedded. De kapaciteterna visas i rapporten så länge du är administratör för kapaciteten. Uppdatering av rapporten misslyckas dock såvida inte du ger vissa behörigheter till Power BI för dina A-SKU:

1. Öppna kapaciteten i Azure Portal.

1. Klicka på **Åtkomstkontroll (IAM)** och lägg därefter till **Power BI Premium**-appen till läsarrollen. Om det inte går att hitta appen efter namn kan du även lägga till den efter klientidentifierare: `cb4dc29f-0bf4-402a-8b30-7511498ed654`.

    ![Behörigheter för Power BI Embedded](media/service-admin-premium-monitor-capacity/embedded-permissions.png)

> [!NOTE]
> Du kan övervaka kapacitetsförbrukningen för Power BI Embedded i appen eller Azure Portal, men inte i Power BI-administratörsportalen.


## <a name="next-steps"></a>Nästa steg

> [!div class="nextstepaction"]
> [Optimera Power BI Premium-kapaciteter](service-premium-capacity-optimize.md)
