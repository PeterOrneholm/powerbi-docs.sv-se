---
title: Azure SQL Database med DirectQuery
description: Azure SQL Database med DirectQuery
services: powerbi
documentationcenter: 
author: guyinacube
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
ms.date: 12/18/2017
ms.author: asaxton
ms.openlocfilehash: 6ee8ab6d30d84857de9cd415ee58caade4e94a57
ms.sourcegitcommit: ea247cb3cfc1cac076d4b076c1ad8e2fc37e15a1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/19/2017
---
# <a name="azure-sql-database-with-directquery"></a>Azure SQL Database med DirectQuery
Här kan du lära dig hur du kan ansluta direkt till Azure SQL Database och skapa rapporter med realtidsdata. Du kan hålla dina data vid källan och inte i Power BI.

Med DirectQuery skickas frågor tillbaka till din Azure SQL Database medan du utforskar dessa data i rapportvyn. Den här användningen föreslås för användare som är bekanta med databaser och de enheter som de ansluter till.

**OBS:**

* Ange det fullständigt kvalificerade servernamnet vid anslutning (se nedan för mer information)
* Se till att brandväggsreglerna för databasen är konfigurerade för ”[Tillåt åtkomst till Azure-tjänster](https://msdn.microsoft.com/library/azure/ee621782.aspx)”.
* Varje åtgärd, som att markera en kolumn eller lägga till ett filter, skickar en fråga tillbaka till databasen
* Panelerna uppdateras varje timme (uppdateringen behöver inte schemaläggas). Detta kan justeras i Avancerade inställningar när du ansluter.
* Frågor och svar är inte tillgänglig för DirectQuery-datauppsättningar
* Schemaändringar plockas inte upp automatiskt.

Dessa begränsningar och anteckningar kan ändras när vi fortsätter att förbättra upplevelsen. Stegen för att ansluta beskrivs nedan. 

## <a name="power-bi-desktop-and-directquery"></a>Power BI Desktop och DirectQuery
För att ansluta till Azure SQL Database med DirectQuery, behöver du använda Power BI Desktop. Den här metoden erbjuder ytterligare flexibilitet och funktioner. Rapporter som skapas med Power BI Desktop kan senare publiceras i Power BI-tjänsten. Du kan lära dig mer om hur du ansluter till [Azure SQL Database med DirectQuery](desktop-use-directquery.md) i Power BI Desktop. 

## <a name="single-sign-on"></a>Enkel inloggning

När du har publicerat en Azure SQL DirectQuery-datauppsättning till tjänsten, kan du aktivera enkel inloggning (SSO) via Azure Active Directory (AD Azure) OAuth2 för dina slutanvändare. 

Om du vill aktivera enkel inloggning går du till datauppsättningens inställningar, öppnar fliken **Datakällor** och markerar rutan för enkel inloggning.

![Konfigurera Azure SQL DQ-dialogrutan](media/service-azure-sql-database-with-direct-connect/sso-dialog.png)

När alternativet för enkel inloggning är aktiverat och dina användares åtkomstrapporter har skapats ovanpå datakällan, skickar Power BI sina autentiserade autentiseringsuppgifter för Microsoft Azure Active Directory i frågorna till Azure SQL-databasen. Detta möjliggör för Power BI att respektera säkerhetsinställningarna som är konfigurerade på datakällsnivå.

Alternativet för enkel inloggning börjar fungera för alla datauppsättningar som använder den här datakällan. Autentiseringsmetoden som används för importscenarier påverkas inte.

## <a name="finding-parameter-values"></a>Hitta parametervärden
Det fullständigt kvalificerade servernamnet och databasnamnet återfinns i Azure Portal.

![](media/service-azure-sql-database-with-direct-connect/azureportnew_update.png)

![](media/service-azure-sql-database-with-direct-connect/azureportal_update.png)

## <a name="next-steps"></a>Nästa steg
[Använda DirectQuery i Power BI Desktop](desktop-use-directquery.md)  
[Kom igång med Power BI](service-get-started.md)  
[Hämta data för Power BI](service-get-data.md)  
Har du fler frågor? [Prova Power BI Community](http://community.powerbi.com/)