---
title: Kombinationsdiagram i Power BI
description: Den här självstudien om kombinationsdiagram förklarar när du ska använda dem och hur du skapar dem i Power BI-tjänsten och Desktop.
author: mihart
ms.reviewer: ''
featuredvideoid: lnv66cTZ5ho
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 06/18/2020
ms.author: rien
LocalizationGroup: Visualizations
ms.openlocfilehash: 90c721f6c2f555bd632d6c8fff56d05994b1444b
ms.sourcegitcommit: caf60154a092f88617eb177bc34fb784f2365962
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/25/2020
ms.locfileid: "85354787"
---
# <a name="create-and-use-combo-charts-in-power-bi"></a>Skapa och använda kombinationsdiagram i Power BI

[!INCLUDE[consumer-appliesto-nyyn](../includes/consumer-appliesto-nyyn.md)]

[!INCLUDE [power-bi-visuals-desktop-banner](../includes/power-bi-visuals-desktop-banner.md)]

I Power BI är ett kombinationsdiagram en enskild visualisering som kombinerar ett linjediagram med ett stapeldiagram. Om du kombinerar de två diagrammen till ett kan du göra en snabbare jämförelse av dina data.

Kombinationsdiagram kan ha en eller två Y-axlar.

## <a name="when-to-use-a-combo-chart"></a>När du ska använda ett kombinationsdiagram
Kombinationsdiagram är ett bra alternativ:

* när du har ett linjediagram och ett stapeldiagram med samma X-axel,
* för att jämföra flera mått med olika värdeintervall,
* för att illustrera sambandet mellan två mätvärden i en visualisering,
* för att kontrollera om ett mätvärde uppfyller det mål som definieras av ett annat mätvärde,
* för att spara utrymme på arbetsytan.

> [!NOTE]
> För att dela en rapport med en Power BI-kollega krävs att du både har individuella Power BI Pro-licenser eller att rapporten har sparats med Premium-kapacitet.

