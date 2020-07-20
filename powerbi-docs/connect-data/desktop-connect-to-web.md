---
title: Ansluta till en webbsida från Power BI Desktop
description: Anslut enkelt till och använd webbdata i Power BI Desktop
author: davidiseminger
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: how-to
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 618e2acb415d72870fd599142775720955e8ba88
ms.sourcegitcommit: c83146ad008ce13bf3289de9b76c507be2c330aa
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/10/2020
ms.locfileid: "86214711"
---
# <a name="connect-to-webpages-from-power-bi-desktop"></a>Ansluta till webbsidor från Power BI Desktop

Du kan ansluta till en webbsida och importera data från den till Power BI Desktop för användning i visuella objekt och i datamodeller.

I **Power BI Desktop** väljer du **Hämta data > Webb** från fliken Start i menyfliksområdet.

![Skärmbild av Power BI Desktop med valet Webb.](media/desktop-connect-to-web/connect-to-web_1.png)

En dialogruta visas som frågar om URL-adressen till sidan som du vill importera data från.

![Skärmbild av dialogrutan Webb med fältet Webbadress.](media/desktop-connect-to-web/connect-to-web_2.png)

När du har skrivit (eller klistrat in) URL:en, väljer du **OK**. Power BI Desktop ansluter till sidan och sedan visas sidans tillgängliga data i fönstret **Navigator**. När du väljer ett av de tillgängliga dataelementen, till exempel en tabell över hela sidan, visar fönstret **Navigator** en förhandsgranskning av dessa data på höger sida av fönstret.

![Skärmbild av dialogrutan Navigator med en förhandsgranskning av den valda tabellens data.](media/desktop-connect-to-web/connect-to-web_3.png)

Du kan välja knappen **Redigera**, som startar **Frågeredigeraren** där du kan utforma och transformera data från OData-feeden innan du importerar dem till Power BI Desktop. Eller så kan du välja knappen **Hämta** och importera alla dataelement som du har valt i den vänstra rutan.

När vi väljer **Hämta** importerar Power BI Desktop de markerade objekten och gör dem tillgängliga i fönstret **Fält** tillgängliga på höger sida av vyn Rapporter i Power BI Desktop.

![Skärmbild av fönstret Fält och en lista med valda tabeller.](media/desktop-connect-to-web/connect-to-web_4.png)

Svårare än så är det inte att ansluta till en webbplats och överföra dess data till Power BI Desktop.

Därifrån kan du dra fält till rapportarbetsytan och alla visuella objekt som du vill skapa. Du kan också använda data från webbplatsen precis som med andra data – du kan forma dem, skapa relationer mellan dem och andra datakällor i din modell och i övrigt göra vad du vill för att skapa den Power BI-rapporten du vill ha.

Om du vill lära dig mer om att ansluta till en webbplats, kan du läsa [Komma igång-guiden för Power BI Desktop](../fundamentals/desktop-getting-started.md).

## <a name="next-steps"></a>Nästa steg
Det finns alla möjliga sorters data du kan ansluta till med Power BI Desktop. Kolla in följande resurser för mer information om datakällor:

* [Datakällor i Power BI Desktop](desktop-data-sources.md)
* [Forma och kombinera data i Power BI Desktop](desktop-shape-and-combine-data.md)
* [Anslut till Excel-arbetsböcker i Power BI Desktop](desktop-connect-excel.md)   
* [Anslut till CSV-filer i Power BI Desktop](desktop-connect-csv.md)   
* [Ange data direkt i Power BI Desktop](desktop-enter-data-directly-into-desktop.md)   
