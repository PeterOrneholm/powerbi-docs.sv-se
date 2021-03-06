---
title: Använda sammansatta modeller i Power BI Desktop
description: Skapa datamodeller med flera dataanslutningar och många-till-många-relationer i Power BI Desktop
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/15/2020
ms.author: davidi
LocalizationGroup: Transform and shape data
ms.openlocfilehash: 5d7e4be9e3b864e2ccfccf64ac0d4460d0821e0a
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83326597"
---
# <a name="use-composite-models-in-power-bi-desktop"></a>Använda sammansatta modeller i Power BI Desktop

När du tidigare i Power BI Desktop använde en DirectQuery i en rapport tilläts inga andra dataanslutningar, oavsett om det var DirectQuery eller import, för rapporten. Med sammansatta modeller tas den begränsningen bort. En rapport kan sömlöst inkludera dataanslutningar från mer än en DirectQuery, eller importera dataanslutning, i valfri kombination.

Funktionen Sammansatta modeller i Power BI Desktop består av tre relaterade funktioner:

* **Sammansatta modeller**: Låter en rapport ha flera dataanslutningar, inklusive DirectQuery-anslutningar eller import, i valfri kombination. I den här artikeln beskrivs sammansatta modeller i detalj.

* **Många-till-många-relationer**: Med sammansatta modeller så kan du etablera *många-till-många-relationer* mellan tabeller. Det här tillvägagångssättet tar bort krav på unika värden i tabeller. Det tar också bort behovet av tidigare lösningar. Du behöver till exempel inte lägga till nya tabeller bara för att skapa relationer. Mer information finns i [Använda många-till-många-relationer i Power BI Desktop](desktop-many-to-many-relationships.md).

* **Lagringsläge**: Nu kan du ange vilka visuella objekt som frågar serverdelens datakällor. Visuella objekt som inte kräver en fråga importeras även om de är baserade på DirectQuery. Den här funktionen hjälper till att förbättra prestanda och minskar belastningen på serversidan. Tidigare initierade även enkla visuella objekt som utsnitt frågor till serverdelskällor. Mer information finns i [Hantera lagringsläget i Power BI Desktop](desktop-storage-mode.md).

## <a name="use-composite-models"></a>Använda sammansatta modeller

Med sammansatta modeller kan du ansluta till en olika sorters datakällor när du använder Power BI Desktop eller Power BI-tjänsten. Du kan göra dessa dataanslutningar på ett par olika sätt:

* Genom att importera data till Power BI, vilket är det vanligaste sättet att hämta data.
* Genom att ansluta direkt till data i dess ursprungliga källdatabas med hjälp av DirectQuery. Mer information om DirectQuery finns i [Använda DirectQuery i Power BI](../connect-data/desktop-directquery-about.md).

När du använder DirectQuery kan du med sammansatta modeller skapa en Power BI-modell, till exempel en enskild Power BI Desktop-fil *.pbix* som utför någon av följande åtgärder eller båda två:

* Kombinerar data från en eller flera DirectQuery-källor.
* Kombinerar data från DirectQuery-källor och importerar data.

Med sammansatta modeller kan du till exempel skapa en modell som kombinerar följande typer av data:

* Försäljningsdata från ett företagsinformationslager.
* Försäljningsmåldata från en SQL Server-avdelningsdatabas.
* Data som importerats från ett kalkylblad.

En modell som kombinerar data från mer än en DirectQuery-källa eller som kombinerar DirectQuery med importerade data kallas en sammansatt modell.

Du kan skapa relationer mellan tabeller som du alltid har gjort, även om dessa tabeller kommer från olika källor. Alla relationer som är mellan källor skapas med kardinaliteten många-till-många, oavsett deras faktiska kardinalitet. Du kan ändra dem till en-till-många, många-till-en eller en-till-en. Vilken kardinalitet du än ställer in har relationer mellan olika källor olika beteenden. Du kan inte använda DAX-funktioner (Data Analysis-uttryck) för att hämta värden på sidan `one` från sidan `many`. Prestanda kan också försämras jämfört med relationer av typen många-till-många inom samma källa.

> [!NOTE]
> I sammansatta modeller är alla importerade tabeller i princip en enda källa, oavsett underliggande datakälla.

## <a name="example-of-a-composite-model"></a>Exempel på en sammansatt modell

Som ett exempel på en sammansatt modell kan du tänka dig en rapport som har anslutit till ett företagsinformationslager i SQL Server med hjälp av DirectQuery. I det här fallet innehåller informationslagret data för **Sales by Country** (Försäljning per land), **Quarter** (Kvartal) och **Bike (Product)** (Cykel (Produkt)) som du kan se på följande bild:

