---
title: "Kom igång med Power BI-tjänsten"
description: "Kom igång med Power BI-tjänsten"
services: powerbi
documentationcenter: 
author: adamw
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: B2vd4MQrz4M
qualityfocus: monitoring
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: get-started-article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/23/2017
ms.author: mihart
ms.openlocfilehash: ee7375c28b3c13b53eba52f0bf76754529c9b4f5
ms.sourcegitcommit: 74fbbca81a056dda19b3647ae058005aba5296f5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/03/2018
---
# <a name="get-started-with-power-bi-service-apppowerbicom"></a>Kom igång med Power BI-tjänsten (app.powerbi.com)
Dessa självstudier hjälper dig att komma igång med ***Power BI-tjänsten***. Om du vill förstå hur Power BI-tjänsten passar ihop med andra Power BI-erbjudanden, så rekommenderar vi starkt att du börjar med att läsa [Vad är Power BI](guided-learning/gettingstarted.yml#step-1).

![](media/service-get-started/power-bi-components.png)

Power BI-tjänsten finns i en kostnadsfri version och en Pro-version. *Om du redan har ett konto* öppnar du en webbläsare och skriver in app.powerbi.com för att öppna Power BI-tjänsten, oavsett vilken version du använder. Om du är ny som användare rekommenderar vi att du börjar på www.powerbi.com i stället. Härifrån kan du lära dig mer om Power BI innan du loggar in till tjänsten.  När du är redo att testa den, väljer du länken **Registrera dig kostnadsfritt** som du ser i det övre högra hörnet. Om administratören redan har aktiverat Power BI för dig, använder du inte knappen Registrera dig kostnadsfritt, utan går i stället direkt till app.powerbi.com. 

![](media/service-get-started/power-bi-sign-up.png)

Om du behöver hjälp med Power BI Desktop, så läs [Kom igång med Desktop](desktop-getting-started.md). Om du behöver hjälp med Power BI Mobile, så läs [Power BI-appar för mobila enheter](mobile-apps-for-mobile-devices.md).

> [!TIP]
> Föredrar du en kostnadsfri självstudiekurs istället? [Registrera dig för vår kurs Analysera och visualisera data på EdX](http://aka.ms/edxpbi).

Besök vår [spelningslista på YouTube](https://www.youtube.com/playlist?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP). En bra video är att börja med är Introduktion till Power BI-tjänsten:
> 
> <iframe width="560" height="315" src="https://www.youtube.com/embed/B2vd4MQrz4M" frameborder="0" allowfullscreen></iframe>
> 
> 
> 

Microsoft Power BI hjälper dig att hålla dig uppdaterad med den information som är viktig för dig.  Tack vare Power BI-tjänsten hjälper ***instrumentpanelerna*** dig att ha koll på verksamhetens puls.  Instrumentpanelerna visar ***paneler*** i vilka du kan öppna ***rapporter*** genom att klicka, för att sedan utforska vidare.  Anslut till flera ***datauppsättningar*** så att alla relevanta data samlas på samma plats. Behöver du hjälp att förstå de olika byggstenarna i Power BI?  Mer information finns i [Power BI – grundläggande begrepp](service-basic-concepts.md).

Om du har viktiga data i Excel- eller CSV-filer, så kan du skapa en Power BI-instrumentpanel så att du kan hålla dig informerad var du än befinner dig och dela information med andra.  Prenumererar du på ett SaaS-program som Salesforce?  Kom igång direkt genom att ansluta till Salesforce och automatiskt skapa en instrumentpanel från dessa data, eller [ta en närmare titt på alla andra SaaS-appar](service-get-data.md) som du kan ansluta till. Om du arbetar för en organisation kan du kontrollera om några [appar](service-create-distribute-apps.md) har publicerats för dig.

Läs mer om alla andra sätt att [hämta data på för Power BI](service-get-data.md).

## <a name="step-1-get-data"></a>Steg 1: Hämta data
Här är ett exempel på hämtning av data från en CSV-fil. Vill du följa den här självstudien? [Hämta den här CSV-exempelfilen](http://go.microsoft.com/fwlink/?LinkID=521962).

1. [Logga in till Power BI](http://www.powerbi.com/). Har du inte något konto? Inga problem, du kan registrera dig kostnadsfritt.
2. Power BI öppnas i webbläsaren. Välj **Hämta data** längst ned i det vänstra navigeringsfältet.
   
   ![](media/service-get-started/getdata3.png)
3. Välj **Filer**. 
   
   ![](media/service-get-started/gs1.png)
4. Bläddra till filen på datorn och välj **Öppna**. Om du har sparat den i OneDrive för företag, väljer du det alternativet. Om du har sparat den lokalt, väljer du **Lokal fil**. 
   
   ![](media/service-get-started/gs2.png)
5. I den här självstudien väljer vi **Importera** så att vi kan lägga till Excel-filen som en datauppsättning som vi sedan kan använda för att skapa rapporter och instrumentpaneler. Om du väljer **Ladda upp** överförs hela Excel-arbetsboken till Power BI, där du kan öppna och redigera den i Excel Online.
   
   ![](media/service-get-started/power-bi-import.png)
6. När din datauppsättning är klar öppnar du den i rapportredigeraren genom att välja **Visa datauppsättning**. 

    ![](media/service-get-started/power-bi-gs.png)

    Eftersom vi inte har skapat några visualiseringar än är rapportarbetsytan tom.

    ![](media/service-get-started/power-bi-report-editor.png)

6. Ta en titt på den översta menyraden och lägg märke till att det finns ett alternativ som heter **Läsvy**. Eftersom alternativet Läsvy visas, innebär det att du för närvarande befinner dig i **redigeringsvyn**. 

    ![](media/service-get-started/power-bi-editing-view.png)

    I redigeringsvyn kan du skapa och ändra dina rapporter eftersom du är *ägare* till rapporterna. Det är du som är *skaparen*. När du delar din rapport med kollegor kan de bara interagera med rapporten i läsvyn. De är *konsumenter*. Lär dig mer om [Läsvy och Redigeringsvy](service-reading-view-and-editing-view.md).
    
    Ett bra sätt för dig att bekanta dig med rapportredigeraren är att [ta en rundtur](service-the-report-editor-take-a-tour.md)
   > 
 

## <a name="step-2-start-exploring-your-dataset"></a>Steg 2: Börja utforska din datauppsättning
Nu när du har anslutit till dina data kan du börja utforska omgivningarna.  När du har hittat något intressant, kan du skapa en instrumentpanel för att övervaka det och se hur det ändras med tiden. Nu ska vi se hur det fungerar.
    
1. I rapportredigeraren använder vi fönstret **Fält** till höger på sidan för att skapa en visualisering.  Markera kryssrutan intill **Bruttoförsäljning** och **Datum**.
   
   ![](media/service-get-started/fields.png)

2. Power BI analyserar informationen och skapar en visualisering.  Om du markerade **Datum** först, så visas en tabell.  Om du markerade **Bruttoförsäljning** först, så visas ett diagram. Växla till ett annat sätt att visa dina data. Nu visar vi dessa data som ett linjediagram. Välj linjediagramsikonen (kallas även mall) från **visualiseringsfönstret**.
   
   ![](media/service-get-started/gettingstart5new.png)

3. Det ser intressant ut så vi *fäster* det på en instrumentpanel. Hovra över visualiseringen och välj **stiftikonen**.  När du har fäst visualiseringen sparas den på instrumentpanelen och hålls uppdaterad så att du kan spåra det senaste värdet direkt.
   
   ![](media/service-get-started/pinnew.png)

5. Eftersom detta är en ny rapport uppmanas du att spara den innan du kan fästa en visualisering på instrumentpanelen. Ge rapporten ett namn (till exempel *Försäljning över tid*) och välj **Spara och fortsätt**. 
   
   ![](media/service-get-started/pbi_getstartsaveb4pinnew.png)
   
6. Vi fäster linjediagrammet på en ny instrumentpanel och ger det namnet ”Ekonomiskt exempel för självstudier”. 
   
   ![](media/service-get-started/power-bi-pin.png)
   
 1. Välj **fäst**.
   
    Genom ett meddelande (nära det övre högra hörnet) får du reda på att visualiseringen har lagts till, som en panel, på instrumentpanelen.
   
    ![](media/service-get-started/power-bi-pin-success.png)

8. Välj **Gå till instrumentpanelen** för att se linjediagrammet fäst, som en panel, på din helt nya instrumentpanel. Du kan göra instrumentpanelen ännu bättre genom att lägga till fler visualiseringspaneler och [byta namn och storlek på dem, länka till dem och placera om dem](service-dashboard-edit-tile.md).
   
   ![](media/service-get-started/power-bi-new-dashboard.png)
   
   Välj den nya panelen på instrumentpanelen och gå tillbaka till rapporten. Power BI för dig tillbaka till rapportredigeraren i läsvyn. Om du vill växla tillbaka till redigeringsvyn, väljer du **Redigera rapporten** från den översta menyraden. När du befinner dig i redigeringsvyn igen kan du fortsätta att utforska och fästa paneler. 

## <a name="step-3--continue-the-exploration-with-qa-natural-language-querying"></a>Steg 3: Fortsätt att utforska med Frågor och svar (frågor på naturligt språk)
1. Om du vill utforska dina data snabbt, så försök med att ställa en fråga i rutan Frågor och svar. Frågerutan för Frågor och svar är placerad längst upp på instrumentpanelen (**Ställ en fråga om dina data**) och i menyraden överst i rapporten (**Ställ en fråga**). Försök till exempel att skriva ”vilket segment hade mest intäkter”.
   
   ![](media/service-get-started/powerbi-qna.png)

2. Frågor och svar söker efter svar och visar dem i form av en visualisering. Välj fästikonen ![](media/service-get-started/pbi_pinicon.png) om du även vill visa den här visualiseringen på instrumentpanelen.
3. Fäst visualiseringen på instrumentpanelen ”Ekonomiskt exempel för självstudier”.
   
    ![](media/service-get-started/power-bi-pin2.png)

4. Gå tillbaka till instrumentpanelen där du ser den nya panelen.

   ![](media/service-get-started/power-bi-final-dashboard.png)

## <a name="next-steps"></a>Nästa steg
Är du redo att testa mer?  Här följer några bra exempel på hur du kan utforska Power BI.

* [Ansluta till en annan datauppsättning](service-get-data.md).
* [Dela instrumentpanelen](service-share-dashboards.md) med dina kollegor.
* Läs [Tips om att utforma instrumentpaneler](service-dashboards-design-tips.md).
* Visa dina instrumentpaneler med en [Power BI-app på en mobil enhet](mobile-apps-for-mobile-devices.md)

Är du inte riktigt redo än? Börja med dessa ämnen som hjälper dig att känna dig bekväm med Power BI.

* [Lär dig hur rapporter, datauppsättningar, instrumentpaneler och fönster fungerar ihop](service-basic-concepts.md)
* Besök vår [interaktiva utbildning för Power BI](guided-learning/index.md) och ta ett par (korta) kurser
* Titta på [Power BI-videor](videos.md)
* [Se vilka tillgängliga exempel som du kan använda](sample-datasets.md)

### <a name="stay-in-touch-with-power-bi"></a>Hålla kontakten med Power BI
* Följ [@MSPowerBI på Twitter](https://twitter.com/mspowerbi)
* Prenumerera på vår [YouTube-video-kanal](https://www.youtube.com/channel/UCy--PYvwBwAeuYaR8JLmrfg)
* Titta på våra på begäran-webbseminarier [Power BI Komma igång](webinars.md)
* Vet du inte var du hittar hjälp? Läs sidan [10 tips om att få hjälp](service-tips-for-finding-help.md)

Har du fler frågor? [Fråga Power BI Community](http://community.powerbi.com/)
