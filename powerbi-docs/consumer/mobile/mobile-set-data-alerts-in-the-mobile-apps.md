---
title: Ställa in dataaviseringar i Power BI-mobilapparna
description: Läs hur du ställer in aviseringar i Power BI-mobilappar för att meddela dig när data i en instrumentpanel ändras utanför de gränser du ställer in.
author: paulinbar
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: how-to
ms.date: 12/11/2019
ms.author: painbar
ms.openlocfilehash: 3d1c1919b5a940bc4ed6c5b0de9bd0af6444af00
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85220067"
---
# <a name="set-data-alerts-in-the-power-bi-mobile-apps"></a>Ställa in dataaviseringar i Power BI-mobilapparna
Gäller för:

| ![iPhone](./media/mobile-set-data-alerts-in-the-mobile-apps/iphone-logo-50-px.png) | ![iPad](./media/mobile-set-data-alerts-in-the-mobile-apps/ipad-logo-50-px.png) | ![Android-telefon](./media/mobile-set-data-alerts-in-the-mobile-apps/android-phone-logo-50-px.png) | ![Android-surfplatta](./media/mobile-set-data-alerts-in-the-mobile-apps/android-tablet-logo-50-px.png) | ![Android-surfplatta](./media/mobile-set-data-alerts-in-the-mobile-apps/win-10-logo-50-px.png) |
|:--- |:--- |:--- |:--- |:--- |
| iPhone-telefoner |iPad-surfplattor |Android-telefoner |Android-surfplattor |Windows 10-enheter |

Du kan ställa in aviseringar på instrumentpaneler i Power BI-mobilappar och i Power BI-tjänsten. Aviseringar meddelar dig när data i en panel ändras utanför de gränser. Aviseringar fungerar för paneler med ett tal, till exempel kort och mätare, men inte med direktöverförda data. Du kan ange dataaviseringar på din mobila enhet och se dem i Power BI-tjänsten och vice versa. Det är endast du som kan se de dataaviseringar som du ställer in, även om du delar en instrumentpanel eller en ögonblicksbild av en panel.

Du kan ställa in aviseringar på paneler om du har en Power BI Pro-licens, eller om den delade instrumentpanelen finns i en Premium-kapacitet. 

> [!WARNING]
> Datadrivna aviseringar ger information om dina data. Om enheten blir stulen bör du gå till Power BI-tjänsten och inaktivera alla regler för datadrivna aviseringar. 
> 
> Lär dig mer om att [hantera dataaviseringar i Power BI-tjänsten](../../create-reports/service-set-data-alerts.md).
> 
> 

## <a name="data-alerts-on-an-iphone-or-ipad"></a>Dataaviseringar på en iPhone eller iPad
### <a name="set-an-alert-on-an-iphone-or-ipad"></a>Ställa in dataaviseringar på en iPhone eller iPad
1. Tryck på en tal- eller mätarpanel på en instrumentpanel att öppna den i Fokusläge.  
   
   ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-iphone-card-visual.png)
2. Tryck på klockikonen ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-iphone-alert-icon.png) för att lägga till en avisering.  
3. Tryck på **Lägg till aviseringsregel**.
   
   ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-iphone-add-alert-rule.png)
4. Välj att ta emot aviseringar över eller under ett värde och ange sedan värdet.
   
   ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-iphone-set-alert-threshold.png)
5. Begär om du vill få aviseringar varje timme eller dag och om du vill få ett e-postmeddelande när du får aviseringen.
   
   > [!NOTE]
   > Du får inte aviseringar varje timme eller varje dag om data inte har uppdaterats vid den tiden.
   > 
   > 
6. Du kan också ändra aviseringens namn.
7. Tryck på **Spara**.
8. En panel kan ha aviseringar för värden både över och under tröskelvärden. I **Hantera aviseringar** trycker du på **Lägg till regel för avisering**.
   
   ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-iphone-add-another-alert-rule.png)

