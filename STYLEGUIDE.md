# Styleguide

Alla filer skrivs i filformatet Markdown. Det finns olika varianter av Markdown men vi försöker hålla oss till CommonMark, Github Flavored Markdown och Obsidian Markdown.
Om det är en funktion som bara funkar i Obsidian, kan det vara bra att det fortfarande är möjligt att ta del av informationen i andra editorer.

Detta för att det är ett rent, öppet textformat med extrafunktioner som kan utnyttjas av olika program. Om ett program skulle sluta fungera är det enkelt att flytta över till ett annat.

[Commonmark](https://commonmark.org/) är en standard som många texteditorer stöder. Då mycket av den kod som delas finns på Github så har många editorer stöd för [GFM (Github Flavored Markdown)](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax).

[Obsidians version av Markdown](https://obsidian.md/help/syntax) bygger vidare på GFM och har fler funktioner än vad GFM och Commonmark har.

## Filstruktur

### Filnamn

Användning av förkortningar och unika namn

#### Unika namn

För att `wikilinks` ska fungera så bra som möjligt är det viktigt att en fil inte har samma namn som en fil i en annan mapp. Exempel: `om/abc.md` `källor/abc.md`. Detta kan enklast lösas genom att filnamnet innehåller en del av mappnamnet och separera med bindesstreck `-` `om/abc-om.md`

#### Förkortningar

Långa namn kan ofta ha en förkortning. För att man i filnamnet ska kunna läsa både förkortningen och namnet är det bra att förkortingen står först och namnet inom parentes `KORT (Fullständigt namn)`
Senare kan Obsidians [aliasfunktion](https://obsidian.md/help/aliases) användas för att kunna länka till filen antingen genom förkortningen eller det fullständiga namnet.

### Mappar

Varje fil ska ligga i en mapp. Om en fil kan tillhöra flera mappar, låt den vara i den mapp där den passar bäst eller ändra innehållet så att filen kan delas i två.

### Mallar

För att göra det enkelt som möjligt att skapa liknande filer flera gånger går det att använda sig av mappen `obsidian-mallar`

## Länkar

Obsidian har stöd för både wikilänkar och markdownlänkar medans GFM bara har stöd för markdownlänkar.

* Använd relativa markdownlänkar i brödtext

```markdown
Se [Tekniska Museet](../organisationer/Tekniska%20Museet.md)
```

* Använd wikilänkar i Frontmatter

```yaml
källor:
  - "[[Verksamhetsberättelse 1997]]"
```

* Använd wikilänkar för sidor som ännu inte har skapats, men skulle kunna skapas.

```markdown
Wikilänk till [[finns ej]]
```

## Callouts

I dagsläget har Github bara stöd för fem (`NOTE`, `TIP`, `IMPORTANT`, `WARNING` och `CAUTION`) olika typer men i Obsidian går det att skapa egna.
Ref:

* [Github Alerts](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax#alerts)
* [Obsidian Callouts](https://obsidian.md/help/callouts)

En kompromiss är att använda Github Alerts och sen skriva typen i fetstil (eller liknande). Om wikin senare skulle publiceras på en hemsida skulle det vara möjligt att dra nytta av typen skriven i fetstil genom att skriva ett skript med hjälp av [remark](https://remark.js.org/)

```markdown
>[!NOTE]
>
>**BESLUT**
>
>Riksstämman beslutar att ...
```

>[!NOTE]
>
>**BESLUT**
>
>Riksstämman beslutar att ...

### Obsidian callouts

 Inte bara att man kan ha egna typer. Obsidian har även stöd för expanderbara och minimerbara block (genom att använda `+` och `-` ). Men detta fungerar inte på Github och alerten visas istället som ett vanligt block. Undvik att använda dessa.

```markdown
>[!NOTE]+
> Är expanderad från början, men inte längre en alert på Github
```

>[!NOTE]+
> Är expanderad från början, men inte längre en alert på Github

```markdown
>[!NOTE]-
> Är minimerad från början, men inte längre en alert på Github
```

>[!NOTE]-
> Är minimerad från början, men inte längre en alert på Github

## Diagram

Ref: [Github](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/creating-diagrams), [Obsidian](https://obsidian.md/help/advanced-syntax#Diagram)
För att göra det enkelt att uppdatera ett diagram, använd gärna [Mermaid](https://mermaid.ai/open-source/) som både fungerar på Github och i Obsidian.

## Frontmatter

Frontmatter gör det möjligt för filer att innehålla metadata.

### Properties

Properties kan återanvändas i alla filer och sparas i [.obsidian/types.json](.obsidian/types.json)
Ref: [Obsidian](https://obsidian.md/help/properties)
Skriv gärna egenskaper (`properties`) i frontmatter som med namnet i plural och använd typen `multitext` istället för `text` även när det bara finns ett värde just nu, till exempel:

```yaml
---
personer:
  - [[Namn Namnsson]]
kategorier:
  - läger
  - 1997
---
```

Fördelen med detta är att man i efterhand enkelt kan lägga till fler värden
utan att behöva ändra typen på egenskapen (från text till lista). Det gör det också möjligt att söka och filtrera på egenskapen konsekvent i hela projektet,
oavsett om ett dokument har ett eller flera värden.

## Källor

Om möjligt länka gärna till källor, detta för att man ska kunna gå tillbaka och verifiera, ändra eller lägga till information. Lägg källan som en egen not under
`källor/` och länka till den från de sidor som bygger på den, i stället för att upprepa hänvisningen.

## Automatiska verktyg (valfritt)

För att snygga till texten automatiskt och upptäcka eventuella felaktigheter finns linters och textformaterare.

* [mise](mise.jdx.dev) (en place) är ett verktyg för att kunna installera olika versioner av samma program på samma maskin.

* [hk](hk.jdx.dev) är framtaget av samma utvecklare och är ett verktyg för att automatiskt validera text innan commit eller push.

* [rumdl](https://rumdl.dev/) används för att linta och formattera Markdownfiler. Går att installera direkt genom mise och har inbyggt stöd i hk.

### Installationsinstruktioner

>[!WARNING]
> Det är viktigt att kunna förstå vad man gör när man håller på att konfigurera saker på sin maskin. Generellt tips är att inte följa instruktioner om du inte förstår vad som händer.

>[!NOTE]
> Om man vill installera så lite som möjligt på Windows går det att hämta hem via `winget` som är förinstallerat.

1. [Installera mise]([https://mise.jdx.dev/installing-mise.html#installing-mise]). Det finns för Windows, Mac, och Linux.
2. Öppna en terminal i samma mapp som projektet
   1. Läs först filen `mise.toml` förstå vad den gör.
      1. Installerar hk och rumdl
      2. Konfigurerar git hooks för projektet med hk.
   2. Kör `mise.trust` om du litar på vad som står i filen
   3. Kör sedan `mise install` så kommer alla verktyg som behövs installeras och konfigureras
3. Vid en commit eller push kommer hk att köra rumdl för att validera filerna som har ändrats.
