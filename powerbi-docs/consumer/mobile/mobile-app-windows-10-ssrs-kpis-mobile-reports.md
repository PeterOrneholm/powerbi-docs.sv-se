---
title: Visa lokala rapporter och KPI:er i Power BI Windows-appen
description: Power BI-mobilappen för Windows 10 erbjuder live, pekaktiverad mobil åtkomst till viktig lokal företagsinformation.
author: paulinbar
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: how-to
ms.date: 05/19/2020
ms.author: painbar
ms.openlocfilehash: a56fecdadc8eddba3fa755497a4ebc978496b7a1
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85231356"
---
# <a name="view-on-premises-reports-and-kpis-in-the-power-bi-windows-app"></a>Visa lokala rapporter och KPI:er i Power BI Windows-appen
Power BI-appen för Windows 10 erbjuder pekaktiverad live-mobilåtkomst till din viktiga lokala företagsinformation i SQL Server 2016 Reporting Services. 

![Reporting Services-mobila rapporter](media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-ssrs-mobile-report.png)

## <a name="first-things-first"></a>Vi tar det i ordning
[Skapa mobila rapporter i Reporting Services](/sql/reporting-services/mobile-reports/create-mobile-reports-with-sql-server-mobile-report-publisher) med SQL Server 2016 Enterprise Edition Mobile Report Publisher och publicerar dem på [Reporting Services-webbportalen](/sql/reporting-services/web-portal-ssrs-native-mode). Skapa KPI:er direkt i webbportalen. Sortera dem i mappar och markerar dina favoriter så att du enkelt kan hitta dem. 

I Power BI-appen för Windows 10 visar du sedan KPS, mobila rapporter och Power BI-rapporter, ordnade i mappar eller samlade som favoriter. 

> [!NOTE]
> Din enhet måste köra Windows 10. Appen fungerar bäst på enheter med minst 1 GB RAM-minne och 8 GB intern lagring.

