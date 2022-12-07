# From C# to F# in 30 days

## Introduction

The sound of a phone ringing cuts through the noise of traffic around me. I glance at the screen as the dog pulls on the hand holding the leash, restless to smell the world. A random number is displayed on the screen but I know who it is.

*‘Hello?’ ‘Hi K, this is M from V. We loved your interview and would like to bring you onboard!’*

I’m ecstatic. This was the phone call I’d been waiting for, I got the job. The only caveat? The job utilized F# and while I have extensive knowledge in .NET, the most I know about F# is that the F stands for Functional… probably?

I guess I have to learn F# if I want to keep paying the bills. But where to even start?

## Learning documentation

Learning documentation for F# is surprisingly well-constructed and engaging for what I always considered to be a niche programming language used mostly by PhDs. There is certainly enough information out there for you to be able to learn F# on your own.

As a self-taught developer, organizing myself to learn F# at a reasonable pace and follow a progressive path building on top of previous knowledge and keeping motivation up was a skill I had already developed for many years.

For students who enjoy a more structured lesson plan with an orthodox teaching style, it might be a little harder to find a quality F# course. I did a little skimming and found most learning resources on F# are found freely online, thus require you to create your own “lessons plan”.

## F# at a glance

F# code is quite pleasing aesthetically. It’s concise and tabbing makes for nice clumping of logic, I don’t miss brackets at all. Being able to write F# code in a similar style to C# certainly makes it easy to get started if you have C# experience and adds that extra challenge of making your code idiomatic to F#.

`dotnet fsi` is probably the most powerful tool for a beginner learning F#. Being able to run your code with a single command from the CLI makes for a very enjoyable development cycle with a quick feedback loop.

The largest difference between C# that I felt when working with a F# for a few weeks was the difficulty of finding satisfactory asnwers to my queries on google. Between having a hard time formulating the queries themselves by nature of my inexperience and the scarcity of F# developers overall makes this experience quite more pleasant if you’re writing C# code.

## Concepts

First learning about F# was an interesting experience, to say the least. Immutability as a default is refreshing, the ideas thrown around of a possibility of a codebase being made of only pure functions are fascinating even if you know in a real-world scenario it wouldn’t be possible.

Property based testing blew my mind, it’s so cool. Boiling down your solutions to its most baselike properties and asserting those not only creating small tests which are dependable as well as documenting the behaviour of your solution through those tests at the same you’re forced to truly understand what you’re creating and its context.

## Paradigm shift

Coming from an object-oriented language into a functional one requires quite the paradigm shift. Types and modules aren’t direct replacements for classes and not only do you need to learn a whole new world of acronyms and jargon but you also need to look at problems through a different lens.

Writing functional code heightens the importance of the flow of the data. Implementing strategies such as railway-oriented programming encourage you to write your code in a way data only flows in one direction, where this is not a focus on OOP. Having some experience with LINQ certainly eased the transition into the functional world.

## First hands-on experience

Writing code functionally did not come naturally. As a challenge I decided to write FizzBuzz following some restrictions Scott Wlaschin proposes to encourage code idiomatic to F#. It took a surprising amount of time for me to write code to a simple solution I already knew the answer to.

```fsharp

type fizzBuzzAnswer = { Number: int; Value: string }

let perfectDivision d n = n % d = 0

let fizz = perfectDivision 3
let buzz = perfectDivision 5

let fizzBuzz n =
    match fizz n, buzz n with
    | true, true -> { Number=n; Value="FizzBuzz" }
    | true, _ -> { Number=n; Value="Fizz" }
    | _, true -> { Number=n; Value="Buzz" }
    | _, _ -> { Number=n; Value="" }

let hasValue value answer = answer.Value = value

let isFizzBuzz = hasValue "FizzBuzz"

let extractNumber answer = answer.Number

let findAllFizzBuzzUpTo n =
    [1..n]
    |> Seq.map fizzBuzz
    |> Seq.filter isFizzBuzz
    |> Seq.map extractNumber
    |> Seq.iter (printfn "%d")

findAllFizzBuzzUpTo 10000
```

## Final thoughts

F# is freaking fantastic. It has its pros and cons and I wouldn’t recommend it to a complete newcomer to programming but as an experienced developer I’m glad I have the opportunity to use it professionally.

It brings with itself many upgrades C# is slowly creeping towards but the most enjoyable part of F# for me is that it opened myself to a new perspective on how to write code and in the short period I’ve been experiencing it, I’ve already learned many lessons I’ll bring with me no matter what technology I use to write code in the future.
