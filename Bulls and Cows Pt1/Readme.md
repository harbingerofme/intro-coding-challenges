# Bulls and Cows pt1

## Short:
```json
difficulty : 1
tags       : ["console","boardgame"]
```


## Backstory

[Bulls and cows](https://en.wikipedia.org/wiki/Bulls_and_Cows) is an old code-breaking mind or paper and pencil game for two or more players. But with fancy new human technology, we can now play alone! Rejoice!

## Goal

Implement a version of bulls and cows for 1 person. The game is palyed with a fixed secret number of 4 digits.

## Input

There's no startup input. 
All input is provided by the player during runtime.

*Optional: allow a commandline input that sets the secret number.*

The player input will be provided in the following format `DDDD` where each `D` is a number ranging from `0` to `9` inclusive on both ends. 

## Output

After a startup message, the program waits for input before outputting a message of the following format: `EbEc` where each `E` is a number ranging from `0` to `4` inclusive on both ends. `b` and `c` are string literals.
`Eb` represents the number of 'bulls', the amount of numbers guesed correctly.
`Ec` represents the number of 'cows', the amount of numbers that are present in the secret number, but not in the right spot.

The game ends when the string `4b0c` is outputted.

## Examples

* Secret number: `0000`
    1. Input: `1234`. Output: `0b0c`.
    2. Input: `0120`. Output: `2b0c`.
    3. Input: `0000`. Output: `4b`
* Secret number: `6969`
    1. Input: `9696`. Output: `0b4c`.
    2. Input: `6666`. Output: `2b0c`.
    3. Input: `6606`. Output: `1b1c`.
* Secret number `4321`:
    1. Input: `7890`: Output: `0b0c`.
    2. Input: `1234`. Output: `0b4c`.
    3. Input: `3421`. Output: `2b2c`.