### <a name="manage-alerts-on-your-iphone-or-ipad"></a>Hantera aviseringar på din iPhone eller iPad
Du kan hantera enskilda aviseringar på din mobila enhet eller [hantera alla varningar i Power BI-tjänsten](../../create-reports/service-set-data-alerts.md).

1. Tryck på en tal- eller mätarpanel som har en avisering på instrumentpanelen.  
   
   ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-iphone-card-visual_has_alert.png)

2. Tryck på klockikonen ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-iphone-has-alert-icon.png).  
3. Tryck på namnet på aviseringen för att redigera den, tryck sedan på skjutreglaget för att stänga av e-postaviseringar eller på papperskorgen för att ta bort aviseringen.
   
    ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-iphone-edit-delete-alert.png)

## <a name="data-alerts-on-an-android-device"></a>Dataaviseringar på en Android-enhet
### <a name="set-an-alert-on-an-android-device"></a>Ställa in dataaviseringar på en Android-enhet
1. Tryck på en tal- eller mätarpanel på Power BI-instrumentpanelen för att öppna den.  
2. Tryck på klockikonen ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-android-alert-icon.png) för att lägga till en avisering.  
   
   ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-android-tap-alert.png)
3. Tryck på plusikonen (+).
   
   ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-android-plus-alert.png)
4. Välj att ta emot aviseringar över eller under ett värde och ange sedan värdet.
   
   ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-android-tablet-set-alert-condition.png)
5. Tryck på **Klar**.
6. Begär om du vill få aviseringar varje timme eller dag och om du vill få ett e-postmeddelande när du får aviseringen.
   
   > [!NOTE]
   > Du får inte aviseringar varje timme eller varje dag om data inte har uppdaterats vid den tiden.
   > 
   > 
7. Du kan också ändra aviseringens namn.
8. Tryck på **Spara**.

### <a name="manage-alerts-on-an-android-device"></a>Hantera dataaviseringar på en Android-enhet
Du kan hantera enskilda aviseringar i Power BI-appen eller [hantera alla varningar i Power BI-tjänsten](../../create-reports/service-set-data-alerts.md).

1. Tryck på en kort- eller mätarpanel som har en avisering på instrumentpanelen.  
2. Tryck på den fasta klockikonen ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-android-filled-alert-bell.png).  
3. Tryck på aviseringen om du vill ändra ett värde eller stänga av den.
   
    ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-android-manage-alerts.png)
4. Tryck på plusikonen (+) för att lägga till en ny avisering på samma panel.
5. Om du vill ta bort aviseringen helt knackar du på papperskorgen ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-android-delete-alert-icon.png).

## <a name="data-alerts-on-a-windows-device"></a>Dataaviseringar på en Windows-enhet

>[!NOTE]
>Stöd för Power BI-mobilappen för **telefoner som använder Windows 10 Mobile** kommer att upphöra den 16 mars 2021. [Läs mer](https://go.microsoft.com/fwlink/?linkid=2121400)

### <a name="set-data-alerts-on-a-windows-device"></a>Ställ in dataaviseringar på en Windows-enhet
1. Tryck på en tal- eller mätarpanel på en instrumentpanel att öppna den.  
2. Tryck på klockikonen ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-windows-10-alert-bell-off.png) för att lägga till en avisering.  
   
   ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-windows-10-tap-alert.png)
3. Tryck på plusikonen (+).
   
   ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-windows-10-no-alerts-yet.png)
4. Välj att ta emot aviseringar över eller under ett värde och ange sedan värdet.
   
   ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-windows-10-set-alert.png)
5. Begär om du vill få aviseringar varje timme eller dag och om du vill få ett e-postmeddelande när du får aviseringen.
   
   > [!NOTE]
   > Du får inte aviseringar varje timme eller varje dag om data inte har uppdaterats vid den tiden.
   > 
   > 
