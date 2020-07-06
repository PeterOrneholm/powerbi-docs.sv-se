---
title: Tips om hur du skapar rapporter i Power BI
description: Metodtips för att skapa rapporter i Power BI-tjänsten och Power BI Desktop
author: davidiseminger
ms.reviewer: willthom
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: how-to
ms.date: 05/07/2020
ms.author: davidi
ms.openlocfilehash: ae9a3695c8db084d9c65871314edfef34cde1cb6
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85238490"
---
# <a name="tips-and-tricks-for-creating-reports-in-power-bi-desktop"></a>Tips om hur du skapar rapporter i Power BI Desktop
För att få ut mesta möjliga av dina data, behövs ibland lite extra hjälp. Vi har samlat några tips och råd som du kan använda när du skapar rapporter i Microsoft Power BI Desktop *och* i Microsoft Excel 2016 eller Excel 2013 Pro-Plus-versioner med Power Pivot-tillägget aktiverat och Power Query installerad och aktiverad. 

## <a name="learning-to-use-the-query-editor"></a>Lär dig att använda frågeredigeraren
Frågeredigeraren i Power BI Desktop liknar Power Query-tillägget i Excel 2013. Det finns flera användbara artiklar i Power BI-supporten med kan du också granska Power Query-dokumentationen på support.office.com för att komma igång.

