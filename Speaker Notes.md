# React?

- UI's 
- Library
- Open source
- Functional & declarative programming



# State uitleg met live coding

1. Pak voorbeeld [04] useState
1. Dit is een App component die een counter toont.
1. We willen de counter updaten, dus voegen **+ knop** en **increment functie** toe.
1. Klik op de knop: **er gebeurt niks**.
1. Console.log waarde counter in increment functie: de counter wordt **wel** opgehoogd.
1. Console.log('rendering...') in de component functie toevoegen zodat je kunt zien dat het component gerenderd wordt.
1. We gaan React vragen hoe dit kan. React zegt: "Je moet mij wel vertellen dat die counter verandert".
   Het component wordt nu niet ge-rerendered.
1. Deze variabele is **state**: hij is aan **verandering** onderhevig en de **actuele waarde** moet altijd getoond worden.
1. Om een variabele aan de state toe te voegen gebruik je React's **useState** functie.
1. Roep deze functie aan en geef de **initiële waarde** mee.
1. De useState functie geeft 2 dingen terug: een variabele voor de **actuele waarde**
   en een **functie** om de **nieuwe** waarde aan door te geven.
1. React behandeld state als immutable data: het is jouw component's verantwoordelijkheid om de juiste waarde door te geven.
   Het component moet deze verantwoordelijkheid ook hebben want hij weet wanneer en waarin een state waarde aangepast moet worden.
1. Als je deze variabelen gebruikt om de actuele waarde te tonen en om daarmee de waarde aan te passen,
   dan zorgt ik (React) ervoor dat deze altijd getoond wordt.
1. Eerst gewoon **useState array uittikken**.
1. Increment functie aanpassen.
1. Laten zien dat het werkt.
1. useState refactoren naar **array destruction**.

Nog meer vertellen:
- Je kunt useState meerdere keren aanroepen voor meerdere stukjes state.
- State updaten doe je via events: user, time, network
- Niet elk component heeft state nodig: je kunt state ook doorgeven als props:
  Zowel het stateful component als zijn children worden gere-rendered.
- In een child component kun je de state van het parent component aanpassen 
  door de parent een callback function als props door te laten geven aan het child component.