>[!NOTE]
>Stöd för Power BI-mobilappen för **telefoner som använder Windows 10 Mobile** kommer att upphöra den 16 mars 2021. [Läs mer](https://go.microsoft.com/fwlink/?linkid=2121400)

## <a name="explore-samples-without-a-sql-server-2016-reporting-services-server"></a>Utforska prover utan en SQL Server 2016 Reporting Services-server
Även om du inte har åtkomst till en Reporting Services-webbportal, kan du fortfarande utforska funktionerna i Reporting Services-mobila rapporter.

1. På din Windows 10-enhet öppnar du Power BI-appen.
2. Tryck på den globala navigeringsknappen ![Den globala navigeringsknappen](media/mobile-app-windows-10-ssrs-kpis-mobile-reports/powerbi_windows10_options_icon.png) i det övre vänstra hörnet.
3. Tryck på ikonen **Inställningar**![Inställningsikonen](media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-settings-icon.png), högerklicka eller tryck och håll in **Anslut till server** och tryck sedan på **Visa exempel**.
   
   ![Visa SSRS-exempel](media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-win10-connect-ssrs-samples.png)
4. Öppna mappen för detaljhandelsrapporterna eller försäljningsrapporter om du vill utforska deras KPI:er och mobila rapporter.
   
   ![Exempel på KPI: er och mobila rapporter](media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-win10-ssrs-sample-kpis.png)

Bläddra exemplen för att interagera med KPI:er och mobila rapporter.

## <a name="connect-to-a-reporting-services-report-server"></a>Anslut till en Reporting Services-rapportserver
1. Tryck på **Inställningar** ![Inställningsikonen](media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-settings-icon.png) längst ned i navigeringsfönstret
2. Tryck på **Anslut till server**.
3. Fyll i serveradressen samt ditt användarnamn och lösenord. Använd följande format för serveradressen:
   
     `https://<servername>/reports` eller `https://<servername>/reports`
   
   > [!NOTE]
   > Inkludera **http** eller **https** framför anslutningssträngen.
   > 
   > 
   
    Tryck på **Avancerade alternativ** för att namnge servern, om du vill.
4. Tryck på bockmarkeringen för att ansluta. 
   
   Servern visas i navigeringsfönstret.
   
   ![Server i navigeringsfönster](media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-ssrs-mobile-report-server.png)
   
   >[!TIP]
   >Tryck på den globala navigeringsknappen ![Global navigeringsknapp](media/mobile-app-windows-10-ssrs-kpis-mobile-reports/powerbi_windows10_options_icon.png) när som helst för att gå mellan dina mobila rapporter i Reporting Services och dina instrumentpaneler i Power BI-tjänsten. 
   > 

   >[!NOTE]
   >Rapportservrar som konfigureras med anpassade portar stöds inte och kan inte nås från Power BI Windows-appen. 

## <a name="view-reporting-services-kpis-and-mobile-reports-in-the-power-bi-app"></a>Visa Reporting Services KPI:er och mobila rapporter i Power BI-appen
Reporting Services-KPI:er, mobila rapporter och Power BI-rapporter (förhandsversion) visas i motsvarande mappar till dem i vilka de finns i Reporting Services-webbportalen.

![Rapportmappar](media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-ssrs-mobile-report-folders.png)

* Tryck på en KPI för att se den i fokusläge.
  
    ![KPI i fokusläge](media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-ssrs-mobile-report-kpis.png)
* Tryck på en mobil rapport för att öppna och interagera med den i Power BI-appen.
  
    ![Reporting Services-mobil rapport](media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-ssrs-mobile-report.png)

## <a name="view-your-favorite-kpis-and-reports"></a>Se dina favorit-KPI:er och rapporter
Du kan markera KPI:er, mobila rapporter och Power BI-rapporter som favoriter i din Reporting Services-webbportal och sedan visa dem i en lämplig mapp på din Windows 10-enhet, tillsammans med dina Power BI-favoritinstrumentpaneler och rapporter.

* Tryck på **Favoriter**.
  
   ![Favoriter-ikonen](media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-ssrs-mobile-report-favorite-menu.png)
  
   Dina favoriter från webbportalen finns på den här sidan.
  
Läs mer om [favoriter i Power BI-mobilappar](mobile-apps-favorites.md).

## <a name="remove-a-connection-to-a-report-server"></a>Ta bort en anslutning till en rapportserver
Du kan bara vara ansluten till en rapportserver i taget från din Power BI-mobilapp. Om du vill ansluta till en annan server, måste du koppla från den nuvarande.

1. Tryck på **Inställningar** ![Inställningsikonen](media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-settings-icon.png) längst ned i navigeringsfönstret.
2. Tryck på namnet till den server som du inte vill vara ansluten till och håll in.
3. Tryck på **Ta bort server**.
   
    ![Ta bort server](media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-windows-10-ssrs-remove-server-menu.png)

## <a name="create-reporting-services-mobile-reports-and-kpis"></a>Skapa Reporting Services-mobila rapporter och KPI:er
Du skapar inte Reporting Services KPI:er och mobila rapporter i Power BI-appen. Du skapar dem i SQL Server Mobile Report Publisher och en SQL Server 2016 Reporting Services-webbportal.

* [Skapa dina egna Reporting Services-mobila rapporter](/sql/reporting-services/mobile-reports/create-mobile-reports-with-sql-server-mobile-report-publisher) och publicera dem till Reporting Services-webbportalen.
* Skapa [KPI:er på en Reporting Services-webbportal](/sql/reporting-services/working-with-kpis-in-reporting-services)

## <a name="next-steps"></a>Nästa steg
* [Kom igång med Power BI-mobilappen för Windows 10](mobile-windows-10-phone-app-get-started.md)  
* [Vad är Power BI?](../../fundamentals/power-bi-overview.md)  
* Har du några frågor? [Fråga Power BI Community](https://community.powerbi.com/)