![Relationsvy för sammansatta modeller](media/desktop-composite-models/composite-models_04.png)

Nu kan du skapa enkla visuella objekt med hjälp av fälten från den här källan. På följande bild visas total försäljning per *ProductName* för valt kvartal.

![Visuellt objekt baserat på data](media/desktop-composite-models/composite-models_05.png)

Men vad händer om du i ett Office Excel-kalkylblad har information om den produktansvariga som har tilldelats till varje produkt, tillsammans med marknadsföringsprioriteten? Om du vill visa **Sales Amount** (försäljningsbelopp) per **Product Manager** (produktansvarig) kanske det inte går att lägga till dessa lokala data i företagsinformationslagret. Eller så kan det ta månader i bästa fall.

Det kanske går att importera dessa försäljningsdata från informationslagret i stället för att använda DirectQuery. Och försäljningsdata skulle sedan kombineras med de data som du har importerat från kalkylbladet. Denna metod är dock orimlig, av samma skäl som gjorde att du började använda DirectQuery. Möjliga skäl:

* En kombination av säkerhetsregler tillämpas i den underliggande datakällan.
* Behov av att kunna visa den senaste informationen.
* Blotta omfattningen av data.

Det är här sammansatta modeller kommer in i bilden. Med sammansatta modeller kan du ansluta till informationslagret med DirectQuery och sedan använda **Hämta data** för ytterligare källor. I det här exemplet upprättar vi först en DirectQuery-anslutning till företagsinformationslagret. Vi använder **Hämta data**, väljer **Excel** och går sedan till det kalkylblad som innehåller våra lokala data. Slutligen importerar vi kalkylbladet som innehåller *produktnamnen*, den tilldelade **säljchefen** och **prioriteten**.  

![Navigatorfönstret](media/desktop-composite-models/composite-models_06.png)

I listan **Fields** (fält) kan du se två tabeller: den ursprungliga **Bike**-tabellen (cykel) från SQL Server och en ny **ProductManagers**-tabell. Den nya tabellen innehåller data som har importerats från Excel.

![Fältvy av tabeller](media/desktop-composite-models/composite-models_07.png)

I **relationsvyn** i Power BI Desktop ser vi nu en ytterligare tabell med namnet **ProductManagers** (produktansvariga).

![Relationsvy av tabeller](media/desktop-composite-models/composite-models_08.png)

Nu behöver vi relatera dessa tabeller till andra tabeller i modellen. Som alltid skapar vi en relation mellan tabellen **Bike** (cykel) från SQL Server och den importerade tabellen **ProductManagers** (produktansvariga). Relationen är alltså mellan **Bike[ProductName]** (cykel [produktnamn]) och **ProductManagers[ProductName]** (produktansvariga [produktnamn]). Som vi nämnde tidigare har alla relationer mellan källor standardkardinaliteten många-till-många.

![Fönstret Skapa relation](media/desktop-composite-models/composite-models_09.png)

Nu när vi har skapat den här relationen visas den i **relationsvyn** i Power BI Desktop precis som man kan förvänta sig.

![Den nya relationsvyn](media/desktop-composite-models/composite-models_10.png)

Nu kan vi skapa visuella objekt med hjälp av något av fälten i **fältlistan**. Den här metoden blandar sömlöst data från flera källor. Till exempel visas totalt *SalesAmount* (försäljningsbelopp) för varje *Product Manager* (produktansvarig) på följande bild:

![Fönstret Fält](media/desktop-composite-models/composite-models_11.png)

I följande exempel visas ett vanligt fall med en *dimensionstabell*, till exempel **Product** (produkt) eller **Customer** (kund), som utökas med extra data som importeras från en annan plats. Det går också att låta tabeller använda DirectQuery för att ansluta till olika källor. För att fortsätta med vårt exempel tänker du dig att **SalesTargets** (försäljningsmål) per **Country** (land) och **Period** lagras i en separat avdelningsdatabas. Du kan som vanligt använda **Hämta data** för att ansluta till dessa data på vanligt sätt som på bilden:

![Navigatorfönstret](media/desktop-composite-models/composite-models_12.png)

Som vi gjorde tidigare kan vi nu skapa relationer mellan den nya tabellen och andra tabeller i modellen och skapa visuella objekt som kombinerar tabelldata. Låt oss titta igen på **relationsvyn**, där vi har skapat nya relationer:

![Relationsvyn med många tabeller](media/desktop-composite-models/composite-models_13.png)

Nästa bild baseras på de nya data och relationer som vi har skapat. Det visuella objektet längst ned till vänster visar totalt *Sales Amount* (försäljningsbelopp) jämfört med *Target* (mål) och variansberäkningen visar skillnaden. Data för **Sales Amount** (försäljningsbelopp) och **Target** (mål) kommer från två olika SQL Server-databaser.

