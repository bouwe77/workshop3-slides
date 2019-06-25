
# React

- UI's 

- Library

- Open source

- Functional & declarative programming

# Components


# State

- Tekening maken:
    1) Mount
    2) Render (in browser, render !== repaint)
    ---------------
    4) Update state
    3) Events (user, time, network)

# Forms

- Uncontrolled inputs: DOM

- Controlled inputs: state

# useEffect

- Components **renderen UI** en **handelen events** af, de rest is **side effects**

- Voorbeelden: 
    - Initieel inladen data, 
    - Acties n.a.v. state change, 
    - DOM manipulaties en
    - Subscriptions

- useEffect wordt na elke render uitgevoerd, tenzij je een 2e argument meegeeft.

----------------------------------------------------------------------------------------------------------------
****************************************************************************************************************
----------------------------------------------------------------------------------------------------------------

# React?

- UI's 
- Library
- Open source
- Functional & declarative programming

# Components

## Conceptueel

Components zijn de bouwblokken van je applicatie en maken het mogelijk de UI in kleine, 
onafhankelijke en herbruikbare stukjes te verdelen.

***Voorbeeld-website laten zien en aanwijzen***

Waarom is dat?

Een React component heeft alles aan boord: de UI ("html"), eventuele (view) logica, en eventueel "model"

Dat is best veel en daarom is het handig kleine components te maken.

Denk aan voordelen zoals overzichtelijkheid, single responsibility, testbaarheid, herbruikbaarheid.

Alle React components hebben onderling een relatie met elkaar. Dit is een parent-child relatie.

Als je de hele component structuur van je app schematisch weer zou wilen geven dan zie je een boomstructuur.

De parent weet wie zijn children zijn, maar een child weet niet wie zijn parent is.

Dat is een belangrijke reden waarom components herbruikbaar zijn.

Tot zover de conceptuele kant van components, nu gaan we langzaam richting code.

## Concreet

Een React component is gewoon een javascript functie, die altijd UI returned, oftewel hetgeen in de browser getoond wordt.

Die UI lijkt op HTML, maar dat is het niet. Het is JSX, een extensie op javascript waarmee het mogelijk wordt inline in javascript een soortvan HTML te gebruiken.

Deze JSX bevat zowel de markup als eventuele child components.


# State (+live coding!)

1. Pak voorbeeld [04] useState
1. Dit is een App component die een counter toont.
1. We willen de counter updaten, dus voegen **+ knop** en **increment functie** toe.
1. Klik op de knop: **er gebeurt niks**.
1. Console.log waarde counter in increment functie: de counter wordt **wel** opgehoogd.
1. Console.log('rendering...') in de component functie toevoegen zodat je kunt zien dat het component gerenderd wordt.
1. Het probleem is dat React niet weet dat er gerendered moet worden.
1. Deze variabele is **state**: hij is aan **verandering** onderhevig en de **actuele waarde** moet altijd getoond worden.
1. Om een variabele aan de state toe te voegen gebruik je React's **useState** functie.
1. Roep deze functie aan en geef de **initiële waarde** mee.
1. De useState functie geeft 2 dingen terug: een variabele voor de **actuele waarde**
   en een **functie** om de **nieuwe** waarde aan door te geven.
1. React behandeld state als immutable data: het is jouw component's verantwoordelijkheid om de juiste waarde door te geven.
   Het component moet deze verantwoordelijkheid ook hebben want hij weet wanneer en waarin een state waarde aangepast moet worden.
1. Als je deze variabelen gebruikt om de actuele waarde te tonen en om daarmee de waarde aan te passen,
   dan zorgt React ervoor dat deze altijd getoond wordt.
1. Eerst gewoon **useState array uittikken**.
1. Increment functie aanpassen.
1. Laten zien dat het werkt.
1. useState refactoren naar **array destruction**.

Nog meer vertellen:
- Je kunt useState meerdere keren aanroepen voor verschillende stukjes state.
- State updaten doe je via events: user, time, network
- Niet elk component heeft state nodig: je kunt state ook doorgeven als props:
  Zowel het stateful component als zijn children worden gere-rendered.
- In een child component kun je de state van het parent component aanpassen 
  door de parent een callback function als props door te laten geven aan het child component.

# Controlled en uncontrolled inputs

- Controlled = state gebruiken om de ingevulde waardes te kunnen gebruiken.
- Uncontrolled = waardes uitlezen via de DOM via refs

# useEffect

Wat doet een component:
1) Render UI via JSX.
2) Handelt events af (user, time, network)
3) Handelt side effects af, bijvoorbeeld: 
    - Zaken die initeel moeten gebeuren
    - Zaken als gevolg van een state update
    - DOM/browser manipulaties

Dat zijn **SIDE EFFECTS** en die handel je af met de **useEffect** hook.

Voor nu (en gezien de tijd) gaan wij een useEffect maken die alleen initieel bij het mounten
van het component wordt uitgevoerd en dat doe je door een lege array als tweede argument mee te geven.