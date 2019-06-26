---
title: Kontrollera användningen av datamängder mellan arbetsytor (förhandsversion) – Power BI
description: Lär dig hur du begränsar informationsflödet i Power BI-klientorganisationen.
author: maggiesMSFT
manager: kfile
ms.reviewer: chbraun
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/31/2019
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: 363bf9b107722b3993ed7ac43138c73da03f410a
ms.sourcegitcommit: 7c426a5209d4fdd1360fc3d0442d57991be1984d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2019
ms.locfileid: "66461797"
---
# <a name="control-the-use-of-datasets-across-workspaces-preview"></a>Kontrollera användningen av datamängder mellan arbetsytor (förhandsversion)

Användning av datamängder mellan arbetsytor är ett kraftfullt sätt att främja datakulturen och datademokratiseringen i en organisation. Om du är Power BI-administratör vill du dock ibland begränsa informationsflödet i din Power BI-klientorganisation. Med klientorganisationsinställningen **Använd datauppsättningar mellan arbetsytor** kan du begränsa återanvändningen av datamängd antingen helt eller delvis per säkerhetsgrupp.

![Inställningar för Power BI-administratörens arbetsyta](media/service-datasets-admin-across-workspaces/power-bi-admin-workspace-settings.png)

Om du inaktiverar den här inställningen påverkas rapportskapare på följande sätt:

- Knappen för att kopiera rapporter mellan arbetsytor är inte tillgänglig. 
- I en rapport som är baserad på en delad datamängd är knappen **Redigera rapport** inte tillgänglig.
- I Power BI-tjänsten visar upptäcktsfunktionen endast datamängder på den aktuella arbetsytan.
- I Power BI Desktop visar upptäcktsfunktionen endast datamängder från de arbetsytor där du är medlem.
- Om användare i Power BI Desktop öppnar en .pbix-fil med en live-anslutning till en datamängd utanför de arbetsytor där de är medlem visas ett felmeddelande som uppmanar dem att ansluta till en annan datamängd.

## <a name="provide-a-link-for-the-certification-process"></a>Ange en länk för certifieringsprocessen

Som klientorganisationsadministratör kan du ange en URL för länken **Läs mer** på sidan för inställningen **Endorsement** (Rekommendation).  Den här länken kan leda till dokumentationen om certifieringsprocessen. Om du inte anger ett mål för länken **Läs mer** pekar den som standard på artikeln [datamängdscertifiering](service-datasets-certify.md).

![Datamängdscertifiering Läs mer](media/service-datasets-certify-promote/power-bi-dataset-learn-more-certification.png)

## <a name="next-steps"></a>Nästa steg

- [Använda datamängder mellan arbetsytor (förhandsversion)](service-datasets-across-workspaces.md)
- Har du några frågor? [Fråga Power BI Community](http://community.powerbi.com/)