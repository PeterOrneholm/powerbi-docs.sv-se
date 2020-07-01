---
title: Ändra anslutningssträngar för datakällor med PowerShell
description: Ändra anslutningssträngar för datakällor med hjälp av API:er i PowerShell – Power BI-rapportserver.
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: how-to
ms.date: 01/21/2020
ms.author: maggies
ms.openlocfilehash: bb769937e99cd3e936d7f5f3967e8f17b939242c
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85236066"
---
# <a name="change-data-source-connection-strings-in-power-bi-reports-with-powershell---power-bi-report-server"></a>Ändra anslutningssträngar för datakällor i Power BI-rapporter med PowerShell – Power BI-rapportserver


Du kan ändra anslutningssträngar för datakällor i Power BI-rapporter på Power BI-rapportservern med hjälp av API:er i PowerShell. 

> [!NOTE]
> För närvarande fungerar den här funktionen bara för DirectQuery. Stöd för import och datauppdatering kommer.

1. Installera PowerShell-cmdletarna för Power BI-rapportservern. Du hittar Leta rätt på cmdletarna och installationsinstruktioner på [https://github.com/Microsoft/ReportingServicesTools](https://github.com/Microsoft/ReportingServicesTools). 

2. Hämta information om befintliga datakällor i Power BI-filen via PowerShell-cmdletarna:

    ```powershell
    Get-RsRestItemDataSource -RsItem '/MyPbixReport'
    ```

    Så här visar du information för den första datakällan i Power BI-rapporten: 

    ```powershell
    $dataSources[0]
    ```

3. Uppdatera informationen om anslutningar och autentiseringsuppgifter efter behov. Om du uppdaterar anslutningssträngen och datakällan använder lagrade autentiseringsuppgifter måste du ange kontots lösenord. 

    Så här uppdaterar anslutningssträngen för en datakälla:

    ```powershell
    $dataSources[0].ConnectionString = 'data source=myCatalogServer;initial catalog=ReportServer;persist security info=False' 
    ```

    Så här ändrar du typ av autentiseringsuppgifter för en datakälla:

    ```powershell
    $dataSources[0].DataModelDataSource.AuthType = 'Integrated'
    ```

    Så här ändrar du användarnamn/lösenord för en datakälla:

    ```powershell
    $dataSources[0].DataModelDataSource.Username = 'domain\user'
    ```
    ```powershell
    $dataSources[0].DataModelDataSource.Secret = 'password'
    ```

4. Spara de uppdaterade autentiseringsuppgifterna på servern igen.

    ```powershell
    Set-RsRestItemDataSource -RsItem '/MyPbixReport' -RsItemType 'PowerBIReport' -DataSources $dataSources
    ```

## <a name="next-steps"></a>Nästa steg

[Datakällor i sidnumrerade rapporter på Power BI-rapportservern](connect-data-sources.md) 

Fler frågor? [Fråga Power BI Community](https://community.powerbi.com/)
