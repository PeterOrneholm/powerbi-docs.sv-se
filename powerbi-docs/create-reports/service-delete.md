---
title: Ta bort en instrumentpanel, rapport, arbetsbok, datauppsättning eller arbetsyta
description: Lär dig hur du tar bort nästan vad som helst från Power BI
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: how-to
ms.date: 09/11/2018
ms.author: maggies
LocalizationGroup: Common tasks
ms.openlocfilehash: ff31548801f372fa1e20949e5c109cc9214f55e1
ms.sourcegitcommit: e8ed3d120699911b0f2e508dc20bd6a9b5f00580
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/11/2020
ms.locfileid: "86264483"
---
# <a name="delete-almost-anything-in-power-bi-service"></a>Ta bort på nästan vad som helst i Power BI-tjänsten
Den här artikeln lär dig hur du tar bort en instrumentpanel, rapport, rapportsida, arbetsbok, datauppsättning, app, visualisering och arbetsyta i Power BI-tjänsten.

## <a name="delete-a-dashboard"></a>Ta bort en instrumentpanel
Instrumentpaneler kan tas bort. När du tar bort en instrumentpanel tas inte den underliggande datauppsättningen eller rapporter som associeras med instrumentpanelen bort.

* Om du är ägaren av instrumentpanelen kan du ta bort den. Om du har delat instrumentpanelen med dina kollegor kommer instrumentpanelen att tas bort från deras Power BI-arbetsyta när du tar bort instrumentpanelen från din Power BI-arbetsyta.
* Om en instrumentpanel har delats med dig och du inte längre vill se den kan du ta bort den.  Att ta bort en instrumentpanel tar inte bort den från någon annan persons Power BI-arbetsyta.
* Om du använder en instrumentpanel som ingår i en [organisations innehållspaketet](../collaborate-share/service-organizational-content-pack-disconnect.md) är det enda sättet att ta bort den att ta bort den associerade datauppsättningen.

### <a name="to-delete-a-dashboard"></a>Ta bort en instrumentpanel
1. Stanna kvar på arbetsytan och välj fliken **Datauppsättningar**.
2. Leta upp instrumentpanelen som du vill ta bort och välj ikonen Ta bort ![ikonen Ta bort](media/service-delete/power-bi-delete-icon.png).

    ![video](media/service-delete/power-bi-delete-dash.gif)

## <a name="delete-a-report"></a>Ta bort en rapport
Oroa dig inte, att ta bort en rapport påverkar inte datauppsättningen som den bygger på.  Och alla visualiseringar som du har fäst i rapporten är också säkra – de blir kvar i instrumentpanelen tills du tar bort dem individuellt.

### <a name="to-delete-a-report"></a>Så här tar du bort en rapport
1. Stanna kvar på arbetsytan och välj fliken **Rapporter**.
2. Leta upp rapporten du vill ta bort och välj ikonen Ta bort   ![ikonen Ta bort](media/service-delete/power-bi-delete-icon.png).   

    ![rapportfliken på en arbetsyta](media/service-delete/power-bi-delete-reportnew.png)
3. Bekräfta borttagningen.

   ![Dialogrutan Ta bort rapport](media/service-delete/power-bi-delete-report.png)

   > [!NOTE]
   > Om rapporten är en del av ett [innehållspaket](../collaborate-share/service-organizational-content-pack-introduction.md) kan du inte ta bort den med den här metoden.  Se [Ta bort din anslutning till ett organisationsinnehållspaket](../collaborate-share/service-organizational-content-pack-disconnect.md).
   >
   >

## <a name="delete-a-workbook"></a>Ta bort en arbetsbok
Arbetsböcker kan tas bort. Men om du tar bort en arbetsbok tar också bort alla rapporter och instrumentpaneler som innehåller data bort från den här arbetsboken.

Om arbetsboken lagras på OneDrive för företag raderas den inte från OneDrive när du tar bort den från Power BI.

### <a name="to-delete-a-workbook"></a>Så här tar du bort en arbetsbok
1. Stanna kvar på arbetsytan och välj fliken **Arbetsböcker**.
2. Leta upp arbetsboken du vill ta bort och välj ikonen Ta bort ![ikonen Ta bort](media/service-delete/power-bi-delete-report2.png) -ikonen.

    ![Fliken Arbetsböcker](media/service-delete/power-bi-delete-workbooknew.png)
3. Bekräfta borttagningen.

   ![Dialogrutan Ta bort arbetsbok](media/service-delete/power-bi-delete-confirm.png)

## <a name="delete-a-dataset"></a>Ta bort en datauppsättning
Datauppsättningar kan tas bort. Men om du tar bort en datauppsättning tas även alla rapporter och instrumentpaneler bort som innehåller data från den datauppsättningen.

