---
title: "Tredjepartstjänst: Google Analytics-anslutningsprogram för Power BI Desktop"
description: "Tredjepartstjänst: Google Analytics-anslutningsprogram för Power BI Desktop"
services: powerbi
documentationcenter: 
author: davidiseminger
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
ms.date: 12/06/2017
ms.author: davidi
ms.openlocfilehash: a419a057405f56f452a53b21276fe5e4f6a4f851
ms.sourcegitcommit: d91436de68a0e833ecff18d976de9d9431bc4121
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/06/2017
---
# <a name="google-analytics-connector-for-power-bi-desktop"></a>Google Analytics-anslutningsprogram för Power BI Desktop
> [!NOTE]
> Innehållspaketet och anslutningen för Google Analytics i Power BI Desktop använder sig av Google Analytics Core Reporting API. Det innebär att funktioner och tillgänglighet kan variera över tid.
> 
> 

Du kan ansluta till Google Analytics-data med hjälp av **Google Analytics**-anslutningsprogrammet. Gör så här för att ansluta:

1. I **Power BI Desktop** väljer du **Hämta data** från fliken **Start** i menyfliksområdet.
2. I fönstret **Hämta data** väljer du **Övrigt** från kategorierna i det vänstra fönstret.
3. Välj **Google Analytics** från alternativen i det högra fönstret.
4. Längst ned i fönstret väljer du **Anslut**.  
   ![](media/service-google-analytics-connector/tps_googleanalytics_1.png)

En dialogruta visas som förklarar att anslutningsprogrammet är en tredjepartstjänst, varnar om hur funktioner och tillgänglighet kan ändras med tiden samt andra förtydliganden.  
![](media/service-google-analytics-connector/tps_googleanalytics_2.png)

När du väljer **Fortsätt** uppmanas du att logga in på Google Analytics.  
![](media/service-google-analytics-connector/tps_googleanalytics_3.png)

När du anger dina autentiseringsuppgifter visas ett meddelande om att Power BI vill ha offlineåtkomst. Detta är hur du använder **Power BI Desktop** för att få åtkomst till dina Google Analytics-data.  

När du har accepterat visar **Power BI Desktop** att du för närvarande är inloggad.  
![](media/service-google-analytics-connector/tps_googleanalytics_5.png)

Välj **Anslut**. Dina Google Analytics-data ansluts till **Power BI Desktop** och läser in datan.  
![](media/service-google-analytics-connector/tps_googleanalytics_6.png)

## <a name="changes-to-the-api"></a>Ändringar i API:n
Även om vi försöker släppa uppdateringar i takt med ändringarna, kan API:n ändras på ett sätt som påverkar resultaten för de frågor som vi genererar. I vissa fall kanske inte vissa frågor längre stöds. På grund av detta beroende kan vi inte garantera resultatet för dina frågor när du använder det här anslutningsprogrammet.

Mer information om ändringar i Google Analytics-API:n finns i deras [ändringslogg](https://developers.google.com/analytics/devguides/changelog).
