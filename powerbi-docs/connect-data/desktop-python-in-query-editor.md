---
title: Använda Python i frågeredigeraren för Power BI
description: Använda Python i frågeredigeraren för Power BI Desktop till avancerade analyser
author: otarb
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: how-to
ms.date: 06/18/2018
ms.author: otarb
LocalizationGroup: Connect to data
ms.openlocfilehash: 6e1c18f61cc822cd9656a49a65c98b225709c540
ms.sourcegitcommit: c83146ad008ce13bf3289de9b76c507be2c330aa
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/10/2020
ms.locfileid: "86215496"
---
# <a name="use-python-in-query-editor"></a>Använda Python i frågeredigeraren
Du kan använda **Python**, ett programmeringsspråk som ofta används av statistiker, dataforskare och dataanalytiker, i **frågeredigeraren** för Power BI Desktop. Med den här integreringen av Python i **frågeredigeraren** kan du utföra datarensning med Python, avancerade datautformning och analyser i datauppsättningar, inklusive färdigställande av saknade data, förutsägelser och klustring för att bara nämna några få. **Python** är ett kraftfullt språk och kan användas i **frågeredigeraren** till att förbereda din datamodell och skapa rapporter.

## <a name="installing-python"></a>Installera Python
För att kunna använda **Python** i Power BI Desktops **frågeredigerare**, måste du installera **Python** på den lokala datorn. Du kan hämta och installera **Python** kostnadsfritt från flera platser, inklusive den [officiella hämtningssidan för Python](https://www.python.org/) och [Anaconda](https://anaconda.org/anaconda/python/).

## <a name="using-python-in-query-editor"></a>Använda Python i frågeredigeraren
För att visa hur du använder **Python** i **frågeredigeraren** anges det här exemplet på en datauppsättning från aktiemarknaden som baseras på en .CSV-fil, som du kan [ladda ned här](https://download.microsoft.com/download/F/8/A/F8AA9DC9-8545-4AAE-9305-27AD1D01DC03/EuStockMarkets_NA.csv) och följa. Stegen i detta exempel är följande:

1. Först läser du in dina data i **Power BI Desktop**. I det här exemplet läser du in filen *EuStockMarkets_NA.csv* och väljer **Hämta data > CSV** på menyfliken **Start** i **Power BI Desktop**.
   
   ![Skärmbild av menyfliksområdet Hämta data i Power BI Desktop med valet CSV.](media/desktop-python-in-query-editor/python-in-query-editor-1.png)
2. Markera filen och välj **Öppna**. CSV:n visas i dialogrutan **CSV-fil**.
   
   ![Skärmbild av dialogrutan CSV-fil som visar vald CSV-fil.](media/desktop-python-in-query-editor/python-in-query-editor-2.png)
3. När datan har lästs in visas den i fönstret **Fält** i Power BI Desktop.
   
   ![Skärmbild av rutan Fält med inlästa data.](media/desktop-python-in-query-editor/python-in-query-editor-3.png)
4. Öppna **Frågeredigeraren** genom att välja **Redigera frågor** på fliken **Start** i **Power BI Desktop**.
   
   ![Skärmbild av Frågeredigeraren i Power BI Desktop med Redigera frågor valt.](media/desktop-python-in-query-editor/python-in-query-editor-4.png)
5. På fliken **Transformera** väljer du **Kör Python-skript**. Redigeringsprogrammet **Kör Python-skript** öppnas (visas i nästa steg). Observera att det saknas data på raderna 15 och 20, vilket det även gör på andra rader som du inte kan se i följande bild. Stegen nedan visar hur Python kan (och kommer) att slutföra dem åt dig.
   
   ![Skärmbild av fliken Transformera med datarader.](media/desktop-python-in-query-editor/python-in-query-editor-5.png)
6. I det här exemplet anger du följande skriptkod:
   
    ```python
       import pandas as pd
       completedData = dataset.fillna(method='backfill', inplace=False)
       dataset["completedValues"] =  completedData["SMI missing values"]
   ```

   > [!NOTE]
   > Du måste ha biblioteket *pandas* installerat i din Python-miljö för att tidigare skriptkod ska fungera korrekt. För att installera pandas, kör du följande kommando i din Python-installation: |      > pip install pandas
   > 
   > 
   
   När koden infogas i dialogrutan **Kör Python-skript** ser den ut ungefär så här:
   
   ![Skärmbild av dialogrutan Kör Python-skript med skriptkoden.](media/desktop-python-in-query-editor/python-in-query-editor-5b.png)
7. När du har valt **OK** visar **frågeredigeraren** en varning om datasekretess.
   
   ![Skärmbild av Frågeredigeraren med en varning om datasekretess.](media/desktop-python-in-query-editor/python-in-query-editor-6.png)
8. För att Python-skript ska fungera korrekt i Power BI-tjänsten måste alla datakällor anges som *offentliga*. Mer information om sekretessinställningar och deras konsekvenser finns i [Sekretessnivåer](../admin/desktop-privacy-levels.md).
   
   ![Skärmbild av dialogrutan Sekretessnivåer och Offentlig valt.](media/desktop-python-in-query-editor/python-in-query-editor-7.png)
   
   Observera en ny kolumn i fönstret **Fält** med namnet *completedValues*. Observera att det är några dataelement som saknas, t.ex på rad 15 och 18. Ta en titt på hur Python hanterar det i nästa avsnitt.
   

Trots att vi bara har fem rader med Python-skript kan **frågeredigeraren** fylla i saknade värden med en förutsägelsemodell.

## <a name="creating-visuals-from-python-script-data"></a>Skapa visuella objekt från Python-skriptdata
Nu kan vi skapa ett visuellt objekt för att se hur Python-skriptkoden använder biblioteket *pandas* till att fylla i saknade värden, enligt följande bild:

![Skärmbild av kontrollen med ursprungliga data och ifyllda saknade värden för biblioteket pandas.](media/desktop-python-in-query-editor/python-in-query-editor-8.png)

När det visuella objektet är klart och även övriga visuella objekt som du vill skapa med **Power BI Desktop**, kan du spara **Power BI Desktop**-filen (som en .pbix-fil) och sedan använda datamodellen, inklusive de Python-skript som ingår i den, i Power BI-tjänsten.

> [!NOTE]
> Vill du se en färdig .pbix-fil där de här stegen har slutförts? I så fall kan du ladda ned den slutförda **Power BI Desktop**-filen som användes i de här exemplen [till höger här](https://download.microsoft.com/download/A/B/C/ABCF5589-B88F-49D4-ADEB-4A623589FC09/Complete%20Values%20with%20Python%20in%20PQ.pbix).

När du har överfört .pbix-filen till Power BI-tjänsten, krävs det några fler steg för att datauppdatering ska aktiveras (i tjänsten) och för att aktivera att visuella objekt uppdateras i tjänsten (datan behöver åtkomst till Python för att de visuella objekten ska uppdateras). De extra stegen är följande:

* **Aktivera schemalagd uppdatering för datauppsättningen** – För att aktivera schemalagd uppdatering för den arbetsbok som innehåller datauppsättningen med Python-skript, se [Konfigurera schemalagd uppdatering](refresh-scheduled-refresh.md), som även innehåller information om **Personlig gateway**.
* **Installera personlig gateway** – Du behöver en **Personlig gateway** installerad på datorn där filen finns och där Python har installerats. Power BI-tjänsten måste komma åt arbetsboken och kunna återge uppdaterade visuella objekt på nytt. Du kan få mer information om hur du [installerar och konfigurerar en personlig gateway](service-gateway-personal-mode.md).

## <a name="limitations"></a>Begränsningar
Det finns vissa begränsningar för frågor med Python-skript som skapats i **frågeredigeraren**:

* Alla Python-inställningar för datakällan måste anges som *offentliga* och alla andra steg i en fråga som skapats i **frågeredigeraren** måste också vara offentliga. Gå till inställningar för datakällan i **Power BI Desktop** genom att välja **Fil > Alternativ och inställningar > Datakällsinställningar**.
  
  ![Skärmbild av menyn Arkiv i Power BI Desktop med Datakällsinställningar valt.](media/desktop-python-in-query-editor/python-in-query-editor-9.png)
  
  I dialogrutan **Datakällsinställningar** markerar du datakällorna och väljer sedan **Redigera behörigheter...** . Kontrollera att **Sekretessnivå** är inställd som *Offentlig*.
  
  ![Skärmbild av dialogrutan Datakällsinställningar där Offentlig är valt som Sekretessnivå.](media/desktop-python-in-query-editor/python-in-query-editor-10.png)    
* Om du vill aktivera schemalagd uppdatering av visuella Python-objekt eller datauppsättningar, måste du aktivera **Schemalagd uppdatering** och installera en **Personlig gateway** på datorn där arbetsboken och Python-installationen finns. Mer information om detta finns i föregående avsnitt i den här artikeln, med länkar till mer information om var och en.
* Kapslade tabeller (tabell över tabeller) stöds inte för tillfället 

Det finns olika saker du kan göra med Python och egna frågor, så utforska och utforma dina data precis som du vill att de ska visas.
