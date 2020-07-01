---
title: Hantera datalagring i dina arbetsytor
description: Läs hur du hanterar datalagring individuellt eller på arbetsytan för att se till att du kan fortsätta publicera rapporter och datamängder.
author: maggiesMSFT
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: how-to
ms.date: 02/25/2020
ms.author: maggies
LocalizationGroup: Administration
ms.openlocfilehash: bd671e32167837a5b8b96388bb2687616e6cada5
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85228565"
---
# <a name="manage-data-storage-in-power-bi-workspaces"></a>Hantera datalagring i Power BI-arbetsytor

Läs hur du hanterar datalagring individuellt eller på arbetsytan så att du kan fortsätta publicera rapporter och datamängder.

## <a name="capacity-limits"></a>Kapacitetsbegränsningar

Lagringsgränser för arbetsytan, vare sig det gäller min arbetsyta eller en apparbetsyta, beror på om arbetsytan har [delad eller premiumkapacitet](../fundamentals/service-basic-concepts.md#capacities).

### <a name="shared-capacity-limits"></a>Begränsningar för delad kapacitet
För arbetsytor i delad kapacitet: 

- Det finns en lagringsgräns per arbetsyta på 100 GB.
- För app-arbetsytor får den totala användningen inte överskrida klientlagringsgränsen på 10 GB multiplicerat med antalet Pro-licenser i klienten.

### <a name="premium-capacity-limits"></a>Begränsningar för premiumkapacitet
För arbetsytor med premiumkapacitet:
- Det finns en gräns på 100 TB per Premium-kapacitet.
- Det finns ingen lagringsgräns per användare.

Läs om andra funktioner i [Power BI-prismodellen](https://powerbi.microsoft.com/pricing).

## <a name="whats-included-in-storage"></a>Vad som ingår i lagringen

Din datalagring inkluderar dina egna datauppsättningar och Excel-rapporter och de objekt som någon har delat med dig. Datauppsättningar är alla datakällor du har laddat upp eller anslutit till. Dessa datakällor omfattar Power BI Desktop-filer och Excel-arbetsböcker du använder. Följande ingår även i din datakapacitet.

* Excel-intervall fästa på en instrumentpanel.
* Reporting Services lokala visualiseringar fästa på en Power BI-instrumentpanel.
* Överförda bilder.

Storleken på en instrumentpanel som du delar varierar beroende på vad som är fäst på den. Om du till exempel fäster objekt från två rapporter som ingår i två olika datauppsättningar, kommer storleken att inkludera bägge datauppsättningarna.

<a name="manage"/>

## <a name="manage-items-you-own"></a>Hantera objekt du äger

Se hur mycket lagringsutrymme du använder i ditt Power BI-konto och hantera ditt konto.

1. Om du vill hantera din lagring går du till **Min arbetsyta** i navigeringsfönstret.
   
    ![Min arbetsyta](media/service-admin-manage-your-data-storage-in-power-bi/pbi_myworkspace.png)

2. Välj kugghjulsikonen ![Kugghjulsikon](media/service-admin-manage-your-data-storage-in-power-bi/pbi_gearicon.png) i det övre högra hörnet \> **Hantera personlig lagring**.
   
    Det översta fältet visar hur mycket av din lagringsgräns som du har använt.
   
    ![Hantera lagringsgräns](media/service-admin-manage-your-data-storage-in-power-bi/pbi_persnlstorage.png)
   
    Datauppsättningarna och rapporterna avgränsas på två flikar:
   
    **Ägs av mig:** Du har laddat upp dessa rapporter och datauppsättningar till ditt Power BI-konto, inklusive tjänstedatauppsättningar som Salesforce och Dynamics CRM.  

    **Ägs av andra:** Andra har delat dessa rapporter och datauppsättningar med dig.
1. Om du vill ta bort en datauppsättning eller rapport, väljer du papperskorgsikonen ![papperskorgsikonen](media/service-admin-manage-your-data-storage-in-power-bi/pbi_deleteicon.png).

Tänk på att du eller någon annan kan ha rapporter och instrumentpaneler baserade på en datauppsättning. Om du tar bort datauppsättningen, fungerar dessa rapporter och instrumentpaneler inte längre.

## <a name="manage-your-workspace"></a>Hantera din arbetsyta
1. Välj pilen intill **Arbetsytor** \> välj namnet på arbetsytan.
   
    ![Välj en arbetsyta](media/service-admin-manage-your-data-storage-in-power-bi/pbi_groupworkspaces.png)
2. Välj kugghjulsikonen ![Kugghjulsikon](media/service-admin-manage-your-data-storage-in-power-bi/pbi_gearicon.png) i det övre högra hörnet \>  **Hantera grupplagring**.
   
    Det översta fältet visar hur mycket av din lagringsgräns som du har använt.
   
    ![Hantera lagring för arbetsytor](media/service-admin-manage-your-data-storage-in-power-bi/pbi_groupstorage.png)
   
    Datauppsättningarna och rapporterna avgränsas på två flikar:
   
    **Ägs av oss:** Du eller någon annan har laddat upp dessa rapporter och datauppsättningar till gruppens Power BI-konto, inklusive tjänstedatauppsättningar som Salesforce och Dynamics CRM.

    **Ägs av andra:** Andra har delat dessa rapporter och datauppsättningar med din grupp.

3. Om du vill ta bort en datauppsättning eller rapport, väljer du papperskorgsikonen ![papperskorgsikonen](media/service-admin-manage-your-data-storage-in-power-bi/pbi_deleteicon.png).
   
   > [!NOTE]
   > Tänk på att du eller någon annan i gruppen kan ha rapporter och instrumentpaneler baserade på en datauppsättning. Om du tar bort datauppsättningen, fungerar dessa rapporter och instrumentpaneler inte längre.
   
   Alla medlemmar i en arbetsyta med rollen administratör, medlem eller deltagare har behörighet att ta bort datamängder och rapporter från arbetsytan.

## <a name="dataset-limits"></a>Datauppsättningsgränser
Det finns en gräns på 1 GB, per datauppsättning som importeras till Power BI. Om du har valt att behålla Excel-upplevelsen istället för att importera data, är gränsen 250 MB för datauppsättningen.

## <a name="what-happens-when-you-reach-a-limit"></a>Vad händer när du når en gräns?
När du når datakapacitetsgränsen för vad du kan göra, får du meddelanden i tjänsten. 

När du väljer kugghjulsikonen ![kugghjulsikonen](media/service-admin-manage-your-data-storage-in-power-bi/pbi_gearicon.png), ser du ett rött streck som anger att du har överskridit din datakapacitetsgräns.

![Uppnådd lagringsgräns](media/service-admin-manage-your-data-storage-in-power-bi/manage-storage-limit.png)

Den här gränsen visas också i **Hantera personlig lagring**.

 ![Hantera personlig lagring, lagringsgränsen har nåtts](media/service-admin-manage-your-data-storage-in-power-bi/manage-storage-limit2.png)

 När du försöker utföra en åtgärd som når någon av gränserna visas ett meddelande om att du är över gränsen. Du kan [hantera](#manage) din lagring för att minska ditt lagringsutrymme och komma förbi gränsen.

 ![Över din lagringsgräns](media/service-admin-manage-your-data-storage-in-power-bi/powerbi-pro-over-limit.png)

 ## <a name="next-steps"></a>Nästa steg

 Har du fler frågor? [Fråga Power BI Community](https://community.powerbi.com/)
