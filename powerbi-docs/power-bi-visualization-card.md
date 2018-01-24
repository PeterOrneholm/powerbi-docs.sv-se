---
title: "Kortvisualiseringar (även kallat stor sifferpanel)"
description: Skapa en kortvisualisering i Power BI
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/24/2017
ms.author: mihart
ms.openlocfilehash: 1136aae9af4481a1d55ca3d11ed300242aab187b
ms.sourcegitcommit: 74fbbca81a056dda19b3647ae058005aba5296f5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/03/2018
---
# <a name="card-visualizations"></a>Kortvisualiseringar
Ett enda tal kan ibland vara det viktigaste du vill spåra i Power BI-instrumentpanelen eller -rapporten, till exempel total försäljning, marknadsandel år för år eller totala affärsmöjligheter. Den här typen av visualisering kallas ett *kort*. Som nästan alla ursprungliga Power BI-visualiseringar, kan kort skapas med hjälp av rapportredigeraren eller Frågor och svar.

![kortvisualisering](media/power-bi-visualization-card/pbi_opptuntiescard.png)

## <a name="create-a-card-using-the-report-editor"></a>Skapa ett kort med hjälp av rapportredigeraren
Dessa anvisningar använder sig av Exempel på detaljhandelsanalys. Om du vill följa med kan du [hämta exemplet](sample-datasets.md) för Power BI-tjänsten (app.powerbi.com) eller Power BI Desktop.   

1. Starta på en [tom rapportsida ](power-bi-report-add-page.md) och välj fältet **Butik** \> **Antal öppna butiker**. Om du använder Power BI-tjänsten måste du öppna rapporten i [redigeringsvyn](service-interact-with-a-report-in-editing-view.md).

    Power BI skapar ett stapeldiagram med ditt tal.

   ![](media/power-bi-visualization-card/pbi_rptnumbertilechart.png)
2. I fönstret Visualiseringar väljer du färgrollerikonen.

   ![](media/power-bi-visualization-card/pbi_changechartcard.png)
6. Hovra över kortet och välj stiftikonen ![](media/power-bi-visualization-card/pbi_pintile.png) för att lägga till visualiseringen på instrumentpanelen.

   ![](media/power-bi-visualization-card/power-bi-pin-icon.png)
7. Fäst panelen på en befintlig eller ny instrumentpanel.

   * Befintlig instrumentpanel: välj instrumentpanelens namn i listrutan.
   * Ny instrumentpanel: Skriv instrumentpanelens namn.
8. Välj **Fäst**.

   Genom ett meddelande (nära det övre högra hörnet) får du reda på att visualiseringen har lagts till, som en panel, på instrumentpanelen.

   ![](media/power-bi-visualization-card/power-bi-pin-success-message.png)
9. Välj **Gå till instrumentpanelen**. Där kan du [redigera och flytta](service-dashboard-edit-tile.md) den fästa visualiseringen.


## <a name="create-a-card-from-the-qa-question-box"></a>Skapa ett kort från frågerutan för frågor och svar
Att använda frågerutan för frågor och svar är den enklaste metoden för att skapa ett kort. Frågerutan för frågor och svar är tillgänglig i Power BI-tjänsten (app.powerbi.com) från en instrumentpanel eller rapport. Stegen nedan beskriver hur du skapar ett kort från en instrumentpanel i Power BI-tjänsten. Om du vill skapa ett kort med Frågor och svar i Power BI Desktop [, följer du nedanstående instruktioner](https://powerbi.microsoft.com/en-us/blog/power-bi-desktop-december-feature-summary/#QandA) för Frågor och svar-förhandsgranskning för Desktop-rapporter.

1. Skapa en [instrumentpanel](service-dashboards.md) och [hämta data](service-get-data.md). Det här exemplet använder sig av [Exempel på analys av affärsmöjligheter](sample-opportunity-analysis.md).

1. Börja skriva vad du vill veta om dina data i frågerutan överst på instrumentpanelen. 

   ![](media/power-bi-visualization-card/power-bi-q-and-a-box.png)

>**Tips**: Gå till [Redigeringsvy](service-reading-view-and-editing-view.md) i Power BI-tjänsterapporten och välj **Ställ en fråga** från den översta menyraden. I en Power BI Desktop-rapport letar du upp ett öppet utrymme i en rapport och dubbelklickar för att öppna en frågeruta.

3. Skriv till exempel ”antal affärsmöjligheter” i frågerutan.

   ![](media/power-bi-visualization-card/power-bi-q-and-a.png)

   Frågerutan hjälper dig med förslag och rättelser och visar slutligen det totala antalet.  
4. Välj stiftikonen ![](media/power-bi-visualization-card/pbi_pintile.png) i det övre högra hörnet för att lägga till kortet på en instrumentpanel.

   ![](media/power-bi-visualization-card/power-bi-pin.png)
5. Fäst kortet, som en panel, på en befintlig eller ny instrumentpanel.

   * Befintlig instrumentpanel: välj instrumentpanelens namn i listrutan. Dina val begränsas till instrumentpanelerna inom den aktuella arbetsytan.
   * Ny instrumentpanel: ange namnet på den nya instrumentpanelen så läggs den till din aktuella arbetsyta.
6. Välj **fäst**.

   Genom ett meddelande (nära det övre högra hörnet) får du reda på att visualiseringen har lagts till, som en panel, på instrumentpanelen.  

   ![](media/power-bi-visualization-card/power-bi-success.png)
7. Välj **gå till instrumentpanel** för att se den nya panelen. Där kan du [byta namn på, ändra storlek, lägga till en hyperlänk och flytta panelen och mer](service-dashboard-edit-tile.md) på din instrumentpanel.

   ![](media/power-bi-visualization-card/power-bi-pinned.png)

## <a name="considerations-and-troubleshooting"></a>Överväganden och felsökning
- Om du inte ser någon frågeruta, kontakta din system- eller klientadministratör.    
- Om du använder Desktop och Frågor och svar inte öppnas när du dubbelklickar på ett tomt utrymme i en rapport, kan du behöva aktivera funktionen.  Välj **Fil > Alternativ och inställningar > Alternativ > Förhandsversionsfunktioner > Frågor och svar** och starta om Desktop.


## <a name="next-steps"></a>Nästa steg
[Paneler på instrumentpanelen i Power BI](service-dashboard-tiles.md)

[Instrumentpaneler i Power BI](service-dashboards.md)

[Power BI – grundläggande begrepp](service-basic-concepts.md)

Har du fler frågor? [Prova Power BI Community](http://community.powerbi.com/)