Du kan få ytterligare information från [Power Query Resource Center](https://support.office.com/article/Microsoft-Power-Query-for-Excel-Help-2b433a85-ddfb-420b-9cda-fe0e60b82a94).

Du kan också visa [Formelreferensen](https://support.office.com/Article/Learn-about-Power-Query-formulas-6bc50988-022b-4799-a709-f8aafdee2b2f).

## <a name="data-types-in-query-editor"></a>Datatyper i frågeredigeraren
När du använder frågeredigeraren i Power BI Desktop för att läsa in data gör vi en uppskattning av den bästa datatypidentifieringen. Datatypinställningarna för kolumner sparas inte allt när du använder formler. Kontrollera att datatypen för kolumnerna är korrekt när du har vidtagit följande åtgärder:  Läs in data initialt till frågefliken, Första raden som rubrik, Lägg till kolumn, Gruppera efter, Sammanfoga, Lägg till och innan du läser in data för första gången.

Det är viktigt att komma ihåg att kursiv stil i datarutnätet inte betyder att datatypen är rätt inställd, det betyder bara att data inte anses vara text.

## <a name="reference-queries-in-the-query-editor"></a>Referensfrågor i Query Editor
När du högerklickar på någon av frågorna i frågeredigerarens navigatör i Power BI Desktop visas alternativet ”Referens”. Det är viktigt av följande anledningar:

* När du använder filer som datakälla för en fråga lagras den absoluta sökvägen till filen i frågan. När du delar eller flyttar Power BI Desktop-filen eller Excel-arbetsboken sparar du tid när du uppdaterar sökvägarna genom att uppdatera den endast en gång i stället för sökvägarna.

Som standard läses alla frågor in i datamodellen. Vissa frågor är mellanliggande steg och är inte avsedda för slutanvändarna. Detta är ofta fallet för referenser till frågor som nämns ovan. Du kan styra inläsningen av frågan genom att högerklicka på frågan i navigatören och växla till alternativet ”Aktivera inläsning”. När *Aktivera inläsning* inte har markerats, kommer frågan fortfarande att vara tillgänglig på frågefliken och du kan använda den med andra frågor. Det är särskilt användbart i kombination med Sammanfoga, Lägga till, och Refererenstransformeringar. Men eftersom resultatet av frågan inte har lästs in till datamodellen kommer frågan inte att störa dina rapporter eller din datamodell. 

## <a name="scatter-charts-need-a-point-identifier"></a>Punktdiagrammet behöver en punktidentifierare
Ta till exempel en enkel tabell med temperaturer och tidpunkten för avläsning av dessa. Om du beskriver detta direkt med ett punktdiagram aggregerar Power BI alla värden i en enda punkt. Om du vill visa individuella datapunkter måste du lägga till ett fält i bucketen Detaljer i fältet. Ett enkelt sätt att göra detta i Power BI Desktop är med hjälp av alternativet ”Lägg till indexkolumn” i menyfliksområdet ”Lägg till kolumn” på frågefliken. 

## <a name="reference-lines-in-your-report"></a>Referensrader i rapporten
Du kan använda en beräknad kolumn i Power BI Desktop om du vill definiera en referensrad. Identifiera tabellen och den kolumn där du vill skapa en referensrad. Välj ”Ny kolumn” i menyfliksområdet och i formelfältet och skriv följande formel:

    Target Value = 100

Det här beräknade kolumnen returnerar värdet 100 oavsett var den används. Den nya kolumnen kommer att visas i fältlistan. Lägg till den beräknade kolumnen Målvärde i ett linjediagram för att visa hur andra serier är relaterade till den specifika referensraden. 

## <a name="sort-by-another-column"></a>Sortera efter en annan kolumn
När du använder ett kategoriskt (sträng)-värde i Power BI för diagramaxlar eller i en utsnitt eller filter är standardordningen alfabetisk. Om du behöver åsidosätta den här ordningen, till exempel för veckodagar eller månader, kan Power BI Desktop sortera efter en annan kolumn. Läs mer i [Sortera efter kolumn i Power BI Desktop](desktop-sort-by-column.md).

## <a name="building-maps-more-easily-with-hints-to-bing"></a>Skapa kartor enklare med tips till Bing
Power BI integrerar med Bing för att tillhandahålla kartkoordinater av standardtyp (en process som kallas geokodning), vilket gör det enklare att skapa kartor. Bing använder vissa algoritmer och tips för att försöka hämta rätt plats, men det är ändå en gissning. Du kan använda följande tips för att öka sannolikheten för rätt geo-kodning:

När du skapar en karta vill du ofta markera länder, regioner och städer. Om du namnger kolumner efter geografisk beteckning i Power BI Desktop hjälper det Bing att gissa vad du vill visa. Till exempel, om du har ett fält med namn på delstater i USA, till exempel ”Kalifornien” och ”Washington” kan Bing återge platsen för Washington, DC, istället för delstaten Washington som svar på ordet ”Washington”. Om du ger kolumnen namnet ”States” förbättras geokodningen. Samma sak gäller för kolumner med namn som Land och Stad. 

Vissa benämningar är tvetydiga när de används i samband med flera länder/regioner. I vissa fall behandlas kan en ”delstat” i ett land/region vara något helt annat i en annan provins eller land. Du kan öka noggrannheten för geokodning genom att skapa kolumner som lägger till flera fält tillsammans och använda dem för att rita upp dataplatser. I stället för att skicka endast ”Wiltshire” kan du skicka ”Wiltshire, England” för att få en mer korrekt geokodning. 

Du kan alltid ange platser med specifik latitud och longitud i Power BI-tjänsten eller Power BI Desktop. När du gör det måste du också skicka ett platsfält. Annars aggregeras dina data som standard så att platsen för longitud och latitud inte blir det förväntade.

## <a name="categorizing-geographic-fields-to-hint-bings-geocoding"></a>Kategorisera geografiska fält för att ge ledtrådar till Bings geokodning
Ett annat sätt att kontrollera att fält är korrekt geokodade är genom att konfigurera datafältens datakategori. Välj önskad tabell i Power BI Desktop, gå till menyfliksområdet Avancerat och ange sedan Datakategori till Adress, Ort, Kontinent, Land/region, Land, Postnummer, Delstat eller Provins. Dessa datakategorier hjälper Bing att koda data korrekt. Läs mer i [kategorisering av data i Power BI Desktop](../transform-model/desktop-data-categorization.md).

## <a name="better-geocoding-with-more-specific-locations"></a>Bättre geokodning med mer specifika platser
Ibland räcker det inte ens med att ställa in datakategorier för mappning. Bygg en mer specifik plats, t.ex. en gatuadress, när du använder frågeredigeraren i Power BI Desktop. Använd funktionen Lägg till kolumn för att skapa en anpassad kolumn. Skapa sedan önskad plats på följande sätt: 

    = [Field1] & " " & [Field2]

Använd sedan fältet som skapas i kartvisualiseringarna. Detta är användbart för att skapa gatuadresser från leveransadressfält som är vanliga i datauppsättningar. Observera att sammanfogning endast fungerar med textfält. Vid behov kan du omvandla gatunumret till en textdatatyp innan du använder det för att skapa en adress.

## <a name="histograms-in-the-query-stage"></a>Histogram i frågesteget
Det finns flera sätt att skapa histogram på i Power BI Desktop. Vi börjar med det enklaste och fortsätter därifrån:

Enkelt histogram – Avgör vilken fråga som histogrammet ska byggas på. Använd alternativet ”Referens” för frågan och skapa en ny fråga och ge den namnet ”FieldName-histogram”. Använd alternativet ”Gruppera efter” på menyfliksområdet ”Transformera” och välj aggregeringen ”Räkna rader”. Se till att datatypen är ett tal för den resulterande aggregeringskolumnen. Sedan kan du visualisera data på rapportsidan. Den här metoden är snabb och enkel att bygga, men fungerar inte bra om du har många datapunkter och den tillåter inte borstning av flera visuella objekt.

Definiera buckets för att skapa ett histogram – Avgör vilken fråga som har fältet som histogrammet ska byggas på. Använd alternativet ”Referens” för frågan och skapa en ny fråga och ge den namnet ”FieldName”. Nu ska du definiera bucketarna med en regel. Använd alternativet Lägg till anpassad kolumn på menyfliksområdet Lägg till kolumn och skapa en anpassad regel. En enkel bucketregel kan se ut så här:

    if([FieldName] \< 2) then "\<2 min" else
    if([FieldName] \< 5) then "\<5 min" else
    if([FieldName] \< 10) then "\<10 min" else
    if([FieldName] \< 30) then "\<30 min" else
    "longer")

Se till att datatypen är ett tal för den resulterande aggregeringskolumnen. Nu kan du skapa histogrammet genom att använda gruppen med teknik som beskrivs i Enkla histogram. Det här alternativet hanterar fler datapunkter, men hjälper ändå inte med borstning.

Definiera ett histogram med stöd för borstning – Med borstning avses när visuella data länkas samman, så att när en användare väljer en datapunkt i ett visuellt objekt, så markerar eller filtrerar övriga visuella objekt de datapunkter som relaterar till den valda datapunkten. Eftersom vi hanterar data i databasfrågor, måste vi skapa en relation mellan tabellerna, och se till att vi vet vilka detaljelement som relaterar till bucketen i histogrammet och vice versa.

Starta processen med hjälp av alternativet ”Referens” för den fråga som innehåller det fält utifrån vilket du vill skapa ett histogram. Ge den nya frågan namnet ”Bucketar”. Låt oss i det här exemplet kalla den ursprungliga frågan ”Information”. Ta sedan bort alla kolumner utom den kolumn som du ska använda som bucket för histogrammet. Använd nu frågefunktionen ”Ta bort dubbletter”. Den finns på snabbmenyn som visas när du markerar kolumnen. Det återstående värdena i kolumnen kommer då att vara unika. Om du har decimaltal kan du först använda tipset om hur man definierar bucketar när man skapar histogram för att få en hanterbar uppsättning bucketar. Nu är det dags att kontrollera de data som visas i frågeförhandsgranskningen. Om du ser tomma värden eller nullvärden måste du åtgärda dessa innan du kan skapa någon relation. Mer information finns i ”Skapa en relation om mina data har nullvärden eller tomma värden”. Med det kan vara problematiskt att använda den här metoden på grund av behovet att sortera. Hur du gör för att få bucketarna att sortera korrekt beskrivs i ”Sorteringsordning: få kategorier att visas i önskad ordning”. 

>[!NOTE]
>Det kan vara bra att tänka på sorteringsordningen innan du skapar några visuella objekt. 

Nästa steg i processen är att definiera en relation mellan ”bucketerna” och ”informationsfrågorna” i bucketkolumnen. Välj **Hantera relationer** i menyfliksområdet i Power BI Desktop. Skapa en relation där bucketar finns i den vänstra tabellen och information i den högra, och markera det fält som du använder för histogrammet. 

Det avslutande steget är att skapa histogrammet. Dra bucketfältet från tabellen ”Bucketar”. Ta bort standardfältet från det resulterande stapeldiagrammet. Dra nu histogramfältet från tabellen ”Information” tabell till samma visuella objekt. Ändra standardmängden till Antal i fältkällan. Histogrammet är resultatet. Om du skapar ett annat visuellt objekt, t.ex. en trädkarta från tabellen Information, så välj en datapunkt i trädkartan om du vill se histogrammet markera och visa den valda datapunkten i förhållande till trenden för hela datauppsättningen.

## <a name="histograms"></a>Histogram
I Power BI Desktop kan du använda ett beräknat fält för att definiera ett histogram. Identifiera tabellen och den kolumn där du vill skapa ett histogram. Skriv följande formel i beräkningsområdet:

> Frekvens: =COUNTROWS(\<Column Name\>)
> 
> 

Spara ändringarna och återgå till rapporten. Lägg till \<Column Name\> och frekvens till en tabell och konvertera till ett stapeldiagram. Se till att \<Column Name\> finns på x-axeln och det beräknade fältet Frekvens ligger på y-axeln.

## <a name="tips-and-tricks-for-creating-relationships-in-power-bi-desktop"></a>Tips om hur du skapar relationer i Power BI Desktop
Ofta, när du läser in datauppsättningar från flera källor hindrar problem som null-värden, tomma värden och duplicerade serier dig från att skapa relationer. 

Låt oss ta en titt på ett exempel: 

Om vi hämtar datauppsättningar från en aktiv kundsupportbegäran och från en annan datauppsättningar med arbetsobjekt med scheman som följande:

> CustomerIncidents: {IncidentID, CustomerName, IssueName, OpenedDate, Status} WorkItems: {WorkItemID, IncidentID, WorkItemName, OpenedDate, Status, CustomerName } 
> 
> 

När vi vill spåra alla incidenter och arbetsobjekt som hör till ett specifikt CustomerName kan vi inte bara skapa en relation mellan dessa två datamängder. Vissa WorkItems kan inte vara relaterade till CustomerName, så det fältet är tomt eller NULL. Det kan finnas flera poster i WorkItems och CustomerIncidents för alla angivna CustomerName. 

### <a name="creating-relationships-in-power-bi-desktop-when-the-data-has-null-or-blank-values"></a>Skapa relationer i Power BI Desktop när data har nullvärden eller tomma värden
Ofta innehåller datauppsättningar kolumner med null eller tomma värden. Detta kan orsaka problem när du försöker använda relationer. Du har i stort sett två alternativ för att hantera problemen. Du kan ta bort rader som innehåller null eller tomma värden. Du kan göra detta med hjälp av antingen filterfunktionen i frågefliken eller om du samkör frågor genom att välja alternativet ”Behåll endast matchande rader”. Alternativt kan du ersätta nullvärden eller tomma värden med värden som fungerar med relationer, vanligtvis strängar som ”NULL” och ”(tom)”. Det finns inga rätta inställningar – när du filtrerar ut frågerader på frågestadiet tas rader bort, vilket kan påverka sammanfattningsstatistik och beräkningar. Den senare metoden bevarar dessa datarader men orelaterade rader visas i modellen, vilket kan leda till felberäkningar. Om du antar denna lösning, se till att du använder filter på Vy/diagram där det behövs för att säkerställa att du får korrekta resultat. Viktigast av allt utvärdera vilka rader som är kvar eller tagits bort och förstå den övergripande effekten på analysen... 

### <a name="creating-relationships-in-power-bi-desktop-when-the-data-has-duplicate-values"></a>Skapa relationer i Power BI Desktop när data har dubblettvärden
Ofta, när du läser in datauppsättningar från flera källor hindrar duplicerade värden dig från att skapa relationer. Du kan lösa detta genom att skapa en dimensionstabell med unika värden från båda datauppsättningar. 

Låt oss ta en titt på ett exempel: 

Om vi hämtar datauppsättningar från en aktiv kundsupportbegäran och från en annan datauppsättningar med arbetsobjekt med scheman som följande:

> CustomerInicdents: {IncidentID, CustomerName, IssueName, OpenedDate, Status} WorkItems: {WorkItemID, IncidentID, WorkItemName, OpenedDate, Status, CustomerName } 
> 
> 

När vi vill spåra alla incidenter och arbetsobjekt som hör till ett specifikt CustomerName kan vi inte bara skapa en relation mellan dessa två datamängder. Vissa WorkItems kan inte vara relaterade till CustomerName, så det fältet är tomt eller NULL. Om du har tomma värden eller nullvärden i tabellen CustomerNames kan du inte skapa en relation – se Skapa relationer om mina data har null – eller tomma värden. Det kan finnas flera poster i WorkItems och CustomerIncidents för alla angivna CustomerName. 

Om du vill skapa en relation i det här fallet måste vi skapa en logisk datauppsättning för alla CustomerNames mellan båda datamängder. Du kan använda följande sekvens för att skapa en logisk datauppsättning på fliken Fråga:

1. Duplicera båda frågor, namnge den första **Temp** och den andra **CustomerNames**.
2. Ta bort alla kolumner i varje fråga *utom* kolumnen CustomerName
3. Använd **Ta bort dubbletter** i varje fråga.
4. I frågan **CustomerNames** väljer du alternativet **Bifoga** i menyfliksområdet. Välj sedan frågan från **Temp**.
5. I frågan från **CustomerNames** väljer du **Ta bort dubbletter**.

Nu har du en dimensionstabell som du kan använda för att relatera till CustomerIncidents och WorkItems som innehåller alla värden för båda. 

## <a name="patterns-to-jump-start-your-use-of-the-query-editor"></a>Mönster för att starta din användning av frågeredigeraren
Frågeredigeraren är ett kraftfullt verktyg som kan manipulera data för att forma och rensa dem så att de kan visualiseras eller modelleras. Det finns några mönster som du bör känna till.

### <a name="temporary-columns-can-be-deleted-after-computing-a-result"></a>Tillfälliga kolumner kan tas bort efter att ha beräknat ett resultat
Du behöver ofta skapa en beräkning i Power BI Desktop som omvandlar data från flera kolumner till en ny kolumn. Detta kan vara komplicerat. Ett enkelt sätt att lösa problemet är att dela upp åtgärden i flera steg. Starta genom att duplicera de inledande kolumnerna. Bygg sedan de tillfälliga kolumnerna. Skapa sedan kolumnen för slutresultatet. Du kan sedan ta bort temporära kolumner så att den slutgiltiga uppsättningen data inte fylls. Det är möjligt eftersom frågefliken utför stegen i ordning. 

### <a name="duplicate-or-reference-queries-followed-by-merge-to-original-query"></a>Dubblett- eller referensfrågor följt av koppla till ursprungsfrågan
Ibland är det praktiskt att beräkna sammanfattande statistik för en datauppsättning. Ett enkelt sätt att göra detta på är att duplicera eller skapa en referens till frågan i frågefliken. Använd sedan **Gruppera efter** för att beräkna sammanfattande statistik. Sammanfattande statistik hjälpa dig att normalisera data i den ursprungliga informationen så att de blir mer jämförbara. Detta är särskilt användbart för att jämföra enskilda värden med helheten. För att göra detta ska du gå till ursprungsfråga och välja alternativet sammanfoga. Sammanfoga sedan data från frågan sammanfattningsstatistik för lämpliga identifierare. Nu är du redo att normalisera de data som behövs för din analys.

## <a name="using-dax-for-the-first-time"></a>Använda DAX för första gången
DAX är formelspråket för beräkningar i Power BI Desktop. Det är optimerat för BI-analys. Det är något annorlunda än vad du är van vid om du endast har använt SQL-liknande frågespråk. Det finns mycket bra resurser online och i dokumentationen för DAX. 

[Lär dig grunderna i DAX i Power BI Desktop](../transform-model/desktop-quickstart-learn-dax-basics.md)

[Data Analysis uttryck (DAX)-referens](/dax/)

[DAX Resource Center](https://social.technet.microsoft.com/wiki/contents/articles/1088.dax-resource-center.aspx)

## <a name="power-bi-service-and-power-bi-desktop"></a>Power BI-tjänsten *och* Power BI Desktop

### <a name="read-or-watch-how-to-design-visually-stunning-reports-and-dashboards"></a>Läsa eller titta på ”Utforma visuellt snygga rapporter (och instrumentpaneler)”
Community-medlemmen Miguel Myers är både dataforskare och grafisk designer. 

![Power BI-rapport](media/desktop-tips-and-tricks-for-creating-reports/power-bi-reports.png)

* [Läs bloggen](https://powerbi.microsoft.com/blog/how-to-design-visually-stunning-reports/)
* [Titta på webbseminariet](https://community.powerbi.com/t5/Webinars-and-Video-Gallery/5-3-17-Webinar-How-to-Design-Visually-Stunning-Power-BI-Reports/m-p/168204?Is=Website)

### <a name="consider-your-audience"></a>Ta hänsyn till din målgrupp
Vilka är de viktigaste måtten som kommer hjälpa dem att fatta beslut? Hur kommer rapporten att användas? Vilka inlärda eller kulturella antaganden kan påverka utformningsvalen? Vilken information behöver din målgrupp för att lyckas?

Var ska rapporten visas? Om den ska visas på en stor skärm kan du placera mer innehåll på den. Om läsarna ska visa den på sina surfplattor blir färre visualiseringar lättare att läsa.

### <a name="tell-a-story-and-keep-it-to-one-screen"></a>Förmedla ditt budskap och begränsa det till en skärm
Varje rapportsida ska kunna förmedla en berättelse vid första anblicken. Går det att undvika rullningslister på sidorna? Är rapporten för plottrigt eller för upptagen?  Ta bort allt utom viktig information som enkelt kan läsas och tolkas.

### <a name="make-the-most-important-information-biggest"></a>Gör den viktigaste informationen störst
Om texten och visualiseringarna på rapportsidan har samma storlek, får läsaren svårt att fokusera på vad som är viktigt. Till exempel är kortvisualiseringar ett bra sätt att visa upp ett viktigt tal på en framträdande plats:  
![Kortvisualisering](media/service-dashboards-design-tips/pbi_card.png)

### <a name="but-be-sure-to-provide-context"></a>Men kom ihåg att tillhandahålla kontexten  

Använd funktioner som textrutor och beskrivningar när du vill lägga till kontext till dina visualiseringar.

### <a name="put-the-most-important-information-in-the-upper-corner"></a>Placera den viktigaste informationen i det övre hörnet
De flesta läser uppifrån och ned, så placera mer allmän information högst upp och visa fler detaljer i den riktning som målgruppen läser (från vänster till höger eller från höger till vänster).

### <a name="use-the-right-visualization-for-the-data-and-format-it-for-easy-reading"></a>Använd rätt visualisering för dina data och formatera den för enklare läsning
Undvik att variera visualiseringarna bara för sakens skull.  Visualiseringar ska skapa en översiktsbild och vara enkla att ”läsa” och tolka.  För vissa data och visualiseringar räcker det med en enkel grafisk visualisering. Men andra data kan kräva en mer komplex visualisering – var noga med att använda rubriker och etiketter och andra anpassningar för att hjälpa läsaren.  

* Var försiktig med att använda diagram som förvränger verkligheten, till exempel 3D-diagram och diagram som inte börjar vid noll. Tänk på att det är förhållandevis svårt för den mänskliga hjärnan att tolka runda figurer. Cirkeldiagram, ringdiagram, måttdiagram och andra runda diagramtyper kan se fina ut, men det finns kanske ett annat visuellt objekt som du kan använda istället?    
* Var konsekvent när du väljer skalor för diagram, bestämmer hur diagram ska dimensioneras och väljer färger för att betecknar värden i diagram.    
* Var noga med att koda kvantitativa data på ett snyggt sätt. Använd inte fler än tre eller fyra siffror när tal visas. Visa mått med en eller två siffror till vänster om decimaltecknet och skala för tusen eller miljoner, det vill säga skriv 3,4 miljoner och inte 3 400 000.    
* Försök att undvika att blanda olika precisions- och tidsnivåer. Kontrollera att tidsramarna är lätta att förstå.  Placera inte ett diagram från förra månaden bredvid filtrerade diagram från en specifik månad det året.    
* Blanda inte heller stora och små mått på samma skala, t.ex i ett linje- eller stapeldiagram.  Som exempel då ett mått är i miljontal och det andra i tusental.  Med en så stor skala är det svårt att se skillnaderna mellan måtten i tusental.  Om du måste blanda så välj en visualisering, t.ex. ett kombinationsdiagram, som tillåter användning av en andra axel.    
* Undvik att fylla dina diagram med dataetiketter som inte behövs. Värdena i stapeldiagram, ***om de är tillräckligt stora***, är vanligtvis så lätta att förstå att man inte behöver visa det faktiska talet.   
* Var uppmärksam på hur [diagram sorteras](../consumer/end-user-change-sort.md). Om du vill uppmärksamma det högsta eller lägsta talet kan du sortera efter mått. Om du vill att användare snabbt ska kunna hitta en viss kategori bland många kategorier, kan du sortera efter axeln.  
* Cirkeldiagram fungerar som bäst med mindre än åtta kategorier. Eftersom man inte kan jämföra värden sida vid sida, är det svårare för att jämföra värden i ett cirkeldiagram än i ett stapel- eller kolumndiagram. Cirkeldiagram är bättre för att visa förhållanden mellan en del och helheten, än för att jämföra delarna med varandra. Och måttdiagram är bra för att visa aktuell status i kontexten för ett mål.    

Mer visualiseringsspecifika anvisningar finns i [Visualiseringstyper i Power BI](../visuals/power-bi-visualization-types-for-reports-and-q-and-a.md).  

### <a name="learn-more-about-best-practice-dashboard-design"></a>Läs mer om bästa praxis för instrumentpanelsutformning
Några av våra favoritböcker är:

* *Storytelling with Data* av Cole Nussbaumer Knafic
* *Data points* av Nathan Yau
* *The truthful Art* av Alberto Cairo
* *Now You See It* av Stephen Few  
* *Envisioning Information* av Edward Tufte  
* *Advanced Presentations Design* av Andrew Abela   

## <a name="next-steps"></a>Nästa steg
* [Grundläggande begrepp för designers i Power BI-tjänsten](../fundamentals/service-basic-concepts.md)
* [Rapporter i Power BI](../consumer/end-user-reports.md)

Har du fler frågor? [Prova Power BI Community](https://community.powerbi.com/)
