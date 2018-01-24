---
title: Anslut till Application Insights Anslut till Power BI
description: "Application Insights för Power BI"
services: powerbi
documentationcenter: 
author: joeshoukry
manager: kfile
backup: maggiesMSFT
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/16/2017
ms.author: yshoukry
ms.openlocfilehash: 3aa07c88daccc84bcf09af9d31a73a4411a3e541
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/15/2017
---
# <a name="connect-to-application-insights-with-power-bi"></a>Anslut till Application Insights med Power BI
Använd Power BI för att skapa kraftfulla anpassade instrumentpaneler från telemetrin [Application Insights](https://azure.microsoft.com/documentation/articles/app-insights-overview/). Förutse din apptelemetri på nya sätt. Kombinera mått för flera appar eller komponenttjänster på en instrumentpanel. Den första versionen av Power BI-innehållspaketet för Application Insights innehåller widgetar för vanliga användningsrelaterade mått såsom aktiva användare, sidvy, sessioner, webbläsare och OS-version och geografisk fördelning av användare på en karta.

Anslut till [Application Insights-innehållspaket för Power BI](https://app.powerbi.com/getdata/services/application-insights).

>[!NOTE]
>Åtkomst till Application Insights översiktsblad för ditt program i Azure Preview Portal krävs för att ansluta. Mer information om kraven finns nedan.

## <a name="how-to-connect"></a>Så här ansluter du
1. Välj **Hämta data** längst ned i det vänstra navigeringsfönstret.
   
    ![Knappen Hämta data](media/service-connect-to-application-insights/pbi_getdata.png)
2. I rutan **tjänster** väljer du **Hämta**.
   
    ![Knappen Hämta tjänster](media/service-connect-to-application-insights/pbi_getservices.png)
3. Välj **Application Insights** > **Hämta**.
   
    ![Application Insights-innehållspaket](media/service-connect-to-application-insights/appinsights.png)
4. Ange information om programmet som du vill ansluta till, inklusive **resursnamnet för Application Insights**, **resursgrupp** och **prenumerations-ID**. Se [Hitta Application Insights-parametrar](#FindingAppInsightsParams) nedan för mer information.
   
    ![Dialogrutan för Application Insights-anslutning](media/service-connect-to-application-insights/pbi_contpkappinsitconnectndialog.png)    
5. Välj **Logga In** och följ anvisningarna för att ansluta.
   
    ![Inloggning för Application Insights-anslutning](media/service-connect-to-application-insights/pbi_contpkappinsitconnectn2.png)
6. Importen startar automatiskt. När du är klar visas ett meddelande och en ny instrumentpanel, rapport och datauppsättning visas i navigeringsfönstret markerade med en asterisk.  Välj instrumentpanelen för att se dina importerade data.
   
    ![Application Insights-instrumentpanel](media/service-connect-to-application-insights/pbi_contpkappinsitdash.png)

**Och sedan?**

* Prova att [ställa en fråga i rutan Frågor och svar](service-q-and-a.md) överst på instrumentpanelen
* [Ändra panelerna](service-dashboard-edit-tile.md) på instrumentpanelen.
* [Välj en panel](service-dashboard-tiles.md) för att öppna den underliggande rapporten.
* Även om din datauppsättning kommer att vara schemalagd att uppdateras dagligen, kan du ändra uppdateringsschemat eller uppdatera på begäran med **Uppdatera nu**

## <a name="whats-included"></a>Vad ingår
Application Insights-innehållspaketet innehåller följande tabeller och mått:  

    - ApplicationDetails  
    - UniqueUsersLast7Days   
    - UniqueUsersLast30Days   
    - UniqueUsersDailyLast30Days  
    - UniqueUsersByCountryLast7Days  
    - UniqueUsersByCountryLast30Days   
    - PageViewsDailyLast30Days   
    - SessionsLast7Days   
    - SessionsLast30Days  
    - PageViewsByBrowserVersionDailyLast30Days   
    - UniqueUsersByOperatingSystemLast7Days   
    - UniqueUsersByOperatingSystemLast30Days    
    - SessionsDailyLast30Days   
    - SessionsByCountryLast7Days   
    - SessionsByCountryLast30Days   
    - PageViewsByCountryDailyLast30Days   

<a name="FindingAppInsightsParams"></a>

## <a name="finding-parameters"></a>Hitta parametrar
Ditt resursnamn, din resursgrupp och ditt prenumerations-ID hittar du i Azure Portal. Genom att markera namnet öppnas en detaljerad vy och du kan använda Essentials-listrutan för att hitta de värden som du behöver.

![Application Insights-parametrar](media/service-connect-to-application-insights/pbi_contpkappinsitparams.png)

Kopiera och klistra in dessa i fälten i Power BI:

![Application Insights-parametrar](media/service-connect-to-application-insights/pbi_contpkappinsitparam2.png)

## <a name="next-steps"></a>Nästa steg
[Kom igång i Power BI](service-get-started.md)

[Hämta data i Power BI](service-get-data.md)
