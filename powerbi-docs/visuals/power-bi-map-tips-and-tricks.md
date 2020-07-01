---
title: Tips och råd för mappar (inklusive Bing Maps-integrering)
description: 'Tips och trick för Power BI-kartvisualiseringar, visuella objekt, platser, longitud och latitud och hur de fungerar med Bing Maps. '
author: mihart
ms.reviewer: rien
featuredvideoid: ajTPGNpthcg
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: how-to
ms.date: 05/05/2020
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 87509a4a2415a8f7a2a7a27d34dc2a6f3a39b92f
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85232402"
---
# <a name="tips-and-tricks-for-power-bi-map-visualizations"></a>Tips för Power BI-kartvisualiseringar

[!INCLUDE[consumer-appliesto-nyyn](../includes/consumer-appliesto-nyyn.md)]    

Power BI integrerar med Bing Maps för att tillhandahålla kartkoordinater av standardtyp (en process som kallas geokodning), vilket gör det enklare att skapa kartor. Tillsammans använder de algoritmer för att identifiera rätt plats, men är det mest en gissning. Om Power BI inte kan skapa kartvisualiseringen på egen hand, använder den sig av Bing Maps. 

Du eller din administratör kan behöva uppdatera brandväggen för att tillåta åtkomst till de URL:er Bing använder för geokodning.  Dessa URL:er är:
* https://dev.virtualearth.net/REST/V1/Locations
* https://platform.bing.com/geo/spatial/v1/public/Geodata
* https://www.bing.com/api/maps/mapcontrol

Du kan använda följande tips för att öka sannolikheten för rätt geo-kodning. Du kan skaffa den första uppsättningen tips för att få åtkomst till datauppsättningen. Den andra uppsättningen tips är saker du kan göra i Power BI om du inte har åtkomst till datauppsättningen. 