### <a name="prerequisites"></a>Förutsättningar
De här självstudierna använder sig av [PBIX-filen Exempel på detaljhandelsanalys](https://download.microsoft.com/download/9/6/D/96DDC2FF-2568-491D-AAFA-AFDD6F763AE3/Retail%20Analysis%20Sample%20PBIX.pbix).

1. Välj **Arkiv** > **Öppna** uppe till vänster på menyraden
   
2. Leta reda på kopian av **PBIX-filen Exempel för detaljhandelsanalys**

1. Öppna **PBIX-filen Exempel för detaljhandelsanalys** i rapportvyn ![Skärmbild av rapportvisningsikonen.](media/power-bi-visualization-kpi/power-bi-report-view.png).

1. Välj ![Skärmbild av den gula fliken.](media/power-bi-visualization-kpi/power-bi-yellow-tab.png) för att lägga till en ny sida.



## <a name="create-a-basic-single-axis-combo-chart"></a>Skapa ett grundläggande kombinationsdiagram med en axel
Se hur Will skapar ett kombinationsdiagram med exemplet på försäljning och marknadsföring.
   > [!NOTE]
   > Den här videon använder en äldre version av Power BI Desktop.
   > 
   > 
<iframe width="560" height="315" src="https://www.youtube.com/embed/lnv66cTZ5ho?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>  

<a name="create"></a>

1. Börja med en tom rapportsida och skapa ett stapeldiagram som visar årets försäljning och bruttomarginal per månad.

    a.  Välj **Försäljning** \> **This Year Sales (Årets försäljning)**  > **Värde** i fönstret Fält.

    b.  Dra **Försäljning** \> **Gross Margin This Year (Årets bruttomarginal)** till området **Värde**.

    c. Välj **Tid** \> **FiscalMonth** och lägg till det i **Axel**.

    ![självstudieexempel på kombinationsdiagram](media/power-bi-visualization-combo-chart/combotutorial1new.png)
5. Välj **Fler alternativ** uppe till höger i visualiseringen och välj **Sortera efter > FiscalMonth** (Räkenskapsmånad). Om du vill ändra sorteringsordningen väljer du ellipsen igen och väljer antingen **Sort ascending (Sortera stigande)** eller **Sort descending (Sortera fallande)** . I det här exemplet väljer vi **Sortera stigande**.

6. Konvertera stapeldiagrammet till ett kombinationsdiagram. Det finns två kombinationsdiagram: **Linjediagram och stående stapeldiagram** samt **Linjediagram och grupperat stående stapeldiagram**. Välj **Linje- och grupperat stapeldiagram** i fönstret **Visualiseringar** med stapeldiagrammet markerat.

    ![exempel på konvertering av kombinationsdiagram](media/power-bi-visualization-combo-chart/converttocombo-new2.png)
7. Från panelen **Fält** drar du **Försäljning** \> **Last Years Sales (Förra årets försäljning)** till behållaren **Radvärden**.

   ![Radvärdesområdet som visar förra årets försäljning](media/power-bi-visualization-combo-chart/linevaluebucket.png)

   Kombinationsdiagrammet bör se ut ungefär så här:

   ![exempel på slutfört kombinationsdiagram](media/power-bi-visualization-combo-chart/combochartdone-new.png)

## <a name="create-a-combo-chart-with-two-axes"></a>Skapa ett kombinationsdiagram med två axlar
I det här steget ska vi jämföra bruttomarginal och försäljning.

1. Skapa ett nytt linjediagram som spårar **Bruttomarginal förra året %** efter **FiscalMonth** (Räkenskapsmånad). Välj ellipserna för att sortera efter **Month** (Månad) och **Ascending** (Stigande).  
I januari var bruttomarginal % 35 %, med en topp på 45 % i april som sjönk i juli och fick ytterligare en topp igen i augusti. Ser vi ett liknande mönster för försäljningen föregående år och det här året?

   ![exempel på försäljning i kombinationsdiagram](media/power-bi-visualization-combo-chart/combo1-new.png)
2. Lägg till **This Year Sales (Årets försäljning) > Värde** och **Last Years Sales (Förra årets försäljning)** till linjediagrammet. Skalan för **Bruttomarginal förra året %** är mycket mindre än skalan för **Försäljning** vilket gör det svårt att jämföra.      

   ![exempel på flatline för kombinationsdiagram](media/power-bi-visualization-combo-chart/flatline-new.png)
3. Konvertera linjediagrammet till ett Linjediagram och stående stapeldiagram om du vill göra det visuella objektet lättare att läsa och tolka.

   ![exempel på konvertering till kombinationsdiagram](media/power-bi-visualization-combo-chart/converttocombo-new.png)

4. Dra **Gross Margin% Last Year (Bruttomarginal % förra året)** från **Kolumnvärde** till **Radvärden**. Power BI skapar två axlar, vilket medför att datauppsättningarna kan skalas på olika sätt; den till vänster mäter dollar försäljning och den till höger procentandel. Svaret på frågan ovan är ja, vi ser ett liknande mönster.

   ![exempel på klusterkombinationsdiagram](media/power-bi-visualization-combo-chart/power-bi-clustered-combo.png)    

## <a name="add-titles-to-the-axes"></a>Lägga till rubriker på axlarna
1. Välj rollerikonen ![rollerikon](media/power-bi-visualization-combo-chart/power-bi-paintroller.png) för att öppna formateringsfönstret.
1. Välj nedpilen för att expandera alternativen för **y-axeln**.
1. För **Y-axel (kolumn)** anger du **Position** till **Vänster** och **Rubrik** till **På**,  **Format** till **Visa endast rubriken** och **Visa enheter** som **Miljoner**.

   ![exempel på öppna y i kombinationsdiagram](media/power-bi-visualization-combo-chart/power-bi-open-y.png)
4. Under **Y-axel (kolumn)** bläddrar du ned tills du ser **Visa sekundär**. Eftersom det finns så många alternativ för Y-axlarna kan du behöva använda båda rullningslisterna. Avsnittet Visa sekundär visar alternativ för att formatera linjediagramdelen i kombinationsdiagrammet.

   ![exempel på sekundär i kombinationsdiagram](media/power-bi-visualization-combo-chart/power-bi-secondary.png)
5. För **Y-axeln (rad)** lämnar du **Position** som **Höger**, ställer in **Rubrik** till **På** och ställer in **Format** på **Visa endast rubriken**.

   Kombinationsdiagrammet visar nu dubbla axlar, båda med rubriker.

   ![exempel på kombinationsdiagramrubriker](media/power-bi-visualization-combo-chart/power-bi-2-titles.png)

6. Du kan också ändra teckensnitt, storlek och färg och ställa in andra formateringsalternativ för att förbättra visning och läsbarhet av diagrammet.

Härifrån kan du vilja:

* [lägga till kombinationsdiagrammet som en panel på instrumentpanelen](../create-reports/service-dashboard-tiles.md),
* [Spara rapporten](../create-reports/service-report-save.md).
* [göra rapporten mer lättillgänglig för personer med funktionshinder](../create-reports/desktop-accessibility-overview.md).

## <a name="cross-highlighting-and-cross-filtering"></a>Korsmarkering och korsfiltrering

Om du markerar en kolumn eller linje i ett kombinationsdiagram så korsmarkeras och korsfiltreras de övriga visualiseringarna på rapportsidan och vice versa. Använd [visuella interaktioner](../create-reports/service-reports-visual-interactions.md) för att ändra det här standardbeteendet.

## <a name="next-steps"></a>Nästa steg

[Ringdiagram i Power BI](power-bi-visualization-doughnut-charts.md)

[Visualiseringstyper i Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md)
