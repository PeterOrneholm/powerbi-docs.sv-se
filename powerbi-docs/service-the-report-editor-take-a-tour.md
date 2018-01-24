---
title: Rapportredigeraren... Ta en rundtur
description: Rapportredigeraren... Ta en rundtur.
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
featuredvideoid: IkJda4O7oGs
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/30/2017
ms.author: mihart
ms.openlocfilehash: e5ee6db22fe0fa7fd1e61ebbfb7dbee9d3458159
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/13/2017
---
# <a name="the-report-editortake-a-tour"></a>Rapportredigeraren... Ta en rundtur
Rapportredigeraren i Power BI-tjänsten och rapportredigeraren i Power BI Desktop liknar varandra mycket. Videon visar rapportredigeraren i Power BI Desktop och den här artikeln beskriver rapportredigeraren i Power BI-tjänsten. 

<iframe width="560" height="315" src="https://www.youtube.com/embed/IkJda4O7oGs" frameborder="0" allowfullscreen></iframe>

I Power BI-tjänsten är *rapportredigeraren* endast tillgänglig i [redigeringsvyn](service-reading-view-and-editing-view.md). Om du vill öppna en rapport i redigeringsvyn måste du vara rapportägare.

Power BI-Rapportredigeraren består av 3 delar:  

1. Fönster för**fält**, **visualiseringar** och **filter**
2. övre navigeringsfälten    
3. rapportarbetsytan     

![](media/service-the-report-editor-take-a-tour/power-bi-report-canvas.png)

## <a name="1-the-report-editor-panes"></a>1. Rapportredigerarens fönster
![](media/service-the-report-editor-take-a-tour/power-bi-report-panes.png)

Det finns 3 synliga fönster första gången som du öppnar en rapport: visualiseringar, filter och fält. Fönstren till vänster, visualiseringar och filter, styr visualiseringarnas utseende, t.ex. typ, färger, filtrering, formatering.  Och fönstret till höger, fält, hanterar de underliggande data som används i visualiseringarna. 

Innehållet som visas i rapportredigeraren varierar beroende på vilka val du gör på rapportarbetsytan.  När du t.ex. väljer ett enskilt visuellt objekt, 

|  |  |
| --- | --- |
| ![](media/service-the-report-editor-take-a-tour/power-bi-panes.png) |<ul><li>Överst i visualiseringsfönstret identifieras det visuella objektets typ. I det här exemplet är det ett klustrat stapeldiagram.<br><br></li> <li>Längst ned i visualiseringsfönstret (du kanske måste rulla nedåt) visas de fält som används i det visuella objektet. Det här diagrammet använder FiscalMonth, DistrictManager och Total Sales Variance. <br><br></li><li>Fönstret Filter (du kanske måste rulla nedåt) visar eventuella filter som har tillämpats. <br><br></li><li>Fönstret Fält innehåller de tabeller som är tillgängliga, och om du expanderar ett tabellnamn visas fälten som utgör tabellen. Ett gult teckensnitt indikerar att minst ett fält från tabellen används i visualiseringen.<br><br></li><li>![](media/service-the-report-editor-take-a-tour/power-bi-paint-roller-icon.png)Välj rollerikonen om du vill visa formateringsfönstret för den valda visualiseringen.<br><br></li><li>![](media/service-the-report-editor-take-a-tour/power-bi-magnifying-icon.png)Välj förstoringsglasikonen om du vill visa analysfönstret.</ul> |
|  | |

## <a name="the-visualizations-pane-from-top-to-bottom"></a>Visualiseringsfönstret (uppifrån och ned)
![](media/service-the-report-editor-take-a-tour/selectviz.png)

Det är här du väljer visualiseringstyp. De små bilderna kallas *mallar*. I bilden ovan har det klustrade stapeldiagrammet valts. Om du inte väljer visualiseringstyp först, men i stället börja skapa en visualisering genom att välja fält, så väljer Power BI en visualiseringstyp åt dig. Du kan behålla den visualiseringstyp som Power BI har valt, eller så ändrar du typ genom att välja en annan mall. Byt så många gånger du vill, så att du verkligen hittar den visualiseringstyp som representerar dina data på bästa sätt.

### <a name="manage-the-fields-used-in-your-visual"></a>Hantera det fält som används i ditt visuella objekt.
![](media/service-the-report-editor-take-a-tour/power-bi-field-list.png)

De bucketar (kallas ibland *källor*) som visas i det här fönstret varierar beroende på vilken typ av visualisering du har valt.  Om du t.ex. har valt ett stapeldiagram visas bucketar för: värden, axel och förklaring. När du markerar ett fält eller drar det till arbetsytan, så lägger Power BI till det fältet i någon av bucketarna.  Du kan också dra fält från fältlistan direkt till bucketarna.  Vissa bucketar är begränsade till vissa datatyper.  **Värden** accepterar t.ex. inte icke-numeriska fält. Om du drar ett **employeename**-fält till bucketen **Values** så ändrar Power BI den till **antal employeename**.

### <a name="remove-a-field"></a>Ta bort ett fält
Om du vill ta bort ett fält från visualiseringen så markera **X** till höger om fältnamnet.

![](media/service-the-report-editor-take-a-tour/deletefield.png)

Mer information finns i [Lägga till visualiseringar i en Power BI-rapport](power-bi-report-add-visualizations-i.md)

### <a name="format-your-visuals"></a>Formatera dina visuella objekt
Öppna formatfönstret genom att välja färgrollerikonen. Vilket alternativ som är tillgängligt beror på vilken visualiseringstyp som har valts.