## <a name="what-is-sent-to-bing-maps"></a>Vad skickas till Bing Maps?
Power BI-tjänsten och Power BI Desktop skickar Bing geoinformation som behövs för att skapa kartvisualiseringen. Det här kan vara data i bucketarna **Plats**, **Latitud** och **Longitud** i visualiseringens fält. Exakt vad som skickas beror på karttypen. Läs mer i [Bing Maps-sekretess](https://go.microsoft.com/fwlink/?LinkID=248686).

* Om longitud och latitud anges i kartor (bubbelkartor, punktkartor och punktritningskartor), kommer inte några data att skickas till Bing. Annars skickas alla data i bucketen **Plats** till Bing.     

* Koropletkartor kräver att det finns ett fält i **Plats**, även om latitud och longitud anges. Alla data som finns i **Plats**, **Latitud** och **Longitud** skickas till Bing.
  
    I exemplet nedan används fältet **Leverantör** till geokodning, så alla värden i kolumnen Leverantör skickas till Bing. Data från **Storlek** och **Färgmättnad** skickas inte till Bing.
  
    ![skickas till Bing Maps](./media/power-bi-map-tips-and-tricks/power-bi-sent-to-bing-new.png)
  
    I exemplet nedan används fältet **Territorium** till geokodning, så alla värden i kolumnen Territorium skickas till Bing. Data från **Förklaring** och **Färgmättnad** skickas inte till Bing.
  
    ![Fyllda kartor och Bing](./media/power-bi-map-tips-and-tricks/power-bi-filled-map.png)

## <a name="in-the-dataset-tips-to-improve-the-underlying-dataset"></a>I datauppsättningen: tips för att förbättra den underliggande datauppsättningen
Om du har åtkomst till datamängden som används för att skapa kartan finns några saker du kan göra för att öka sannolikheten för rätt geokodning.

**1. Kategorisera geografiska fält i Power BI Desktop**

Du kan kontrollera att fält är korrekt geokodade i Power BI Desktop genom att ställa in *Datakategori* i datafälten. Välj önskad kolumn i vyn Data. I menyfliksområdet väljer du fliken **Modellering**. Ange sedan **Datakategori** till **Adress**, **Stad**, **Kontinent**, **Land/region**, **Län**, **Postnummer**, **Delstat** eller **Provins**. Dessa datakategorier hjälper Bing att korrekt koda datumet. Läs mer i [kategorisering av data i Power BI Desktop](../transform-model/desktop-data-categorization.md). Om du ansluter i realtid till SQL Server Analysis Services behöver du ange datakategorisering utanför Power BI med hjälp av [SQL Server Data Tools (SSDT)](https://docs.microsoft.com/sql/ssdt/download-sql-server-data-tools-ssdt).

**2. Använda mer än en platskolumn.**     
 Ibland räcker det inte att ställa in datakategorier för kartor för att Bing ska kunna gissa din avsikt. Vissa benämningar är tvetydiga eftersom platsen som finns i flera länder eller regioner. ***Southampton*** finns till exempel i England, Pennsylvania och New York.

Power BI använder Bings [Ostrukturerade URL-malltjänst](/bingmaps/rest-services/locations/find-a-location-by-address) för att hämta latitud- och longitudkoordinater baserat på en uppsättning adressvärden för valfritt land. Om dina data inte innehåller tillräckligt med platsdata kan du lägga till dessa kolumner och kategorisera dem korrekt.

 Om du bara har en stadskolumn blir geokodningen svår för Bing. Lägga till ytterligare geokolumner om du vill att platsen ska vara entydig.  Ibland räcker det att lägga till en platskolumn i datauppsättningen, i det här fallet en stat/provins. Glöm inte att kategorisera den korrekt, se nr 1 ovan.

Kontrollera att det bara finns en enda platskategori i de olika fälten. Till exempel ska stad automatiskt vara **Southampton**, inte **Southampton, New York**.  Och platsadressfältet ska vara **1 Microsoft Way** och inte **1 Microsoft sätt, Redmond, WA**.

**3. Använd specifik latitud och longitud**

Lägg till latitud- och longitud i datauppsättningen. Detta tar bort all tvetydighet och returnerar resultatet snabbare. Latitud- och longitudfält måste vara i *decimaltal* format, vilket du kan ange i datamodellen.

<iframe width="560" height="315" src="https://www.youtube.com/embed/ajTPGNpthcg" frameborder="0" allowfullscreen></iframe>

**4. Använd platskategorin för kolumner med fullständig platsinformation**

Medan vi rekommenderar att du använder geohierarkier i dina kartor om du måste använda en enda platskolumn med fullständig geografisk information kan du ange datakategorisering och **plats**. Till exempel om data i kolumnen består av fullständiga adresser, till exempel 1 Microsoft Way, Redmond i delstaten Washington 98052, fungerar den generaliserade datakategorin bäst med Bing. 

## <a name="in-power-bi-tips-to-get-better-results-when-using-map-visualizations"></a>I Power BI: Tips för att få bättre resultat när du använder kartor
**1. Använd latitud- och longitudfälten (om de finns)**

I Power BI om datauppsättningen som du använder har fält för longitud och latitud--använd dem!  Power BI har särskilda buckets för att göra kartdata entydiga. Du behöver bara dra fältet som innehåller dina latituddata till området **Visualiseringar > Latitud**.  Gör sedan samma sak för dina longituddata. När du gör det också måste du fylla i fältet *plats* när du skapar din visualiseringar. Annars sammanställs informationen som standard, till exempel latitud och longitud skulle länkas på delstatsnivå, inte stadsnivå.

![latitud och longitud](./media/power-bi-map-tips-and-tricks/pbi_latitude.png) 

## <a name="use-geo-hierarchies-so-you-can-drill-down-to-different-levels-of-location"></a>Använda geohierarkier för att öka detaljnivån till olika ”nivåer” för platsen
När din datauppsättning redan har flera nivåer för platsdata kan du och dina kollegor använda Power BI för att skapa *geo-hierarkier*. Gör detta genom att dra mer än ett fält till **Plats**. Tillsammans blir fälten då en geo-hierarki. I nedanstående exempel har vi lagt till geo-fält för: Land/Region, tillstånd och stad. I Power BI kan du och dina kollegor detaljgranska uppåt och nedåt med hjälp av den här geo-hierarkin.

  ![Platsfält](./media/power-bi-map-tips-and-tricks/power-bi-hierarchy.png)

   ![skapa geo-hierarki för kartor](./media/power-bi-map-tips-and-tricks/power-bi-geo.gif)

När du ändrar detaljnivån med geo-hierarkier är det viktigt att veta hur varje detaljnivåknapp fungerar och vad som skickas till Bing Maps. 

* Detaljnivåknappen längst till höger kallas även för granskningsläge ![Med ikonen Granskningsläge](media/power-bi-map-tips-and-tricks/power-bi-drill-down.png) kan du välja en kartplats och se mer information om den specifika platsen en nivå i taget. Till exempel om du aktiverar detaljnivån och klickar på Nordamerika flyttar du nedåt i hierarkin till nästa nivå – delstater i Nordamerika. För geo-kodning skickar Power BI endast land- och delstatsinformation för Nordamerika till Bing Maps.  
* Till vänster finns ytterligare 2 alternativ för att ändra detaljnivå. Det första alternativet, ![den första detaljnivåikonen](media/power-bi-map-tips-and-tricks/power-bi-drill-down2.png) , går nedåt till nästa nivå i hierarkin för alla platser samtidigt. Om du för närvarande tittar på länder och sedan använder det här alternativet för att ändra till nästa nivå, delstater, så visar Power BI delstatsdata för alla länder. Power BI skickar delstatsdata till Bing Maps (inga landdata) för alla platser för geo-kodning. Det här alternativet är användbart om varje nivå i hierarkin är inte relaterat till nivån ovanför. 
* Det andra alternativet, ![byt nivå med kartor](./media/power-bi-map-tips-and-tricks/power-bi-drill-down3.png) , påminner om att ändra detaljnivån, men du behöver inte klicka på kartan.  Den expanderas till nästa nivå i hierarkin och kommer ihåg den aktuella nivåns kontext. Till exempel, om du för tillfället tittar på länder och väljer den här ikonen kommer du att hamna på nästa nivå i hierarkin – delstater. Power BI skickar data för varje delstat och dess motsvarande land att hjälpa Bing Maps att geokoda med större precision. Det här alternativet eller alternativet öka detaljnivå längst till höger används med de flesta kartorna, så att du kan skicka så mycket information som möjligt till Bing för att få noggrann platsinformation. 

## <a name="next-steps"></a>Nästa steg
[Öka detaljnivån i en visualisering i Power BI](../consumer/end-user-drill.md)

[Visualiseringar i Power BI](power-bi-report-visualizations.md)

Har du fler frågor? [Prova Power BI Community](https://community.powerbi.com/)
