# 🧩 Wide Language

A human-first, declarative, composable programming language for the web and beyond.

Wide isn’t just about code.

It’s about bringing clarity where the world gave us clutter.

Let humans speak code that doesn’t punish them for loving the Web.

---

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [Introduction](#introduction)
  - [What's about?](#whats-about)
  - [What's the vibe?](#whats-the-vibe)
- [Language Type System](#language-type-system)
  - [: Type Operator](#-type-operator)
  - [! Not Operator](#-not-operator)
  - [Assigment Operator](#assigment-operator)
  - [Some examples](#some-examples)
- [Default Values](#default-values)
- [Printing on Screen](#printing-on-screen)
  - [Interpolation](#interpolation)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

---

## Introduction

### What's about?

🌐 Declarative

🧘 Minimal, clean, human-centered

🧩 Structured but expressive

💡 A language of intention, not noise

🪄 Magic without mystery

🤝 Human-readable, logic-infused

🔗 Bridging HTML, CSS, logic, and UI into one idea

### What's the vibe?

🧩 Modular Clarity - Represents structured blocks, clean design.

🧘 Calm Logic - The Zen of Wide: no keywords, no chaos.

🌐 Declarative Web - Wide is web-native in philosophy.

🔷 Clear Signal - Clean visual. Feels “componenty” and geometric.

✨ Elegant Simplicity - Represents Wide's minimalist beauty.

💎 Structured Brilliance - Suggests gem-like syntax and structure.

📐 Precise Design - Wide has geometry in its soul.

🕊️ Peaceful Syntax - It doesn’t fight the developer. It flows.

🌿 Organic Structure - Like Lisp, but more readable and modern.

🤍 Clean Slate - Wide isn’t cluttered. It’s humane and new.

## Language Type System

Wide itself has no Keywords like most programming languages do.

It's basic type system looks like this:

| Símbolo | Descrição | Exemplos |
|:---:|--------|--------|
| ? | Boolean (1 para verdadeiro, 0 para falso ) | true/false, yes/no, on/off |
| '' | Char  | letter 'A', number '1', symbol '$' |
| " | String  | "hello", "sweet potatoes", "How are you?" |
| 0 | Integer | 1, 10, 100, 999 |
| 0.0 | Float Number | 20.5%, -5.6°C, 10.9km |
| 0.00 | Double Number | Pi(π)3.14159265358979323846, -23.5505200 lat, -46.6333094 lng |
| <> | Object | Person, Vehicle, Dropdown, Box, Header, Provider |

🧠✨ If you want to make any good use of them you must know 3 operators used to give them meaning and context.

### : Type Operator

When you see it you may say:

- **it's of type**
- or **it returns the type**

**Note**

⚠️ If used alone it means:

- **no type**
-or **no return type**

### ! Not Operator

When you see it you may say:

- **is not**
- **negation of**
- or **it can not be** *(something)*

### Assigment Operator

When you see it you may say:

- **is assigned the value** *(of, from or constant of)*

There's no assignment operator in Wide, it's implicit in the space after any declaration.

But if you really want, you can use `=`, but believe, you won't gonna need that!

### Some examples

```wide
` You read: "isRaining" "is of type" "boolean" "and is assigned the value of" "true"
isRaining:? 1

` "winDirectionInitial" "is of type" "char" "and is assigned the value of" "N"
winDirectionInitial:'' 'N'

` "stationName" "is of type" "string" "and is assigned the value of " "Mauna Loa Observatory"
stationName:"" "Mauna Loa Observatory"

` "stationID" "is of type" "integer" "and is assigned the value of" "72528"
stationID:0 72528

` "currentTemperatureCelsius" "is of type" "float" "and is assigned the value of" "15.5"
currentTemperatureCelsius:0.0 15.5

` "atmosphericCO2ppm" "is of type" "double" "and is assigned the value of" "425.789"
atmosphericCO2ppm:0.00 425.789

` "station" "is of type" "object" "and is assigned the value from an object"
` "such having properties: isRaining, winDirectionInitial, stationName,
` stationID, currentTemperatureCelsius, and atmosphericCO2ppm"
station:<> = <
    isRaining:? 1
    winDirectionInitial:'' 'N'
    stationName:"" "Mauna Loa Observatory"
    stationID:0 72528
    currentTemperatureCelsius:0.0 15.5
    atmosphericCO2ppm:0.00 425.789
/>
```

**Noticed some redundancy?**

⚠️ Type inference could be used:
The provided examples don't need to explicitly declare their types since the compiler is able to find by itself what to use based on the assigned values.

Also, you can just use `:` to improve readability.

```wide
` You just read the same as before

isRaining: 1
winDirectionInitial: 'N'
stationName: "Mauna Loa Observatory"
stationID: 72528
currentTemperatureCelsius: 15.5
atmosphericCO2ppm:= 425.789
station: <
    isRaining: 1
    winDirectionInitial: 'N'
    stationName: "Mauna Loa Observatory"
    stationID: 72528
    currentTemperatureCelsius: 15.5
    atmosphericCO2ppm: 425.789
/>
```

## Default Values

When the type is passed followed by no assigned value a default value will be automatically assigned.

It's mostly a zero, except for string and object types.

These values will be used until you manually assign another.

```wide
` default value is 0 (false)
isRaining:?

` default value is 0 (vazio)
winDirectionInitial:''

` default value is vazio
stationName:""

` default value is 0
stationID:0

` default value is 0.0
currentTemperatureCelsius:0.0

` default value is 0.00
atmosphericCO2ppm:0.00

` default value is <>, also called a 'Fragment'.
station:<>
```

This is also true for the objects' properties:

```wide
station: <
    isRaining:?
    winDirectionInitial:''
    stationName:""
    stationID:0
    currentTemperatureCelsius:0.0
    atmosphericCO2ppm:0.00
/>
```

## Printing on Screen

That seems nice, but how do you print on screen?

To print on screen you just enclose what you want to print inside double quotes ""

```wide
"Hello, Wide!"
```

### Interpolation

You can use curly braces inside double quotes to dinamically output values:

```wide
name: "Wide"
"Hello, {name}!" `outputs: "Hello, Wide!"

price: 9.99
"It's ${9.99}." `outputs: "It's, $9.99."
```

## Variables

As you have already seen, variables are declared just passing the type:

```wide
name:"" "Wide"
```

or letting the compiler do it's job and infer the type:

```wide
name: "Wide"
```

or using the `=` explicit assignment operator, but again, you won't gonna need that!