Om en datauppsättning är en del av en eller flera [organisationsinnehållspaket](../collaborate-share/service-organizational-content-pack-disconnect.md) är det enda sättet att ta bort den att ta bort den från innehållshanteringspaketet där den har används, vänta tills den bearbetas och sedan försöka ta bort den igen.

### <a name="to-delete-a-dataset"></a>Ta bort en datauppsättning
1. Stanna kvar på arbetsytan och välj fliken **Datauppsättningar**.
2. Leta rätt på datamängden du vill ta bort och välj **Fler alternativ** (...).  

    ![Fliken Datauppsättningar](media/service-delete/power-bi-delete-datasetnew.png)
3. I listrutan väljer du **Ta bort**.

   ![ellipsmenyn](media/service-delete/power-bi-delete-datasetnew2.png)
4. Bekräfta borttagningen.

   ![Dialogrutan Ta bort instrumentpanel](media/service-delete/power-bi-delete-dataset-confirm.png)

## <a name="delete-a-workspace"></a>Ta bort en arbetsyta
> [!WARNING]
> När du skapar en arbetsyta skapar du också en Microsoft 365-grupp. Och när du tar bort en arbetsyta tar du även bort motsvarande Microsoft 365-grupp. Det innebär att gruppen också tas bort från andra Microsoft 365-produkter som SharePoint och Microsoft Teams.
>
>

Som författare till arbetsytan kan du ta bort den. När du tar bort den tas den kopplade appen bort för alla medlemmar i gruppen och tas bort från din AppSource om du har publicerat appen till hela organisationen. Att ta bort en arbetsyta är inte samma sak som att lämna en arbetsyta.

### <a name="to-delete-a-workspace---if-you-are-an-admin"></a>Ta bort en arbetsyta – om du är administratör
1. Välj **Arbetsytor** i navigeringsfönstret

2. Välj **Fler alternativ** (...) till höger om arbetsytan du vill ta bort och välj **Redigera arbetsyta**.

    ![arbetsytor](media/service-delete/power-bi-delete-workspace.png)

3. I fönstret **Redigera arbetsyta** väljer du **Ta bort arbetsyta** > **Ta bort**.

    ![ta bort arbetsyta](media/service-delete/power-bi-delete-workspace2.png)

### <a name="to-remove-a-workspace-from-your-list"></a>Ta bort en arbetsyta från listan
Om du inte längre vill vara medlem i en arbetsyta kan du ***lämna*** den så tas den bort från listan. När du lämnar en arbetsyta förblir den på plats för andra användare av arbetsytan.  

> [!IMPORTANT]
> Du kan inte lämna en arbetsyta om du är den enda administratören för den.
>
>

1. Öppna den arbetsyta du vill ta bort.

2. Välj **Fler alternativ** (...) uppe till höger och välj **Lämna arbetsyta** > **Lämna**.

      ![lämna arbetsyta](media/service-delete/power-bi-leave-workspace.png)

   > [!NOTE]
   > Vilka alternativ du ser i listrutan beror på om du är administratör eller medlem i arbetsytan.
   >
   >

## <a name="delete-or-remove-an-app"></a>Radera eller ta bort en App
Appar kan enkelt tas bort från listan med appar. Men endast administratörer kan ta bort en app permanent.

### <a name="remove-an-app-from-your-app-list-page"></a>Ta bort en app från din lista med appar
Om du tar bort en app från applistan tas den inte bort för andra medlemmar.

1. Öppna applistsidan genom att välja **Appar** i navigeringsfönstret.
2. Håll muspekaren över appen du vill ta bort och välj ikonen Ta bort ![papperskorgsikon](media/service-delete/power-bi-delete-report2.png)  -ikonen.

   ![välj appar](media/service-delete/power-bi-delete-app.png)

   Om du tar bort en app av misstag har du flera alternativ för att få den tillbaka.  Du kan be appskaparen att skicka den igen, du kan hitta det ursprungliga e-postmeddelandet med länken till appen, du kan kolla i ditt [Aktivitetscenter](../consumer/end-user-notification-center.md) för att se om meddelandet för den appen fortfarande listas eller så kan du kontrollera din organisations [AppSource](../consumer/end-user-apps.md).

## <a name="considerations-and-troubleshooting"></a>Överväganden och felsökning
Den här artikeln visar hur du tar bort de primära byggstenarna för Power BI-tjänsten. Men det finns flera saker som du kan ta bort i Power BI.  

* [Ta bort din aktuella instrumentpanel](../consumer/end-user-featured.md)
* [Ta bort en instrumentpanel från favoriter](../consumer/end-user-favorite.md)
* [Ta bort en rapportsida](service-delete.md)
* [Ta bort en instrument](service-dashboard-edit-tile.md)
* [Ta bort en rapportvisualisering](service-delete.md)

Har du fler frågor? [Prova Power BI Community](https://community.powerbi.com/)