![Bild som visar mer data](media/desktop-composite-models/composite-models_14.png)

## <a name="set-the-storage-mode"></a>Ange lagringsläget

Varje tabell i en sammansatt modell har ett lagringsläge som indikerar om tabellen är baserad på DirectQuery eller import. Lagringsläget kan visas och ändras i **egenskapsfönstret**. Om du vill visa lagringsläget högerklickar du på en tabell i **fältlistan** och väljer sedan **Properties** (Egenskaper). Följande bild visar lagringsläget för tabellen **SalesTargets** (försäljningsmål).

Lagringsläget kan också visas i knappbeskrivningen för varje tabell.

![Knappbeskrivning som visar lagringsläget](media/desktop-composite-models/composite-models_16.png)

För alla Power BI Desktop-filer ( *.pbix*) som innehåller tabeller från DirectQuery och vissa importtabeller visar statusfältet ett lagringsläge som kallas **Kombinerat**. Du kan klicka på den termen i statusfältet och enkelt växla alla tabeller till import.

Mer information om lagringsläget finns i [Hantera lagringsläge i Power BI Desktop](desktop-storage-mode.md).  

> [!NOTE]
> Du kan använda lagringsläget *Blandad* i Power BI Desktop och i Power BI-tjänsten.

## <a name="calculated-tables"></a>Beräknade tabeller

Du kan lägga till beräknade tabeller i en modell som använder DirectQuery. Dataanalysuttryck (DAX) som definierar den beräknade tabellen kan referera till antingen importerade tabeller eller DirectQuery-tabeller eller en kombination av dessa.

Beräknade tabeller är alltid importerade, och data i tabellerna uppdateras när tabellerna uppdateras. Om en beräknad tabell refererar till en DirectQuery-tabell visar visuella objekt som refererar till DirectQuery-tabellen alltid de senaste värdena i den underliggande källan. Visuella objekt som refererar till den beräknade tabellen kan också visa värdena vid tidpunkten då den beräknade tabellen senast uppdaterades.

## <a name="security-implications"></a>Säkerhetsaspekter

Sammansatta modeller innebär vissa säkerhetsaspekter. En fråga som skickas till en datakälla kan innehålla datavärden som har hämtats från en annan källa. I det tidigare exemplet skickar det visuella objekt som visar **Sales Amount** (försäljningsbelopp) per **Product Manager** (produktansvarig) en SQL-fråga till relationsdatabasen för försäljning. SQL-frågan kan innehålla namnen på produktansvariga och deras associerade produkter.

![Skript som visar säkerhetsaspekter](media/desktop-composite-models/composite-models_17.png)

Därför inkluderas information som lagras i kalkylbladet nu i en fråga som skickas till relationsdatabasen. Om den här informationen är konfidentiell bör du överväga säkerhetsaspekterna. Tänk framför allt på följande:

* Alla databasadministratörer som kan visa spårningar eller spårningsloggar kan visa den här informationen, även utan behörighet till de data som finns i den ursprungliga källan. I det här exemplet behöver administratören behörighet till Excel-filen.

* Krypteringsinställningarna för varje källa bör övervägas. Du vill undvika att information hämtas från en källa genom en krypterad anslutning och sedan oavsiktligt tas med i en fråga som skickas till en annan källa genom en okrypterad anslutning.

Power BI Desktop visar ett varningsmeddelande när du skapar en sammansatt modell så att du kan bekräfta att alla säkerhetsaspekter har övervägts.  

Av liknande skäl måste du vara försiktig när du öppnar en Power BI Desktop-fil som skickats från en ej betrodd källa. Om filen innehåller sammansatta modeller kan det hända att information, som någon hämtar från en källa med hjälp av autentiseringsuppgifterna för den användare som öppnar filen, skickas till en annan datakälla som en del av frågan. Den som har skapat Power BI Desktop-filen kan då se informationen. Första gången du öppnar en Power BI Desktop-fil som innehåller flera källor visas en varning. Varningen liknar den som visas när du öppnar en fil som innehåller inbyggda SQL-frågor.  

## <a name="performance-implications"></a>Prestandaöverväganden  

När du använder DirectQuery ska du alltid tänka på prestanda, främst för att se till att källan på serversidan har tillräckligt med resurser för att ge användarna en bra upplevelse. En bra upplevelse innebär att de visuella objekten uppdateras inom högst fem sekunder. Mer information om prestanda finns i [Använda DirectQuery i Power BI](../connect-data/desktop-directquery-about.md).

