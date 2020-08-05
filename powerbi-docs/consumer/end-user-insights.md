---
title: Kör och visa insikter på instrumentpaneler
description: Som en Power BI-slutanvändare, lär dig mer om att få insikter om dina instrumentpanelers paneler.
author: mihart
ms.reviewer: mihart
featuredvideoid: et_MLSL2sA8
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 06/22/2020
ms.author: mihart
LocalizationGroup: Dashboards
ms.openlocfilehash: 5fa66f2ff3650e4b4578207c2c70b70041c2c3d5
ms.sourcegitcommit: 2131f7b075390c12659c76df94a8108226db084c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/03/2020
ms.locfileid: "87537744"
---
# <a name="view-data-insights-on-dashboard-tiles-with-power-bi"></a>Visa datainsikter på instrumentpanelens paneler med Power BI

[!INCLUDE[consumer-appliesto-yyny](../includes/consumer-appliesto-yyny.md)]

Varje [panel](end-user-tiles.md) för visuella objekt på instrumentpanelen är en dörr in till datagranskning. När du väljer en panel öppnas en rapport eller [Frågor och svar](end-user-q-and-a.md) där du kan filtrera och sortera och fördjupa dig i datauppsättningen bakom rapporten. Och när du kör insikter, gör Power BI datagranskningen åt dig.

![läget ellips-menyn](./media/end-user-insights/power-bi-insight.png)

Kör insikter om du vill generera intressanta interaktiva visuella objekt utifrån dina data. Insikter kan köras på en specifik panel på instrumentpanelen och du kan till och med köra insikter på en insikt!

Funktionen insikter bygger på en växande [uppsättning avancerade analytiska algoritmer](end-user-insight-types.md) utvecklade tillsammans med Microsoft Research som vi kommer att fortsätta att använda så att flera användare kan söka efter insikter i sina data på nya och intuitiv sätt.

## <a name="run-insights-on-a-dashboard-tile"></a>Kör insikter på en panel på instrumentpanelen
När du kör insikter på en panel på instrumentpanelen, söker Power BI exakt de data som används för att skapa denna enskilda panel. 

1. [Öppna en instrumentpanel](end-user-dashboards.md).
2. Hovra över en panel. välj **Fler alternativ** (...) och sedan **Visa insikter**. 

    ![läget ellips-menyn](./media/end-user-insights/power-bi-hovers.png)


3. Panelen öppnas i [Fokusläge](end-user-focus.md) med detta insiktskort visat längst till höger.    
   
    ![Fokusläge](./media/end-user-insights/power-bi-insights-tile.png)    
4. Fångar ett insiktskort ditt intresse? Välj insiktskortet för att gå djupare. Vald insikt visas till vänster och nya insiktskort som endast baseras på data i denna enda insikt visas till höger.    

 ## <a name="interact-with-the-insight-cards"></a>Interagera med Insight-korten
När du har en insikt öppen, kan fortsätta att utforska.

   * Filtrera det visuella objektet på arbetsytan.  Välj pilen i det övre högra hörnet för att expandera filterfönstret om du vill visa filtren.

      ![insikter med utökad filtermeny](./media/end-user-insights/power-bi-filters.png)
   
   * Kör insikter på själva insiktskortet. Detta kallas ofta **relaterade insikter**. Välj ett insiktskort för att göra det aktivt. Det visas på rapportarbetsytan.
   
      ![insikter med utökad filtermeny](./media/end-user-insights/power-bi-insight-card.png)
   
   * I det övre högra hörnet väljer du ikonen med glödlampan ![ikonen Hämta insikter](./media/end-user-insights/power-bi-bulb-icon.png) eller **Hämta insikter**. Insikten visas till vänster och nya kort som endast baseras på data i denna enda insikt visas till höger.
     
     ![menyrad med ikonen Hämta insikter](./media/end-user-insights/power-bi-related.png)
     
Om du vill återgå till din rapport väljer du **Avsluta Fokusläge** i det övre vänstra hörnet.

## <a name="considerations-and-troubleshooting"></a>Överväganden och felsökning
- **Visa insikter** fungerar inte med alla typer av paneler på instrumentpanelen. Det är till exempel inte tillgängligt för anpassade visuella Power BI-objekt.<!--[Power BI visuals](end-user-custom-visuals.md)-->


## <a name="next-steps"></a>Nästa steg

Kör insikter om visuella rapportobjekt [med hjälp av analysfunktionen](end-user-analyze-visuals.md)    
Lär dig mer om [tillgängliga typer av Quick Insights](end-user-insight-types.md)

