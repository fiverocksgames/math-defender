---
title: It Made Two Runs on a Real Phone
date: 2026-09-11 21:30:00 +0900
lang: en
category: FIRST PLAYABLE VERTICAL SLICE
summary: The game could complete a stage in the editor, but it kept breaking down on a real Android device. We fixed the screen, touch, placement, and restart path until a second run worked too.
description: How Math Defender's first playable vertical slice finally reached repeatable real-device play on Android.
permalink: /en/journals/2026-09-11-real-device-vertical-slice.html
translation_url: /journals/2026-09-11-real-device-vertical-slice.html
---
In the previous journal, Math Defender finally made it through a whole stage.

Solve problems,
pass Scout,
place heroes,
fight,
reach Result,
and restart.

At the time, that felt like a major line to cross.

Then we put the game on a real Android phone, and the story changed again.

![Math Defender Problem screen after the real-device UI pass](https://fiverocksgames.github.io/math-defender/assets/journals/2026-09-11/problem.png)

*Problem phase during the real-device validation pass. Looking fine in the editor and being readable and tappable on a phone turned out to be different problems.*

At first, the Problem screen was simply too small.
The battlefield did not fit the screen properly.
In Preparation, visible controls did not lead to a usable placement flow.

"It works in the editor" and "you can actually play it on a phone" turned out to be different statements.

We fixed one round and tested again.
The orientation and scale improved, but Scout was still too small.
We fixed that too.

Then touch input was reaching the game, but heroes still would not place.
Dragging a card over a cell could be detected, yet the hero prefab mapping was not resolving correctly in the device build, so the actual placement failed.

Preparation also needed a different interaction model.

The old flow was roughly:

> select hero → select cell → press Place

That multi-step interaction was much less clear on a phone than it had seemed in the editor.
So we changed it to Drag-to-Place: drag a hero card from the Hero Bar at the bottom of the screen and drop it directly onto a battlefield cell.

![Preparation screen with direct drag-to-place from the Hero Bar](https://fiverocksgames.github.io/math-defender/assets/journals/2026-09-11/preparation.png)

*Preparation phase after the interaction change. Instead of several taps, a hero card moves directly from the Hero Bar onto a battlefield cell.*

A valid cell gives feedback.
Dropping places the hero immediately.
Gold is spent.
Battle can start only after a real placement has happened.

The problems did not end in one pass.

Each real-device check exposed another layer:

- text size,
- the Scout screen,
- hero-card presentation,
- touch coordinates,
- grid resolution,
- hero prefab mapping,
- and the clean state after Restart.

If automated tests passed but the phone still blocked the player, we went back and fixed it.
If Journal Capture passed but a finger could not complete the placement flow, we did not call the slice done.

Then, on September 11, we ran the latest build on a real Android device again.

We dragged heroes into place,
started Battle,

![Battle screen after a successful real-device placement flow](https://fiverocksgames.github.io/math-defender/assets/journals/2026-09-11/battle.png)

*Battle phase. The real-device pass verified that placement could lead all the way into an actual battle.*

reached Result,
and pressed Restart Stage.

![Result screen used to verify the restart path](https://fiverocksgames.github.io/math-defender/assets/journals/2026-09-11/result.png)

*Result phase. The acceptance check did not stop here: Restart Stage also had to return to a clean Problem state.*

The game returned to a clean Problem state.

Then we played forward again.

The second run made it back through Preparation and Battle normally.

This time we had verified something slightly more important than "one run reaches the end."

**The game keeps working after the end and can be played again.**

That was enough for the first playable vertical slice to finally cross its acceptance line.

It is still nowhere near a finished game.
The battlefield needs more visual cleanup.
The Hero Bar and placement grid need more polish.
And the bigger question—whether this loop is actually fun enough to repeat—still has to be answered through play.

But now, with a real phone in hand, we can repeatedly do this:

> solve → prepare → fight → see the result → restart

Last time, we learned that "connected" and "playable" were not the same thing.

This time, we learned one more distinction.

"Playable once" and "playable again" are not the same thing either.

So this journal uses two runs as the line.