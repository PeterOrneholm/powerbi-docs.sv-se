---
title: Få Excel-data att fungera med Frågor och svar i Power BI
description: Så här får du dina data att fungera bra med frågor och svar i Power BI
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: how-to
ms.date: 05/13/2019
ms.author: maggies
LocalizationGroup: Ask questions of your data
ms.openlocfilehash: f7760021966673b93313809a806473b94c7750d3
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85218710"
---
# <a name="make-excel-data-work-well-with-qa-in-power-bi"></a>Få Excel-data att fungera med Frågor och svar i Power BI
Om du är en person som skapar datamodeller eller bygger Excel-arbetsböcker som ska användas med Power BI kan du läsa på...

I Power BI kan du med vanliga frågor och svar söka efter strukturerade data och välja rätt visualisering för din fråga – det är det som gör det till ett sådant fascinerande verktyg att arbeta med.   

Frågor och svar fungerar på alla överförda Excel-filer som innehåller tabeller, intervall eller PowerPivot-modeller, men ju fler optimeringar och datarensningar du gör, desto mer robust prestandan för frågor och svar.  Om du planerar att dela rapporter och instrumentpaneler baserat på din datauppsättning, vill du att dina kollegor lätt kan ställa frågor och få kvalitetssvar.

## <a name="how-qa-works-with-excel"></a>Så här fungerar frågor och svar med Excel
Frågor och svar har en uppsättning kärnfunktioner som förstår naturligt språk och som arbetar med dina data. Det har kontextberoende nyckelordssökning för dina Excel-tabeller, kolumner och beräknade fältnamn. Dessutom har det inbyggd kunskap för att filtrera, sortera, aggregera, gruppera och visa data. 

I exempelvis en Excel-tabell med namnet ”Försäljning” och kolumnerna ”Produkt”, ”Månad”, ”Sålda enheter”, ”Bruttoförsäljning” och ”Resultat” kan du ställa frågor om någon av dessa entiteter.  Du kan begära att försäljning eller total vinst per månad ska visas, att produkterna sorteras efter sålda enheter och mycket annat. Läs mer om att [använda Frågor och svar i instrumentpaneler och rapporter](power-bi-tutorial-q-and-a.md) och [vilka visualiseringstyper som du kan ange i en Frågor och svar-fråga](../visuals/power-bi-visualization-types-for-reports-and-q-and-a.md).

## <a name="prepare-an-excel-dataset-for-qa"></a>Förbered en Excel-datauppsättning för frågor och svar
Funktionen Frågor och svar använder sig av namnen på tabeller, kolumner och beräknade fält när den besvarar dataspecifika frågor, vilket innebär att det du kallar entiteter i din arbetsbok är viktigt!

Här får du några tips om hur du kan utnyttja Frågor och svar på bästa sätt i din arbetsbok.

* Kontrollera att dina data finns i en Excel-tabell. Så här [skapar du en Excel-tabell](https://support.office.com/article/Create-an-Excel-table-in-a-worksheet-e81aa349-b006-4f8a-9806-5af9df0ac664).
* Kontrollera att namnen på dina tabeller, kolumner och beräknade fält är logiska med naturligt språk.
  
  Om du t.ex. har en tabell med försäljningsdata, så anropa tabellen ”Sales”. Kolumnnamn som “Year”, “Product”, “Sales Rep”, och “Amount” fungerar väl med Frågor och svar.

* Om arbetsboken har en Power Pivot-datamodell, kan du göra ytterligare optimeringar. Läs mer i [Avmystifiera Power BI Q&A, del 2](https://powerbi.microsoft.com/blog/demystifying-power-bi-q-amp-a-part-2/) från vårt interna expertteam när det gäller naturligt språk.

* Öppna datamängden i Power BI Desktop och skapa nya kolumner, skapa mått, skapa unika värden genom att sammanfoga fält, klassificera data efter typ (t.ex. datum, strängar, geografi, bilder, URL:er) och mycket annat.

## <a name="next-steps"></a>Nästa steg

- [Frågor och svar för konsumenter](../consumer/end-user-q-and-a.md)  
- [Använda Frågor och svar på instrumentpaneler och i rapporter](power-bi-tutorial-q-and-a.md)
- [Förbereda lokala datamängder för Frågor och svar](service-q-and-a-direct-query.md)   
- [Hämta data (för Power BI)](../connect-data/service-get-data.md)  

Har du fler frågor? [Prova Power BI Community](https://community.powerbi.com/)
