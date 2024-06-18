![Banner](Data/Images/FSharp-Exercism-S02E01-Booleans-AnnalynsInfiltration-Banner.png)

### FSharp-Exercism-S02E01-Booleans-AnnalynsInfiltration

This repository my work for the [Exercism](https://exercism.org/) F# track.

### Download Command
`exercism download --track=fsharp --exercise=annalyns-infiltration`

### Submission Command
`exercism submit Exercism\fsharp\annalyns-infiltration\AnnalynsInfiltration.fs"`

![Banner](Data/Images/FSharp-Exercism-S02-Booleans-Title.png)

# Annalyn's Infiltration

Welcome to Annalyn's Infiltration on Exercism's F# Track.
If you need help running the tests or submitting your code, check out `HELP.md`.
If you get stuck on the exercise, check out `HINTS.md`, but try and solve it without using those first :)

## Introduction

## Booleans

Booleans in F# are represented by the `bool` type, which values can be either `true` or `false`.

F# supports three boolean operators: `not` (NOT), `&&` (AND), and `||` (OR).

## Instructions

In this exercise, you'll be implementing the quest logic for a new RPG game a friend is developing. The game's main character is Annalyn, a brave girl with a fierce and loyal pet dog. Unfortunately, disaster strikes, as her best friend was kidnapped while searching for berries in the forest. Annalyn will try to find and free her best friend, optionally taking her dog with her on this quest.

After some time spent following her best friend's trail, she finds the camp in which her best friend is imprisoned. It turns out there are two kidnappers: a mighty knight and a cunning archer.

Having found the kidnappers, Annalyn considers which of the following actions she can engage in:

- Fast attack: a fast attack can be made if the knight is sleeping, as it takes time for him to get his armor on, so he will be vulnerable.
- Spy: the group can be spied upon if at least one of them is awake. Otherwise, spying is a waste of time.
- Signal prisoner: the prisoner can be signalled using bird sounds if the prisoner is awake and the archer is sleeping, as archers are trained in bird signaling so they could intercept the message.
- _Free prisoner_: Annalyn can try sneaking into the camp to free the prisoner.
  This is a risky thing to do and can only succeed in one of two ways:
  - If Annalyn has her pet dog with her she can rescue the prisoner if the archer is asleep.
    The knight is scared of the dog and the archer will not have time to get ready before Annalyn and the prisoner can escape.
  - If Annalyn does not have her dog then she and the prisoner must be very sneaky!
    Annalyn can free the prisoner if the prisoner is awake and the knight and archer are both sleeping, but if the prisoner is sleeping they can't be rescued: the prisoner would be startled by Annalyn's sudden appearance and wake up the knight and archer.

You have four tasks: to implement the logic for determining if the above actions are available based on the state of the three characters found in the forest and whether Annalyn's pet dog is present or not.

## 1. Check if a fast attack can be made

Implement the `canFastAttack` function that takes a boolean value that indicates if the knight is awake. This function returns `true` if a fast attack can be made based on the state of the knight. Otherwise, returns `false`:

```fsharp
let knightIsAwake = true
canFastAttack(knightIsAwake)
// => false
```

## 2. Check if the group can be spied upon

Implement the `canSpy` function that takes three boolean values, indicating if the knight, archer and the prisoner, respectively, are awake. The function returns `true` if the group can be spied upon, based on the state of the three characters. Otherwise, returns `false`:

```fsharp
let knightIsAwake = false
let archerIsAwake = true
let prisonerIsAwake = false
canSpy(knightIsAwake, archerIsAwake, prisonerIsAwake)
// => true
```

## 3. Check if the prisoner can be signalled

Implement the `canSignalPrisoner` function that takes two boolean values, indicating if the archer and the prisoner, respectively, are awake. The function returns `true` if the prisoner can be signalled, based on the state of the two characters. Otherwise, returns `false`:

```fsharp
let archerIsAwake = false
let prisonerIsAwake = true
canSignalPrisoner(archerIsAwake, prisonerIsAwake)
// => true
```

## 4. Check if the prisoner can be freed

Implement the `canFreePrisoner` function that takes four boolean values. The first three parameters indicate if the knight, archer and the prisoner, respectively, are awake. The last parameter indicates if Annalyn's pet dog is present. The function returns `true` if the prisoner can be freed based on the state of the three characters and Annalyn's pet dog presence. Otherwise, it returns `false`:

```fsharp
let knightIsAwake = false
let archerIsAwake = true
let prisonerIsAwake = false
let petDogIsPresent = false
canFreePrisoner(knightIsAwake, archerIsAwake, prisonerIsAwake, petDogIsPresent)
// => false
```

## Source

### Created by

- @ErikSchierboom