Användning av sammansatta modeller innebär ytterligare prestandaöverväganden. Ett enda visuellt objekt kan innebära att frågor skickas till flera källor, vilket ofta gör att resultat skickas vidare från en fråga till en annan källa. Den här situationen kan resultera i följande typer av körning:

* **En SQL-fråga som innehåller ett stort antal literalvärden**: Ett visuellt objekt som till exempel begär totalt **Sales Amount** (försäljningsbelopp) för en uppsättning valda **Product Managers** (produktansvariga) skulle först behöva ta reda på vilka **Products** (produkter) som hanterades av dessa produktansvariga. Den här sekvensen måste inträffa innan det visuella objektet skickar en SQL-fråga som innehåller alla produkt-ID:n i en `WHERE`-sats.

* **En SQL-fråga som frågar på en lägre nivå av kornighet med data som senare sammanställs lokalt**: Om antalet **Products** (produkter) som uppfyller filtervillkoret för **Product Manager** (produktansvarig) växer till ett stort antal kan det blir ineffektivt eller olämpligt att ta med alla produkter i en `WHERE`-sats. I stället kan du fråga relationskällan på den lägre nivån av **Products** (produkter) och därefter sammanställa resultaten lokalt. Om kardinaliteten för **Products** (produkter) överskrider en gräns på 1 miljon så misslyckas frågan.

* **Flera SQL-frågor, en per gruppera efter värde**: När sammanställningen använder **DistinctCount** och är grupperad efter en kolumn från en annan källa, och om den externa källan inte stöder effektiv överföring av många literalvärden som definierar grupperingen, så behöver du skicka en SQL-fråga per grupp efter värde.

   Ett visuellt objekt som begär ett distinkt antal **CustomerAccountNumber** från SQL Server-tabellen efter **Product Manager** (produktansvarig) som importerats från ett kalkylblad behöver skicka information från tabellen **Product Managers** (produktansvariga) i frågan som skickas till SQL Server. Den här åtgärden är inte lämplig över andra källor, till exempel Redshift. I stället blir det en SQL-fråga som skickas per **Sales Manager** (försäljningsansvarig) upp till en lämplig gräns, varefter frågan misslyckas.

Vart och ett av dessa fall har sina egna prestandaimplikationer, och de exakta detaljerna varierar för varje datakälla. Även om kardinaliteten för de kolumner som används i relationen mellan de två källorna fortfarande är låg, några tusen, så bör inte prestanda påverkas. När kardinaliteten växer bör du vara mer uppmärksam på hur prestanda påverkas.

Dessutom kan användning av många-till-många-relationer innebära att separata frågor måste skickas till den underliggande källan för varje totalsumma eller delsumma, i stället för att de detaljerade värdena sammanställs lokalt. Ett enkelt visuellt objekt med totalsummor skulle skicka två SQL-frågor i stället för en.

## <a name="limitations-and-considerations"></a>Begränsningar och överväganden

Den här versionen av sammansatta modeller har vissa begränsningar:

För närvarande stöds bara [inkrementell uppdatering](../admin/service-premium-incremental-refresh.md) för sammansatta modeller för datakällor av typen SQL, Oracle och Teradata.

Följande flerdimensionella Live-anslutningskällor kan inte användas med sammansatta modeller:

* SAP HANA
* SAP Business Warehouse
* SQL Server Analysis Services
* Power BI-datauppsättningar
* Azure Analysis Services

När du ansluter till dessa flerdimensionella källor med DirectQuery kan du inte ansluta till en annan DirectQuery-källa eller kombinera den med importerade data.

De befintliga begränsningarna för DirectQuery gäller fortfarande när du använder sammansatta modeller. Många av dessa begränsningarna är nu per tabell, beroende på tabellens lagringsläge. En beräknad kolumn i en importerad tabell kan till exempel referera till andra tabeller, men en beräknad kolumn i en DirectQuery-tabell kan fortfarande enbart referera till kolumner i samma tabell. Andra begränsningar gäller för modellen som helhet, om någon av tabellerna inom modellen är DirectQuery. Funktionerna QuickInsights och Frågor och svar är till exempel inte tillgängliga i en modell om någon av tabellerna i den har lagringsläget DirectQuery.

## <a name="next-steps"></a>Nästa steg

Mer information om sammansatta modeller och DirectQuery finns i följande artiklar:

* [Många-till-många-relationer i Power BI Desktop](desktop-many-to-many-relationships.md)
* [Lagringsläge i Power BI Desktop](desktop-storage-mode.md)
* [Använda DirectQuery i Power BI](../connect-data/desktop-directquery-about.md)
* [Datakällor som stöds av DirectQuery i Power BI](../connect-data/power-bi-data-sources.md)