6. Du kan också ändra aviseringens namn.
7. Tryck på krysset.
8. En panel kan ha aviseringar för värden både över och under tröskelvärden. Tryck på plustecknet (+) i **Hantera aviseringar**.
   
   ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-windows-10-add-another-alert.png)

### <a name="manage-alerts-on-a-windows-device"></a>Hantera dataaviseringar på en Windows-enhet
Du kan hantera enskilda aviseringar i Power BI-appen eller [hantera alla varningar i Power BI-tjänsten](../../create-reports/service-set-data-alerts.md).

1. Tryck på en kort- eller mätarpanel som har en avisering på instrumentpanelen.  
2. Tryck på klockikonen ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-windows-10-alert-bell-on.png).  
   
   ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-windows-10-has-alerts.png)
3. Tryck på aviseringen om du vill ändra ett värde eller stänga av den.
   
    ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-windows-10-add-another-alert.png)
4. Om du vill ta bort aviseringen helt kan du högerklicka eller trycka och hålla kvar på > **Ta bort**.

## <a name="receiving-alerts"></a>Ta emot aviseringar
Du får aviseringar i [Power BI-meddelandecentret](mobile-apps-notification-center.md) på din mobila enhet eller i Power BI-tjänsten, tillsammans med meddelanden om nya instrumentpaneler som någon har delat med dig.

Datakällor är ofta inställda på att uppdateras varje dag, men vissa uppdateras oftare. När data i instrumentpanelen uppdateras och om data som spåras når något av dina angivna tröskelvärden sker flera saker.

1. Power BI kontrollerar om mer än en timme eller mer än 24 timmar har gått (beroende på vilket alternativ som du valde) sedan den senaste aviseringen skickades.
   
   Så länge data har passerat tröskelvärdet får du en avisering varje timme eller var 24 timme.
2. Om du har valt att skicka ett e-postmeddelande kommer du att se följande i din inkorg.
   
   ![](media/mobile-set-data-alerts-in-the-mobile-apps/powerbi-alerts-email.png)
3. Power BI lägger till ett meddelande i [Meddelandecenter](mobile-apps-notification-center.md) och lägger till en gul prick på klockikonen ![klockikon](media/mobile-set-data-alerts-in-the-mobile-apps/powerbi-alert-tile-notification-icon.png) på namnlisten (iOS och Android) eller till den globala navigeringsknappen ![globala navigeringsknapp](./media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-iphone-alert-global-nav-button.png) (Windows 10-enheter).


4. Tryck på klockikonen ![klockikon](media/mobile-set-data-alerts-in-the-mobile-apps/powerbi-alert-tile-notification-icon.png) eller på den globala navigeringsknappen ![global navigeringsknapp](./media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-iphone-alert-global-nav-button.png) för att [öppna ditt **Meddelandecenter**](mobile-apps-notification-center.md) och se aviseringsinformationen.
   
     

> [!NOTE]
> Aviseringar fungerar bara på data som ska uppdateras. När data uppdateras söker Power BI för att se om en avisering har angetts för dessa data. Om data har uppnått ett tröskelvärde utlöses en avisering.
> 
> 

## <a name="tips-and-troubleshooting"></a>Tips och felsökning
* Aviseringar stöds inte för närvarande för Bing paneler eller kortpaneler med datum-/tidsmått.
* Aviseringar fungerar bara med numeriska data.
* Aviseringar fungerar bara på data som ska uppdateras. De fungerar inte på statiska data.
* Aviseringar fungerar inte med paneler som innehåller direktuppspelade data.

## <a name="next-steps"></a>Nästa steg
* [Hantera aviseringar i Power BI-tjänsten](../../create-reports/service-set-data-alerts.md)
* [Power BI Mobile-meddelandecentret](mobile-apps-notification-center.md)
* Har du några frågor? [Fråga Power BI Community](https://community.powerbi.com/)
