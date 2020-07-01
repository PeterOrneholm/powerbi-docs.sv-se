---
title: Utgående Power BI- och Azure-data
description: Förstå avgifter för utgående Azure-utgående och Power BI baserat på klientorganisationens plats och Power BI Premium
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: how-to
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Data from databases
ms.openlocfilehash: c93299a2066dd2f15843048742e857495db7242a
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85230588"
---
# <a name="power-bi-and-azure-egress"></a>Utgående Power BI- och Azure-data

När du använder Power BI med Azure-datakällor kan du undvika avgifter för utgående Azure-data genom att se till att din Power BI-klientorganisation är i samma region som dina Azure-datakällor.

När din Power BI-klientorganisation distribueras i samma Azure-region där du distribuerar dina datakällor debiteras du inte några avgifter för utgående data för schemalagd uppdatering och DirectQuery-interaktioner. 

## <a name="determining-where-your-power-bi-tenant-is-located"></a>Fastställa var Power BI-klientorganisationen finns

Om du vill ta reda på var din Power BI-klientorganisation finns kan du läsa artikeln [Var finns min Power BI-klientorganisation?](../admin/service-admin-where-is-my-tenant-located.md).

För Power BI Premium Multi-Geo-kunder gäller att om Power BI-klientorganisationen inte är på den optimala platsen för vissa av dina Azure-baserade datakällor kan du distribuera Power BI Premium Multi-Geo i önskad Azure-region och dra fördel av att ha din Power BI-klientorganisation och Azure-datakällor i samma Azure-region.

## <a name="next-steps"></a>Nästa steg

Mer information om Power BI Premium och Multi-Geo finns i följande resurser:

* [Vad är Microsoft Power BI Premium?](../admin/service-premium-what-is.md)
* [Så här köper du Power BI Premium](../admin/service-admin-premium-purchase.md)
* [Multi-Geo-stöd för Power BI Premium (förhandsversion)](../admin/service-admin-premium-multi-geo.md)
* [Var finns min Power BI-klient?](../admin/service-admin-where-is-my-tenant-located.md)
* [Vanliga frågor och svar om Power BI Premium](../admin/service-premium-faq.md)
