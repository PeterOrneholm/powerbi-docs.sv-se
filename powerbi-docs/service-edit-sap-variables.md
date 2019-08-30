---
title: Redigera SAP-variabler i Power BI-tjänsten (förhandsversion)
description: Azure och Power BI
author: Sujata994
ms.author: sunaraya
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 08/12/2019
LocalizationGroup: Data from databases
ms.openlocfilehash: db1d4a8a9734c910514b4952b664bf7ebce324c1
ms.sourcegitcommit: 4a3afe761d2f4a5bd897fafb36b53961739e8466
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/20/2019
ms.locfileid: "69654879"
---
# <a name="edit-sap-variables-in-the-power-bi-service-preview"></a>Redigera SAP-variabler i Power BI-tjänsten (förhandsversion)

Vid användning av SAP Business Warehouse eller SAP HANA med DirectQuery kan rapportförfattare nu tillåta slutanvändare att redigera SAP-variabler i **Power BI-tjänsten** för Premium-arbetsytor.

![Dialogrutan Redigera variabler](media/service-edit-sap-variables/sap-edit-variables-dialog.png)

I det här dokumentet beskrivs kraven för att redigera variabler i Power BI, hur du aktiverar den här förhandsgranskningsfunktionen samt var du kan redigera variabler i Power BI-tjänsten.

## <a name="requirements-for-sap-edit-variables"></a>Krav för redigering av SAP-variabler

Det finns några krav för användning av funktionen för att redigera SAP-variabler. I följande lista beskrivs dessa krav.

**Nya filterupplevelsen krävs** – du måste ha [den nya filterupplevelsen](power-bi-report-filter.md) aktiverad för rapporten. Så här kan du aktivera den för din rapport i Power BI Desktop:
- I Power BI Desktop väljer du **Arkiv** > **Alternativ och inställningar** > **Alternativ**
- Under **Aktuell fil** i det vänstra navigeringsfältet väljer du **Rapportinställningar**.
- Under **Filtreringsupplevelse** väljer du **Aktivera det uppdaterade filterfönstret**.

**DirectQuery-anslutningar krävs** – du måste ansluta till SAP-datakällan med hjälp av DirectQuery. Importanslutningar stöds inte.

**Power BI Premium-prenumeration krävs** – funktionen för att redigera SAP-variabler fungerar för närvarande endast i Power BI Premium-prenumerationer.

**Konfiguration av enkel inloggning krävs** – för att den här funktionen ska fungera måste enkel inloggning vara konfigurerad. Mer information finns i [översikten av enkel inloggning (SSO)](service-gateway-sso-overview.md).

**Nya gatewaybitar** krävs – ladda ned den senaste gatewayen och uppdatera din befintliga gateway. Mer information finns i [tjänstgateway](service-gateway-onprem.md).

**Flerdimensionellt endast för SAP HANA** – för SAP HANA fungerar funktionen för att redigera SAP-variabler endast med flerdimensionella modeller och fungerar inte för relationskällor.

**Stöds ej i nationella moln** – för närvarande är Power Query Online inte tillgängligt i nationella moln. Därför stöds den här funktionen heller inte i nationella moln.

## <a name="how-to-enable-the-feature"></a>Så aktiverar du funktionen

Om du vill aktivera funktionen för att **redigera SAP-variabler** ansluter du i Power BI Desktop till en SAP HANA- eller SAP BW-datakälla. Gå sedan till **Arkiv > Alternativ och inställningar > Alternativ** och välj **DirectQuery** i avsnittet Aktuell fil i det vänstra fönstret. När du väljer det visas DirectQuery-alternativ i det högra fönstret samt en kryssruta där du kan **Tillåt slutanvändare att ändra SAP-variabler i rapporten (förhandsversion)** enligt vad som visas i följande bild.

![DirectQuery-alternativ](media/service-edit-sap-variables/sap-preview-setting-in-desktop.png)

## <a name="use-sap-edit-variables-in-power-bi-desktop"></a>Använda redigering av SAP-variabler i Power BI Desktop

När du använder redigering av SAP-variabler i Power BI Desktop kan du redigera variablerna genom att välja länken Redigera variabler i menyn **Redigera frågor** i menyfliksområdet. Därifrån visas följande dialogruta. Den här funktionen har varit tillgänglig i Power BI Desktop ett tag. Rapportskapare kan välja variabler för rapporten med hjälp av följande dialogruta.

![Lägga till objekt](media/service-edit-sap-variables/sap-variables-add-items.png)

## <a name="use-sap-edit-variables-in-the-service"></a>Använda redigering av SAP-variabler i tjänsten

När rapporten har publicerats till Power BI-tjänsten kan användarna se länken **Redigera variabler** i det nya filterfönstret. Om du publicerar rapporten för första gången kan det ta upp till 5 minuter innan länken Redigera variabler visas. Om länken inte visas behöver du uppdatera datamängden manuellt.
Det gör du på följande sätt:

1. I Power BI-tjänsten väljer du fliken **Datamängder** i innehållslistan för en arbetsyta.

2. Leda upp den datamängd som du behöver uppdatera och välj ikonen **Uppdatera**.

    ![Redigera variabler](media/service-edit-sap-variables/sap-edit-variables-link.png)

3. Om du väljer länken Redigera variabler öppnas dialogrutan **Redigera variabler**, där användare kan åsidosätta variabler. Om du väljer knappen **Återställ** återställs variablerna till de ursprungliga värden som visades när den här dialogrutan öppnades.

    ![Dialogrutan Redigera variabler](media/service-edit-sap-variables/sap-edit-variables-dialog.png)

4. Eventuella ändringar i dialogrutan **Redigera variabler** bevaras endast för den här användaren (vilket liknar annat beteende för bevarande i Power BI). Om du väljer **Återställ till standard**, vilket visas i följande bild, återställs rapporten till rapportskaparens ursprungliga tillstånd, inklusive variablerna.

    ![Återställ till standard](media/service-edit-sap-variables/reset-to-default.png)

Vid arbete med en publicerad rapport i Power BI-tjänsten som använder SAP HANA eller SAP BW med funktionen för att **redigera variabler** aktiverad kan rapportägaren ändra de standardvärdena. Ägaren till rapporten kan ändra variablerna i redigeringsläge och spara rapporten så att dessa inställningar kan bli de *nya standardinställningarna* för den rapporten. Alla andra användare som kommer åt rapporten efter att dessa ändringar har gjorts av rapportägaren ser de nya inställningarna som standardinställningar.

## <a name="issues-and-considerations"></a>Problem och överväganden

För närvarande stöds inte funktionen för att redigera SAP-variabler i appar.

## <a name="next-steps"></a>Nästa steg

Mer information om SAP HANA, SAP BW eller DirectQuery finns i följande artiklar:

- [Använda SAP HANA i Power BI Desktop](desktop-sap-hana.md)
- [DirectQuery och SAP Business Warehouse (BW)](desktop-directquery-sap-bw.md)
- [DirectQuery och SAP HANA](desktop-directquery-sap-hana.md)
- [Använd DirectQuery i Power BI](desktop-directquery-about.md)