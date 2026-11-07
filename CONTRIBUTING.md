# Bidra till wikin

Vi behöver hjälp med att fylla i information om Unga Forskares historia.
Det kan vara saker som vad en förening gjorde, ett läger eller kurs som på något sätt varit kopplat till Unga Forskare, eller vad som hände under ett visst verksamhetsår.

## Personuppgifter

Inga personuppgifter förutom namn får läggas in. Vill du bli borttagen, hör av dig till [Unga Forskare](#kontakt).

## Program

Använd gärna Obsidian eller en annan texteditor som hanterar Markdown väl.

Obsidian är gratis och har bra stöd för att länka samman filer. Projektet använder sig av `frontmatter` för att ange vad dokumentet är för typ och annan metadata, vilket Obsidian hanterar på ett bra sätt.

## Styleguide

Se [STYLEGUIDE](STYLEGUIDE.md) för hur filer namnges och struktureras

## Git och Github

- [Microsoft Learn - Introduktion till Github](https://learn.microsoft.com/sv-se/training/modules/introduction-to-github/)

### Issues

För att minska risken att flera personer arbetar på samma sak eller något som inte passar projektet kan det vara bra att skapa en issue först. I en issue blir det enklare att bolla tankar och idéer och komma fram till vad det är som kan göras.

### Pull request

- [Github Docs - Creating a pull request from a fork](https://docs.github.com/en/pull-requests/how-tos/create-pull-requests/creating-a-pull-request-from-a-fork)

För att det ska bli enkelt att granska och föra in ändringen, låt pullrequesten handla om en sammanhängande ändring.
Det är möjligt att ha en PR som bygger på en annan PR (se [Stacked PRs](https://github.github.com/gh-stack/))

1. Gör en `fork` av projektet
2. Skapa en `branch`.
3. Gör ändringar i projektet. Detta går att göra på två olika sätt
    1. Direkt på Github
    2. Gör en `clone` av din `fork` lokalt på datorn.
        1. Se till att det INTE är en mapp som synkar med program som OneDrive, Dropbox, iCloud eller liknande. Detta för att viktiga git-filer kan försvinna eller blir korrupta av synkningen.
4. Skapa sen en `pull request` till projektet

### Storlek på pull requests

- **Liten PR, färre än 15 noter** — får gärna handla om flera olika saker.
- **Stor PR, 30 noter eller fler** — ska bara handla om **en** sak.

En stor PR kan till exempel vara källan *Protokoll Riksstämman år X*, med
efterföljande PR:er för *Verksamhetsberättelse år X*.

Skälet är att stora blandade PR:er är svåra att granska. Håller sig en
stor PR till en källa går den att läsa igenom i ett svep.

## Kontakt

Skapa en [Issue](#issues) om du undrar över något eller kontakta Unga Forskare (se [kontaktuppgifter](https://ungaforskare.se/kontakta-oss/) på Unga Forskares hemsida)
