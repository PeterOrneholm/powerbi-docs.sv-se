---
title: Använda samma kontoinloggning för Power BI och Azure
description: Så här använder du samma kontoinloggning för Power BI och Azure
author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 09/09/2019
ms.author: kfollis
LocalizationGroup: Troubleshooting
ms.openlocfilehash: fe93fa3f41cf1c340b31ce3c6f817f842f3039ff
ms.sourcegitcommit: c18130ea61e67ba111be870ddb971c6413a4b632
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/09/2020
ms.locfileid: "86161662"
---
# <a name="using-the-same-account-for-power-bi-and-azure"></a>Använda samma kontoinloggning för Power BI och Azure

Om du är en användare av både Power BI och Azure, vill du kanske använda samma inloggning för båda tjänsterna så att du inte behöver ange ditt lösenord två gånger.

Power BI loggar in dig med ditt organisationskonto som är kopplat till din arbets- eller skolmejl.  Azure loggar in dig med ett Microsoft-konto eller ditt organisationskonto.

Om du vill använda samma inloggning för både Azure och Power BI ska du logga in på Azure med ditt organisationskonto.

**Vad händer om jag redan har loggat in på Azure med mitt Microsoft-konto?**

Du kan lägga till ditt organisationskonto som medadministratör i Azure med följande steg:

1. Logga in på [Azure-portalen](https://portal.azure.com/). Om du är en användare i flera kataloger i Azure markerar du **Prenumerationer** och filtrerar sedan för att visa katalogen och de prenumerationer som du vill redigera.

1. I navigeringsfönstret väljer du **Åtkomstkontroll (IAM)** och sedan **Lägg till** \> **Lägg till medadministratör**.

    ![Skärm bild av åtkomstkontroll med Lägg till en medadministratör framhävt.](media/service-admin-how-to-use-the-same-account-as-azure/add-co-administrator.png)

1. Ange den e-postadress som är associerat med ditt organisationskonto och välj **Lägg till**.

1. Nästa gång du loggar in på Azure-portalen ska du använda din organisations e-postadress.

Har du fler frågor? [Prova Power BI Community](https://community.powerbi.com/)
