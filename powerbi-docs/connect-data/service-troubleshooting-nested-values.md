---
title: Felsöka kapslade värden som returneras som text i Power BI-tjänsten
description: Lär dig mer om hur du åtgärdar kapslade värden som konverteras till strängar när du använder fel sekretessinställningar för datakällan
author: cpopell
ms.reviewer: ''
ms.custom: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: troubleshooting
ms.date: 6/4/2019
ms.author: gepopell
LocalizationGroup: Reports
ms.openlocfilehash: ab40ca9c415dacf52f4d82eb2c157d57aef92f93
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83332784"
---
# <a name="troubleshooting-nested-values-returned-as-text-in-power-bi-service"></a>Felsöka kapslade värden som returneras som text i Power BI-tjänsten

## <a name="cause"></a>Orsak

Tidigare har det kunnat uppstå fall där en Power BI-rapport uppdateras korrekt på skrivbordet men inte i Power BI-tjänsten, och då har felet ”Det går inte att konvertera värdet ’[Table]’ till typen Tabell”. En av orsakerna till det här felet är att när brandväggen för datasekretess buffrar en datakälla så konverteras kapslade, icke-skalära värden (till exempel tabeller, poster, listor och funktioner) automatiskt till textvärden (till exempel ”[Table]” eller ”[Record]”).

Nu när Power BI-tjänsten har stöd för att ställa in sekretessnivån (eller att helt inaktivera brandväggen) kan du undvika sådana fel genom att [konfigurera sekretessinställningarna för datakällan](https://powerbi.microsoft.com/blog/privacy-levels-for-cloud-data-sources/) i Power BI-tjänsten så att den inte är privat.

Från och med juni visas följande fel i Power BI när brandväggen buffrar en kapslad tabell/post/lista eller liknande, snarare än att de här värdena konverteras till text i bakgrunden: 

`We cannot return a value of type Table in this context`

## <a name="effect-on-loadrefresh"></a>Effekt vid inläsning/uppdatering

Även om ändringen motiveras av brandväggsbuffringen så påverkas även inläsning/uppdatering. För att kunna åtgärda beteendet vid brandväggsbuffring behövde vi även ändra beteendet vid inläsning av kapslade tabeller/poster och liknande till Power BI-modellen och Excel-datamodellen i PQ för Excel. Tidigare så lästes kapslade tabeller/poster och liknande in som textvärden (som ”[Table]” eller ”[Record]”). Nu behandlas de som fel, vilket genererar ett nullvärde i den inlästa tabellen och att felräknaren i inläsningsresultatet ökar ett steg.

Eftersom de här felen endast sker under inläsning/uppdatering visas de inte i Power Query Editor.

### <a name="before"></a>Före

- Inläsning/uppdatering utan fel
- Den inlästa tabellen innehåller ”[Table]”, ”[Record]” osv.
 

### <a name="after"></a>Efter

- Inläsning/uppdatering med fel
- Den inlästa tabellen innehåller NULL-värden (istället för ”[Table]”, ”[Record]” osv.)
 

## <a name="resolution"></a>Lösning

Läser du in en kolumn som innehåller icke-skalära värden (som tabeller, listor eller poster)?
I så fall ska du kunna eliminera felen genom att ta bort kolumnen.
Om du inte kan ta bort kolumnen ska du kunna replikera det gamla beteendet genom att lägga till en anpassad kolumn och använda logik som i följande exempel:

`if [MyColumn] is table then "[Table]" else if [MyColumn] is record then "[Record]" else if [MyColumn] is list then "[List]" else if [MyColumn] is function then "[Function]" else [MyColumn]`

Uppstår felet i Power BI Desktop om du ställer in alla sekretessinställningar för datakällan som Privat?
I så fall ska du kunna lösa problemet genom att [konfigurera sekretessinställningarna för datakällan](https://powerbi.microsoft.com/blog/privacy-levels-for-cloud-data-sources/) i Power BI-tjänsten som icke privata.
