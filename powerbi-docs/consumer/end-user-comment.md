---
title: Lägga till kommentarer på instrumentpaneler och i rapporter
description: I det här dokumentet visas hur du lägger till kommentarer på en instrumentpanel, i en rapport eller i ett visuellt objekt samt hur du använder kommentarer för att föra konversationer med samarbetspartner.
author: mihart
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: how-to
ms.date: 02/18/2020
ms.author: mihart
LocalizationGroup: Consumer
ms.openlocfilehash: 4d9581a617241afbe668d8e1810c0c3f60a0835c
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85236052"
---
# <a name="add-comments-to-a-dashboard-or-report"></a>Lägga till kommentarer på en instrumentpanel eller i en rapport

[!INCLUDE[consumer-appliesto-ynny](../includes/consumer-appliesto-ynny.md)]

[!INCLUDE [power-bi-service-new-look-include](../includes/power-bi-service-new-look-include.md)]

Lägg till en personlig kommentar eller starta en konversation om en instrumentpanel eller en rapport med dina kollegor. **Kommentarsfunktionen** är bara ett exempel på hur en *användare* kan samarbeta med andra. 

![kommentarsvideo](media/end-user-comment/comment.gif)

> [!NOTE]
> När du ska samarbeta med andra, till exempel om du vill lägga till kommentarer i delade rapporter, behöver du en Power BI Pro- eller Premium-licens. [Vilken licenstyp har jag?](end-user-license.md)

## <a name="how-to-use-the-comments-feature"></a>Hur du använder kommentarsfunktionen
Kommentarer kan läggas till på en hel instrumentpanel, i enskilda visuella objekt på en instrumentpanel, på en rapportsida, i en sidnumrerad rapport samt i enskilda visuella objekt på en rapportsida. Lägg till en allmän kommentar eller en kommentar riktad till specifika kollegor.  

När du lägger till en kommentar i en rapport hämtar Power BI de aktuella filter- och utsnittsvärdena. Det innebär att när du väljer eller svarar på en kommentar så kan rapportsidan eller rapportens visuella objekt ändras till att visa de filter- och utsnittsval som var aktiva när kommentaren först lades till.  

![video om rapport med filter](media/end-user-comment/power-bi-comment.gif)

Varför är det här viktigt? Anta att en kollega använde ett filter som gav en intressant insikt som kollegan vill dela med teamet. Utan det filtret skulle kommentaren kanske inte ge någon tydlig information.

Om du använder en sidnumrerad rapport kan du endast lämna en allmän kommentar om rapporten.  Du kan inte lämna kommentarer till enskilda visuella objekt i sidnumrerade rapporter.

### <a name="add-a-general-comment-to-a-dashboard-or-report"></a>Lägga till en allmän kommentar på en instrumentpanel eller i en rapport
Processen för att lägga till kommentarer på en instrumentpanel liknar den där du lägger till i en rapport.  I det här exemplet använder vi en instrumentpanel. 

1. Öppna en Power BI-instrumentpanel eller en rapport och välj ikonen **Kommentarer**. Då öppnas dialogrutan Kommentarer.

    ![Ikonen Kommentarer](media/end-user-comment/power-bi-comment-menu.png)

    Här ser vi att skaparen av instrumentpanelen redan har lagt till en allmän kommentar.  Alla med åtkomst till instrumentpanelen kan se den här kommentaren.

    ![Ikonen Kommentarer](media/end-user-comment/power-bi-first-comments.png)

2. Svara genom att välja **Svara**, skriva svaret och välja **Publicera**.  

    ![Ikonen Kommentarssvar](media/end-user-comment/power-bi-comment-reply.png)

    Som standard dirigerar Power BI ditt svar till de kollegor som startade kommentarstråden, i det här fallet Aaron. 

    ![Kommentar med svar](media/end-user-comment/power-bi-respond.png)

 3. Om du vill lägga till en kommentar som inte ingår i en befintlig tråd skriver du kommentaren i det övre textfältet.

    ![Ikonen Kommentarssvar](media/end-user-comment/power-bi-new-comments.png)

    Kommentarerna för den här instrumentpanelen ser nu ut så här.

    ![Kommentarskonversationer](media/end-user-comment/power-bi-conversation.png)

### <a name="add-a-comment-to-a-specific-dashboard-or-report-visual"></a>Lägga till en kommentar i ett visst visuellt objekt på en instrumentpanel eller i en rapport
Utöver att lägga till kommentarer på en hel instrumentpanel eller en hel rapportsida kan du lägga till kommentarer i enskilda instrumentpanelsrutor och enskilda visuella objekt i rapporter. Processerna liknar varandra, och i det här exemplet använder vi en rapport.

1. Hovra över det visuella objektet och välj **Fler alternativ** (...).    
2. Välj **Öppna kommentarer** i listrutan.

    ![Lägga till en kommentar är det första alternativet](media/end-user-comment/power-bi-report-comment.png)  

3.  Dialogrutan **Kommentarer** öppnas och de andra visuella objekten på sidan är gråtonade. Det visuella objektet har inga kommentarer än. 

    ![Lägg till en kommentar till mig själv](media/end-user-comment/power-bi-comment-column.png)  

4. Skriv kommentaren och välj sedan **Publicera**.

    ![Lägg till en kommentar till mig själv](media/end-user-comment/power-bi-comment-logistics.png)  

    - På en rapportsida kan du välja en kommentar som gjorts på ett visuellt objekt för att markera det visuella objektet (se ovan).

    - På en instrumentpanel visas diagramikonen ![ikonen Kommentar med diagram](media/end-user-comment/power-bi-comment-chart-icon.png) meddela om en kommentar är knuten till ett specifikt visuellt objekt. Kommentarer som gäller för hela instrumentpanelen har ingen särskild ikon. Om du väljer diagramikonen markeras det relaterade visuella objektet på instrumentpanelen.
    

    ![relaterat visuellt objekt markerat](media/end-user-comment/power-bi-highlight.png)

5. Välj **Stäng** för att återgå till instrumentpanelen eller rapporten.

### <a name="get-your-colleagues-attention-by-using-the--sign"></a>Få kollegornas uppmärksamhet genom att använda @-tecknet
Oavsett om du skapar en kommentar för instrumentpanel, rapport, ruta eller visuellt objekt kan du fånga kollegornas uppmärksamhet med hjälp av ”\@”-tecknet.  När du skriver ”\@”-tecknet öppnar Power BI en listruta där du kan söka efter och välja personer från din organisation. Alla verifierade namn med \@-tecknet först visas i blått. 

Det här är en konversation jag har med *visualiseringsdesignern*. Den personen använder @-tecknet för att försäkra sig om att jag ser kommentaren. Jag vet att den här kommentaren är avsedd för mig. När jag öppnar den här appen i Power BI väljer jag **Kommentarer** i rubriken. Vår konversation visas i **kommentarsfönstret**.

![Lägg till ett omnämnande till en kommentar](media/end-user-comment/power-bi-comment-convo.png)  



## <a name="next-steps"></a>Nästa steg
Tillbaka till [visualiseringar för användare](end-user-visualizations.md)    
<!--[Select a visualization to open a report](end-user-open-report.md)-->
