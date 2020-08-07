---
title: 'DAX: Använd SELECTEDVALUE istället för VALUES'
description: Vägledning om när du ska använda SELECTEDVALUE-funktionerna.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 11/20/2019
ms.author: v-pemyer
ms.openlocfilehash: 70f28bd916f2c8d9c6ce40e61cd7f4c90a7726f8
ms.sourcegitcommit: 2131f7b075390c12659c76df94a8108226db084c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/03/2020
ms.locfileid: "87537445"
---
# <a name="dax-use-selectedvalue-instead-of-values"></a>DAX: Använd SELECTEDVALUE istället för VALUES

Som datamodellerare kan du ibland behöva skriva ett DAX-uttryck som testar om en kolumn är filtrerad efter ett visst värde.

I tidigare versioner av DAX kunde du göra det här med mönster bestående av tre DAX-funktioner. Funktionerna var [IF](/dax/if-function-dax), [HASONEVALUE](/dax/hasonevalue-function-dax) och [VALUES](/dax/values-function-dax). Här är ett exempel på en sådan måttdefinition. Den beräknar momsbeloppet, men bara vid försäljning till kunder i Australien.

```dax
Australian Sales Tax =
IF(
    HASONEVALUE(Customer[Country-Region]),
    IF(
        VALUES(Customer[Country-Region]) = "Australia",
        [Sales] * 0.10
    )
)
```

I det här exemplet returnerar funktionen HASONEVALUE endast TRUE när ett enskilt värde filtrerar kolumnen **Country-Region**. När värdet är TRUE jämförs funktionen VALUES med den litterala texten ”Australia”. När funktionen VALUES returnerar TRUE multipliceras måttet **Sales** med 0,10 (som motsvarar 10 %). Om funktionen HASONEVALUE returnerar FALSE, om fler än ett värde filtrerar kolumnen, returnerar den första IF-funktionen BLANK.

Användningen av HASONEVALUE är en defensiv teknik. Den måste användas eftersom det kan vara så att flera värden filtrerar kolumnen **Country-Region**. I det här fallet returnerar funktionen VALUES en tabell med flera rader. Om en tabell med flera rader jämförs med en skalär genereras ett fel.

## <a name="recommendation"></a>Rekommendation

Vi rekommenderar att du använder funktionen [SELECTEDVALUE](/dax/selectedvalue-function). Den ger samma resultat som mönstret som beskrivs i den här artikeln, men mer effektivt och elegant.

Måttdefinitionen skrivs nu om med funktionen SELECTEDVALUE.

```dax
Australian Sales Tax =
IF(
    SELECTEDVALUE(Customer[Country-Region]) = "Australia",
    [Sales] * 0.10
)
```

> [!TIP]
> Du kan skicka ett _alternativ resultat_ till funktionen SELECTEDVALUE. Det alternativa resultatvärdet returneras när inga eller flera filter används för kolumnen.

## <a name="next-steps"></a>Nästa steg

Mer information om den här artikeln finns i följande resurser:

- [Data Analysis uttryck (DAX)-referens](/dax/)
- Utbildningsväg: [Använda DAX i Power BI Desktop](https://docs.microsoft.com/learn/paths/dax-power-bi/)
- Har du några frågor? [Fråga Power BI Community](https://community.powerbi.com/)
- Har du förslag? [Bidra till att förbättra Power BI](https://ideas.powerbi.com)
