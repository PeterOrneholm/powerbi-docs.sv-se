---
title: Ytterligare köp kan krävas – riktlinjer för visuella objekt i Power BI
description: Läs hur du kan publicera dina anpassade visuella objekt till AppSource där andra kan upptäcka och använda dem via ett inköp.
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 11/26/2018
ms.openlocfilehash: 9ef7890c6f80845a9e6d1bd02e35778ed866ff54
ms.sourcegitcommit: 35d763dfc75c229204d36fd8b35c1e860786b707
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/27/2018
ms.locfileid: "52332219"
---
# <a name="guidelines-for-power-bi-visuals-with-additional-purchases"></a>Riktlinjer för visuella objekt i Power BI med ytterligare inköp

Tills nyligen godkände endast **marknadsplatsen (AppSource)** kostnadsfria visuella objekt i Power BI. Den här principen ändras så att visuella objekt med prislappen ”ytterligare köp kan krävas” också kan skickas till **AppSource**. Visuella objekt där ytterligare köp kan krävas liknar köp via app-tillägg (IAP) i Office Store. Utvecklare kan också skicka dessa visuella objekt för certifiering när de har godkänts av **AppSource**-teamet och när du har kontrollerat att de uppfyller certifieringskraven enligt beskrivningen i [artikeln om certifierade anpassade visuella objekt](../power-bi-custom-visuals-certified.md).

> [!Note]
> Det visuella objektet måste inte ha åtkomst till externa tjänster eller resurser för att godkännas.

## <a name="whats-changing-in-the-submission-process"></a>Vad ändras i överföringsprocessen?

Utvecklare laddar upp sina visuella IAP-objekt till AppSource via instrumentpanelen för försäljning, precis som med kostnadsfria visuella objekt. För att visa att det skickade visuella objektet har IAP-funktioner ska utvecklare skriva följande i anteckningarna för instrumentpanelen för försäljning: ”Visual with in-app purchase” (Visuellt objekt med köp i appen). Utvecklare måste också ange en licensnyckel eller token så att verifieringsteamet kan validera IAP-funktioner. När det visuella objektet har verifierats och godkänts anger AppSources lista för lägen för visuella IAP-objekt ”Ytterligare köp kan krävas” under alternativen för prisnivå.

## <a name="what-is-a-power-bi-visual-with-iap-features"></a>Vad är ett visuellt Power BI-objekt med IAP-funktioner?

Ett visuellt IAP-objekt är kostnadsfria visuella objekt och kostnadsfria funktioner, men har även ytterligare funktioner som kan innebära att extra avgifter kan tillkomma för att driva dem. Utvecklare måste meddela användare i det visuella objektets beskrivning av vilka funktioner som kräver ytterligare köp för att fungera. Microsoft tillhandahåller för närvarande inte inbyggda programgränssnitt (API:er) för att stödja köp i appar och tilläggsprogram. Utvecklare kan använda valfritt betalningssystem från tredje part för dessa inköp. Se vår [butiksprincip](https://docs.microsoft.com/office/dev/store/validation-policies#2-apps-or-add-ins-can-display-certain-ads).

## <a name="logo-guidelines"></a>Riktlinjer för logotyp

I det här avsnittet beskrivs specifikationerna för att lägga till logotyper och logotyper i visuella objekt.

> [!NOTE]
> Logotyper tillåts endast i redigeringsläge. Logotyper kan inte visas i visningsläge.

![definitioner](media/office-store-in-app-purchase-visual-guidelines/definitions.png)

![saker-att-behålla](media/office-store-in-app-purchase-visual-guidelines/things-to-keep-in-mind.png)

![saker-att](media/office-store-in-app-purchase-visual-guidelines/things-to-avoid.png)

![storlek-och-format ](media/office-store-in-app-purchase-visual-guidelines/size-and-format.png)

![marginaler-och](media/office-store-in-app-purchase-visual-guidelines/margins-and-sizes.png)

![redigerings-läge](media/office-store-in-app-purchase-visual-guidelines/logos-in-edit-mode.png)

## <a name="best-practices"></a>Metodtips

### <a name="visual-landing-page"></a>Landningssida för visuellt objekt

Använd landningssidan för att klargöra för användarna hur de kan använda ditt visuella objekt och var de kan köpa licensen. Omfattar inte videor som utlöses automatiskt. Lägg bara till material som hjälper till att förbättra användarupplevelsen, till exempel information eller länkar till information om licensköp, och hur IAP-funktioner används.

### <a name="license-key-and-token"></a>Licensnyckel och token

För att underlätta för användaren lägger du till licensnyckel eller tokenrelaterade fält överst i formatfönstret så att de blir bättre placerade för användarna.

## <a name="next-steps"></a>Nästa steg

Läs hur du kan publicera dina anpassade visuella objekt till [AppSource](office-store.md) där andra kan upptäcka och använda dem.