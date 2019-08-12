---
title: Pseduocode
date: 2019-08-12
tags:
---

In undergrad, I took a few programming courses where we didn’t write any code until we learned how to conceptualize the problem we were trying to solve with pen and paper. The professors introduced this as pseudocode: writing out the intended behavior of an algorithm, step by step in a language that can't be compiled on a computer. Normally, this will be similar to the language that you speak.

You've probably heard of the rubber duck method: you talk through your problem to some inanimate object, like a rubber duck. Without going through the science of how this works, the purpose is to talk through the problem out loud with for a clearer understanding of what you're trying to solve and/or a better idea of the algorithm needed to solve it. Pseudocode is great supplement or alternative to the rubber duck method because it applies the same principles, but written down.

## Writing Pseudocode

There really aren't any strict rules when it comes to writing pseudocode, but one rule you should try to follow is to avoid any language specific syntax. You should be able to read it aloud, but not compile it on your computer. Also, there's no rules on what you use to write it out on. For example, I like to write with pen and paper in my work journal, but will sometimes to type it out in code comments.

When I teach beginning web development to students, where we learn about pseudocode before getting started on JavaScript. Here's the 4 step process I teach for writing pseudocode:

- Write the steps
_Write out all the things that should happen. One tactic I like to use is writing the first and last steps, then working through what happens in between._

- Identify things that can change over time
_Typically, these are identified as variables that will be used in your code._

- Identify conditions, decisions, and repeatable steps (if/else, loops)
_These will most likely be control syntax like if/else statements and loops in your code._

- Put it all together and organize
_You might end up with a "draft" version if writing it out on pen and paper. Just like source code, it can be beneficial nice to have a history of your thought process and work, so keep that draft around!_ 

**Bonus Step**: _Don't overthink it!_
Problem solving approaches are subjective: pseudocode is a written representation of your tried and true approach. You're the expert. You can be as descriptive or concise as you'd prefer. These steps are just a guideline and can be followed in any order that works best for you. Your pseudocode may not be exact representation of your code in the end, and that's ok!

## Examples

I keep a work journal that I write in a bullet journal-like format and leave space every day for notes, including pseudocode. This pseudocode is from a sample I built:

![author's pseudocode for a project](/img/release-note-pseudo_2.jpg)

In my web development class, I write pseudocode to guide students through the procedural steps of completing each homework assignment. 

The following is homework I assigned, where we built a small guessing game. The user will need to guess a random number between 1-25. If they haven't guessed the correct number after 5 guesses, then they lose the game. The user will win if the user guesses the correct number. Here's what a completed assignment can look like:

<div class="glitch-embed-wrap embed" style="height: 420px; width: 50%;">
  <iframe
    src="https://glitch.com/embed/#!/embed/tranquil-parakeet?path=&previewSize=100"
    title="undefined on Glitch"
    allow="geolocation; microphone; camera; midi; vr; encrypted-media"
    style="height: 100%; width: 100%; border: 0;">
  </iframe>
</div>


Here's the pseudocode that came with the assignment:

```
1. User types guessed number in textbox
2. User clicks button to guess number
3. If already guessed more than 5 guesses
    Display “game over, you lost”
    End
   Else
    Compare to winning number
4. If guess is equal to winning number
    Display “you won, game over”
    End
   Else
    Display “wrong, guess again”
    Back to step 1
```


## Closing Thoughts

If you're working through a complex problem and coming up with more questions than answers, try pseudocode! Taking a step away from your code to explicitly define the problem can bring you closer to a solution. 