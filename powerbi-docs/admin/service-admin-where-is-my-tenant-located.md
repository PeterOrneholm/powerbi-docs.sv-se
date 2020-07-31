---
title: Var finns min Power BI-klient?
description: Lär dig var din Power BI-klient finns och hur den platsen har valts. Det här är viktigt att lära sig eftersom det kan påverka dina interaktioner med tjänsten.
author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 09/09/2019
ms.author: kfollis
LocalizationGroup: Administration
ms.openlocfilehash: ee123bed8940b52a66f3b0f860671a87210c261f
ms.sourcegitcommit: e9cd61eaa66eda01cc159251d7936a455c55bd84
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/23/2020
ms.locfileid: "86952695"
---
# <a name="where-is-my-power-bi-tenant-located"></a>Var finns min Power BI-klient?

<iframe width="560" height="315" src="https://www.youtube.com/embed/0fOxaHJPvdM?showinfo=0" frameborder="0" allowfullscreen></iframe>

Lär dig var din Power BI-klient finns och hur den platsen har valts. Det är viktigt att lära sig platsen eftersom det kan påverka dina interaktioner med tjänsten.

## <a name="how-to-determine-where-your-power-bi-tenant-is-located"></a>Så här fastställer du var Power BI-klient finns

Följ dessa steg för att hitta den region som din klient finns i.

1. I Power BI-tjänsten på den översta menyn väljer du hjälp ( **?** ) och sedan **Om Power BI**.

1. Leta efter värdet bredvid **dina data lagras i**. Det är den region där din klientorganisation finns. Värdet är även den region där dina data lagras, såvida du inte använder dedikerade kapaciteter i olika regioner för dina arbetsytor.

    ![Dataområde](media/service-admin-where-is-my-tenant-located/power-bi-data-region.png)

## <a name="how-the-data-region-is-selected"></a>Så här väljs dataregionen

Dataområdet baseras på det land/region som du väljer när du skapar klienten. Valet gäller för registreringen för både Microsoft 365 och Power BI eftersom den här informationen delas. Om det är en ny klientorganisation väljer du rätt land/region i listan när du registrerar dig.

![Val av land](media/service-admin-where-is-my-tenant-located/sign-up-country-selection.png)

Power BI väljer det dataområde som är närmast ditt val, vilket avgör var data lagras för din klientorganisation.

> [!IMPORTANT]
> Du kan inte ändra valet när du väl har skapat klientorganisationen.

Har du fler frågor? [Prova Power BI Community](https://community.powerbi.com/)
