---
title: "Skapa en ny rapport från en datauppsättning "
description: "Skapa en ny Power BI-rapport från en datauppsättning."
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: monitoring
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/28/2017
ms.author: mihart
ms.openlocfilehash: f4afb1eaa1b3012fdbdb0eff35e9eff695cc32e4
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/13/2017
---
# <a name="create-a-new-power-bi-report-by-importing-a-dataset"></a>Skapa en ny Power BI-rapport genom att importera en datauppsättning
Du har läst [Rapporter i Power BI](service-reports.md) och nu vill du skapa en egen. Det finns många olika sätt att skapa en rapport och i den här artikeln börjar vi med att skapa en grundläggande rapport från en Excel-datauppsättning. När du förstår grunderna för att skapa en rapport leder **Nästa steg** längst ned till mer avancerade avsnitt om rapporter.  

> **TIPS**: för att skapa en rapport genom att kopiera en befintlig rapport, se [Kopiera en rapport](power-bi-report-copy.md)
> 
> 

## <a name="import-the-dataset"></a>Importera datauppsättningen
Den här metoden för att skapa en rapport som börjar med en datauppsättning och en tom rapportarbetsyta. För att följa med in instruktionerna kan du [hämta exempeldatauppsättningen Försäljningsanalys för Excel](http://go.microsoft.com/fwlink/?LinkId=529778) och spara den till OneDrive för företag (rekommenderas) eller lokalt.

1. Vi kommer att skapa rapporten i en arbetsyta för Power BI-tjänsten, så välj en befintlig arbetsyta eller skapa en ny.
   
   ![](media/service-report-create-new/power-bi-workspaces2.png)
2. Välj **Hämta data** längst ned i det vänstra navigeringsfönstret.
   
   ![](media/service-report-create-new/power-bi-get-data3.png)
3. Välj **Arkiv**  och navigera till den plats där du sparade exemplet Säljanalys.
   
    ![](media/service-report-create-new/power-bi-select-files.png)
4. För den här övningen väljer vi **Importera**.
   
   ![](media/service-report-create-new/power-bi-import.png)
5. När du har importerat datauppsättningen väljer du **Visa datauppsättning**.
   
   ![](media/service-report-create-new/power-bi-view-dataset.png)
6. När du visar en datauppsättning öppnas rapportredigeraren.  Du ser en tom arbetsyta och rapportredigeringsverktygen.
   
   ![](media/service-report-create-new/power-bi-blank-report.png)

> **TIPS**: Om du inte är bekant med rapportarbetsytan eller behöver en påminnelse kan du besöka [Ta en titt på rapportredigeraren ](service-the-report-editor-take-a-tour.md) innan du fortsätter.
> 
> 

## <a name="add-a-radial-gauge-to-the-report"></a>Lägg till en radiell mätare i rapporten
Nu när vi har importerat vår datauppsättning kan vi börja svara på frågor.  Vår marknadschef (CMO) vill veta hur nära vi kommer att vara till att uppfylla det här årets försäljningsmål. En mätare är ett [bra visualiseringsval](power-bi-report-visualizations.md) för att visa den här typen av information.

1. Välj **Sales (Försäljning)**  >  **This Year Sales (Årets försäljning)** > **Value (Värde)** i fönstret Fält.
   
    ![](media/service-report-create-new/power-bi-report-step1.png)
2. Omvandla det visuella objektet till en mätare genom att välja mätarmallen![](media/service-report-create-new/powerbi-gauge-icon.png) från fönstret **Visualiseringar**.
   
    ![](media/service-report-create-new/power-bi-report-step2.png)
3. Dra **försäljning** > **Årets försäljning** > **Mål** till brunnen **Målvärde**. Vi verkar vara mycket nära vårt mål.
   
    ![](media/service-report-create-new/power-bi-report-step3.png)
4. Nu är dags att [spara din rapport](service-report-save.md).
   
   ![](media/service-report-create-new/powerbi-save.png)

## <a name="add-an-area-chart-and-slicer-to-the-report"></a>Lägg till ett ytdiagram och utsnitt i rapporten
Vår marknadschef har några ytterligare frågor för oss att besvara. Hon vill veta hur försäljningen år jämfört med förra året. Dessutom vill hon se resultaten per distrikt.

1. Först ska vi skapa lite utrymme på arbetsytan. Välj mätaren och flytta den till det övre högra hörnet. Tryck och dra ett av hörnet så att den blir mindre.
2. Avmarkera mätaren. Gå till rutan Fält och välj **Försäljning** > **Försäljning detta år** > **värdet** och välj **Försäljning**  >  **Försäljning förra året**.
   
    ![](media/service-report-create-new/power-bi-report-step4.png)
3. Omvandla det visuella objektet till ett ytdiagram genom att välja ytdiagrammallen![](media/service-report-create-new/power-bi-areachart-icon.png) från fönstret **Visualiseringar**.
4. Välj **Tid** > **Period** till brunnen **Axel**.
   
    ![](media/service-report-create-new/power-bi-report-step5.png)
5. Om du vill sortera visualiseringen, väljer du ellipserna och därefter **Sortera efter period**.
6. Nu ska vi lägga till utsnittet. Markera ett tomt område på arbetsytan och välj Utsnitt ![](media/service-report-create-new/power-bi-slicer-icon.png) mall. Detta lägger till ett tomt utsnitt på vår arbetsyta.
   
    ![](media/service-report-create-new/power-bi-report-step6.png)    
7. Välj **Distrikt** > **Distrikt** på fönstret Fält. Flytta och ändra storlek på utsticket.
   
    ![](media/service-report-create-new/power-bi-report-step7.png)  
8. Använd utsnittet för att leta efter mönster och insikter enligt distrikt.
   
   ![](media/service-report-create-new/power-bi-slicer-video2.gif)  
9. Du kan också fortsätta att lägga till visualiseringar.

## <a name="next-steps"></a>Nästa steg
* [Skapa en kopia av en rapport](power-bi-report-copy.md)
* [Spara rapporten](service-report-save.md)    
* [Lägg till en ny sida i rapporten](power-bi-report-add-page.md)  
* Lär dig hur du [fäster visualiseringar på en instrumentpanel](service-dashboard-pin-tile-from-report.md)    
* Har du fler frågor? [Försök med att fråga Power BI Community](http://community.powerbi.com/)
