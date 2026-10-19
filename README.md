# Vecka 43: Serverless Framework Bootcamp

## Bygg en Serverless Toolbox

I denna övning ska du skapa en mindre serverless-applikation med hjälp av **Serverless Framework**.

Applikationen ska bestå av flera olika Lambda-funktioner där varje funktion har ett eget tydligt ansvarsområde.

Syftet med uppgiften är att träna på att:

* skapa ett Serverless Framework-projekt
* konfigurera funktioner i `serverless.yml`
* arbeta med flera Lambda-funktioner i samma projekt
* skicka data till Lambda-funktioner
* deploya funktioner till AWS

---

## Projektstruktur

Projektet ska minst innehålla följande struktur:

```text
serverless-toolbox/
│
├── functions/
│   ├── ...
│
├── responses/
│   ├── ...
│
├── utils/
│   ├── ...
│
├── serverless.yml
└── package.json
```

Du får självklart skapa ytterligare mappar om du behöver dem.

---

## Funktioner

Din toolbox ska innehålla minst **fyra Lambda-funktioner**.

Du väljer själv vad funktionerna ska göra.

Exempel på funktioner:

### Password Generator

Tar emot önskad längd och genererar ett slumpmässigt lösenord.

```json
{
  "length": 20
}
```

---

### Dice Roller

Tar emot vilken typ av tärning som ska användas och hur många gånger den ska kastas.

```json
{
  "sides": 6,
  "amount": 3
}
```

Kan exempelvis returnera:

```json
{
  "rolls": [3, 6, 2],
  "total": 11
}
```

---

### Temperature Converter

Konverterar mellan Celsius och Fahrenheit.

```json
{
  "temperature": 25,
  "from": "celsius"
}
```

---

### Random Team Generator

Tar emot en lista med namn och delar slumpmässigt upp personerna i grupper.

```json
{
  "people": [
    "Anna",
    "Mohammed",
    "Lisa",
    "Erik",
    "Sara",
    "John"
  ],
  "teams": 2
}
```

---

### Calculator

Tar emot två tal och en operation.

```json
{
  "a": 10,
  "b": 5,
  "operation": "multiply"
}
```

---

### Random Picker

Tar emot en array och returnerar ett slumpmässigt alternativ.

```json
{
  "items": [
    "Pizza",
    "Tacos",
    "Sushi",
    "Hamburgare"
  ]
}
```

Du får självklart hitta på helt andra funktioner.

---

## Deploy

Applikationen ska deployas till AWS med Serverless Framework:

```bash
serverless deploy
```

Kontrollera efter deployment att funktionerna har skapats på ditt AWS-konto.

När du är klar med uppgiften kan resurserna (om ni vill) tas bort med:

```bash
serverless remove
```

---

## Level Up!

För dig som vill ha en större utmaning:

Utöka din toolbox med fler funktioner eller mer avancerad funktionalitet.

Du skulle exempelvis kunna:

* validera inkommande data och returnera fel vid felaktig input
* låta flera funktioner använda samma kod från en `utils`-mapp
* skapa olika environment variables för olika funktioner
* bygga en mer avancerad lösenordsgenerator
* skapa en kortlek och funktioner för att blanda och dela ut kort
* skapa en quizgenerator
* generera slumpmässiga rollspelskaraktärer
* dela in personer i jämnstora lag

Försök framför allt tänka:

> **Vilket ansvar ska just den här Lambdafunktionen ha?**