![](media/service-the-report-editor-take-a-tour/power-bi-formatting.png)

Formateringsmöjligheterna är nästan oändliga.  Om du vill veta mer, så utforska på egen hand eller läs följande artiklar:

* [Anpassa visualiseringens rubrik, bakgrund och förklaring](power-bi-visualization-customize-title-background-and-legend.md)
* [Färgformatering](service-getting-started-with-color-formatting-and-axis-properties.md)
* [Anpassa egenskaper för x-axeln och y-axeln](power-bi-visualization-customize-x-axis-and-y-axis.md)

### <a name="add-analytics-to-your-visualizations"></a>Lägg till analys i din visualiseringar
Välj förstoringsglasikonen om du vill visa analysfönstret. Vilket alternativ som är tillgängligt beror på vilken visualiseringstyp som har valts.

![](media/service-the-report-editor-take-a-tour/power-bi-analytics.png)    
Med fönstret Analytics i Power BI-tjänsten kan du lägga till dynamiska referensrader i visualiseringar och ange fokus för viktiga trender eller insikter. Läs mer i [Fönstret Analytics i Power BI-tjänsten](service-analytics-pane.md) eller [Fönstret Analytics i Power BI Desktop](desktop-analytics-pane.md).

- - -
## <a name="the-filters-pane"></a>Fönstret Filter
Visa, ange och ändra filter för sida, rapport, detaljinformation och visuell nivå.

![](media/service-the-report-editor-take-a-tour/power-bi-formatting-pane.png)

Mer information finns i [Lägg till ett filter till en rapport](power-bi-report-add-filter.md).

- - -
## <a name="the-fields-pane"></a>Fönstret Fält
Fönstret Fält visar de tabeller och fält som finns i dina data och som är tillgängliga så att du kan använda dem för att skapa visualiseringar.

|  |  |
| --- | --- |
| ![](media/service-the-report-editor-take-a-tour/reportfields.png) |<ul><li>Starta en ny visualisering genom att dra ett fält till sidan.  Du kan också dra ett fält till en befintlig visualisering så att fältet läggs till i visualiseringen.<br><br></li> <li>När du lägger till en bock bredvid ett fält så lägger Power BI till det fältet i den aktiva (eller nya) visualiseringen. Och det avgör även i vilken bucket fältet ska placeras.  Ska fältet t.ex. används som en förklaring, en axel eller ett värde? Power BI gör en kvalificerad gissning, och du kan flytta den från en bucket till en annan, om så skulle behövas. <br><br></li><li>Oavsett hur du gör, så har varje markerat fält lagts till i fönstret Visualiseringar i Rapportredigeraren.</li></ul> |

**Obs!** Om du använder Power BI Desktop du har också alternativ för att visa/dölja fält, lägga till beräkningar osv.

### <a name="what-do-the-field-icons-mean"></a>Vad betyder fältikonerna?
* **∑ Aggregeringar** En aggregering är ett numeriskt värde som t.ex. ska summeras eller utgöra ett genomsnitt. Aggregeringar importeras med data (som definieras i den datamodell som rapporten baseras på).
  Mer information finns i [Aggregeringar i Power BI-rapporter](service-aggregates.md).
* ![](media/service-the-report-editor-take-a-tour/pbi_calculated_icon.png)**Beräknade mått (kallas även för beräknade fält)**  
   Varje beräknat fält har en egen hårdkodad formel. Du kan t.ex. inte ändra beräkningen om den är en summa. Den kan bara vara en summa. Mer information finns i [Förstå mått](desktop-measures.md)
* ![](media/service-the-report-editor-take-a-tour/icon.png) **Unika fält**  
   Fält med den här ikonen importerades från Excel och är inställda på att visa alla värden, även om de har dubbletter. Dina data kan t.ex. ha två poster för personer med namnet ”John Smith”, och var och en behandlas som unik – de summeras inte.  
* **![](media/service-the-report-editor-take-a-tour/pbi_geo_icon.png)Geografifält**  
   Platsfält kan användas för att skapa kartvisualiseringar. 
* **![](media/service-the-report-editor-take-a-tour/power-bi-hierarchy-icon.png) Hierarki**  
   Markera pilen om du vill visa vilka fält som bildar hierarkin. 

- - -
## <a name="2-the-top-navigation-bar"></a>2. Översta navigeringsfältet
Åtgärder som är tillgängliga från det övre navigeringsfältet är ett stort antal, och nya åtgärder läggs till hela tiden. Använd Power BI-dokumentationens innehållsförteckning eller sökrutan om du vill ha information om en viss åtgärd.

## <a name="3-the-report-canvas"></a>3. Rapportarbetsytan
Rapportarbetsytan är den plats där arbetet visas. När du använder fönstren Fält, Filter och Visualiseringar för att skapa visuella objekt, så skapas och visas dessa på rapportarbetsytan. Varje flik längst ned på arbetsytan representerar en sida i rapporten. Öppna en sida genom att välja dess flik. 

## <a name="next-steps"></a>Nästa steg:
[Skapa en rapport](service-report-create-new.md)

[Redigera en rapport](service-interact-with-a-report-in-editing-view.md)

Läs mer om [rapporter i Power BI](service-reports.md)

[Kom igång med Power BI](service-get-started.md)

[Power BI – grundläggande begrepp](service-basic-concepts.md)

Har du fler frågor? [Försök med att fråga Power BI Community](http://community.powerbi.com/)
