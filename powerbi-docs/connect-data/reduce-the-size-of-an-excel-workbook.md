---
title: Minska storleken på en Excel-arbetsbok för att visa den i Power BI
description: Minska storleken på en Excel-arbetsbok för att visa den i Power BI
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: how-to
ms.date: 01/10/2019
ms.author: davidi
LocalizationGroup: Data from files
ms.openlocfilehash: 7755834f5d76392f7212073f958d3c4070dcaca7
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85234788"
---
# <a name="reduce-the-size-of-an-excel-workbook-to-view-it-in-power-bi"></a>Minska storleken på en Excel-arbetsbok för att visa den i Power BI
Du kan ladda upp Excel-arbetsböcker som är mindre än 1 GB till Power BI. En Excel-arbetsbok kan ha två delar: en datamodell och resten av rapporten. Arbetsbokens kärninnehåll. Om rapporten uppfyller följande storleksgränser, kan du spara den till **OneDrive för företag**, ansluta till den från Power BI och visa den i Excel Online:

* Arbetsboken som helhet kan vara upp till 1 GB.
* Arbetsbokens kärninnehåll kan vara upp till 30 MB.

## <a name="what-makes-core-worksheet-contents-larger-than-30-mb"></a>Vad gör arbetsbokens kärninnehåll större än 30 MB
Här följer några element som kan göra att arbetsbokens kärninnehåll är större än 30 MB:

* Bilder.
* Skuggade celler. [Ta bort ett cellskuggningsformat](https://support.office.com/article/Add-or-change-the-background-color-of-cells-ac10f131-b847-428f-b656-d65375fb815e).
* Färgade kalkylblad. [Ta bort ett arks bakgrund](https://support.office.com/article/add-or-remove-a-sheet-background-3577a762-8450-4556-96a2-cc265abc00a8).
* Textrutor.
* Clip-art.

Överväg att ta bort de här elementen om möjligt. 

Om rapporten innehåller en datamodell, finns det några andra alternativ: 

* Ta bort data från Excel-kalkylbladen och lagra dem i datamodellen i stället. Mer information finns i ta bort data från kalkylblad nedan. 
* [Skapa en minneseffektiv datamodell](https://support.office.com/article/Create-a-memory-efficient-Data-Model-using-Excel-2013-and-the-Power-Pivot-add-in-951c73a9-21c4-46ab-9f5e-14a2833b6a70) för att minska den sammanlagda storleken för rapporten.

Om du vill göra dessa ändringar, måste du redigera arbetsboken i Excel.

Läs mer om [filstorleksgränser för Excel-arbetsböcker i SharePoint Online](https://support.office.com/article/File-size-limits-for-workbooks-in-SharePoint-Online-9e5bc6f8-018f-415a-b890-5452687b325e).

## <a name="remove-data-from-worksheets"></a>Ta bort data från kalkylblad
Om du importerar data till Excel från Power Query-fliken eller Excel Data-fliken, kanske arbetsboken har samma data i en Excel-tabell och i datamodellen. Stora tabeller i Excel-kalkylblad kan göra att kalkylbladets kärninnehåll blir större än 30 MB. Om du tar bort tabellen i Excel och behåller data i datamodellen, kan du avsevärt minska kalkylbladet kärninnehåll i rapporten. 

Följ dessa tips när du importerar data till Excel:

* **I Power Query**: Rensa rutan **Läs in i kalkylblad**.
  
  Data importeras endast till datamodellen, utan data i Excel-kalkylbladen.
* **Från Excel Data-fliken**, om du tidigare har markerat **Tabell** i Importguiden: Gå till **Befintliga anslutningar**\> och klicka på \> **Skapa endast anslutning**. Ta bort den ursprungliga tabellen eller tabellerna som skapades under den initiala importen.
* **På Excel Data-fliken**: markera inte **tabell** i rutan **importera data**.

## <a name="workbook-size-optimizer"></a>Arbetsbokens storleksoptimering
Om din arbetsbok innehåller en datamodell, kan du köra arbetsbokens storleksoptimering för att minska storleken på din arbetsbok. [Hämta arbetsbokens storleksoptimering](https://www.microsoft.com/download/details.aspx?id=38793).

## <a name="related-info"></a>Relaterad information
[Skapa en minneseffektiv datamodell](https://support.office.com/article/Create-a-memory-efficient-Data-Model-using-Excel-2013-and-the-Power-Pivot-add-in-951c73a9-21c4-46ab-9f5e-14a2833b6a70)

[Använd OneDrive för företag-länkar i Power BI Desktop](desktop-use-onedrive-business-links.md)

