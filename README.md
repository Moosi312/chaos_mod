# EU4 chaos mod
## How it works

As soon as the game starts an event `cm_control_events.1` is fired on which the player chooses how often the chaos event should fire.
This event will then trigger the main control event `cm_control_events.100`. This event will call itself again according to the given time (so the time between the events will aways be constant) and call a random event (this function is a scripted_effect in the file `cm_chaos_effect`).

There are two types of chaos events:
1. Effects: This is a direct effect like "add stability"
2. Modifiers: This is a lasting effect (time it lasts can be altered in the settings decision). The difference is that the event for the effect, not the main control event, will determine if the effect will be good or bad. The modifiers are mostly constructed in a way that there are four possiblities: The tamer ones (a good and bad modifier) and two more insane ones (a terrible and an amazing modifier).

## How to add effects
To add an effect go to the `events` folder and choose the right category from the files `cm_<category>_events.txt`.

Copy the layout of a file above and create your desired effect in the `option`.

Add the event to the `cm_chaos_effect` scripted_effect.

## How to add modifierrs
To add modifiers go to the `common\event_modifers` folder and choose the right category from the files `cm_<category>_modifiers.txt` and add the desired modifiers. Then create a new event for them in the `events\cm_zmodifiers_<category>_events.txt`.

Add the event to the `cm_chaos_effect` scripted_effect.