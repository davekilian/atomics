---
layout: chapter
title: What is a Computer?
---

If we want to know how computers work, it would sure be handy to know what a computer is! Unfortunately for us, most of the definitions out there reach too far into math or philosophy to be very useful for us in this book! For, now let's just say this:

<center><i>A computer is a programmable calculator.</i></center>

It's probably not very clear what this means yet, eh? To understand this a little better, it's useful to see where the word "computer" originally comes from ... ready to wind back the clocks a few decades?

## Computing in the Olden Days

If I asked you to close your eyes and picture a computer, you'd probably think of an electronic device with a screen &mdash; maybe a phone, a laptop, or something with a monitor. But the word "computer" had already been around for hundreds of years before those things!

"Computer" was originally a job you could be hired to do. Back then, computers were brought in to crunch through big numerical problems. Big science and engineering projects had teams of computers working on them. If you've seen the movie [Hidden Figures](https://en.wikipedia.org/wiki/Hidden_Figures), you've already seen a little of what it was like to be a computer in the modern era!

Computers did a lot of the same kinds of calculations you learned in school: addition, subtraction, multiplication, division, with whole numbers, decimals, fractions ... but unlike your schooling, where you did little arithmetic problems just to show someone you knew how to do it, computers' arithmetic built to something greater: they'd string many little problems togeter into one very big computation!

Wonder what kinds of computations they did? Let's find out!

We'll try a little exercise to give us a feel for the kind of work computers did. Since I was talking about *Hidden Figures*, how about an astrophysics example? Let's compute our way through part of an *n-body simulation*: something the women from *Hidden Figures* may very well have computed in real life!

## ... to Outer Space! 🚀

It's time for some 🪐space facts🪐 ...

We're used to thinking of gravity as an invisible force that pulls everything down:

![](figures/fig-2-1.svg)

But gravity is actually *universal*: everything in the universe has a gravitational pull on everything else! So, as the Earth is pulling you down, you're also pulling it back up!

![](figures/fig-2-2.svg)

The Earth is much bigger than you, so your gravity on the Earth barely moves the Earth at all, whereas the Earth's gravity can really get *you* moving fast! There's even bigger stuff than the Earth out there, but its gravity on you is very weak, because it's all so very, very far away.

So if gravity is only strong for big objects close to us, that might lead us to ask: what would happen if there was something really big *and* very close to us? Like, what if another planet the size of Earth just sort of appeared next to us one day?

![](figures/fig-2-3.svg)

Would this new planet's gravity affect the Earth's movement? Definitely. Would the Earth's gravity also affect this planet's movement? Also yes! So you might wonder: what happens next? How do the planets move under the effect of each others' gravity? This question is called the *2-body problem*. It's famous, and it's solved: we know mathematical equations which exactly predict the movement of both planets.

But that all changes when you add a third planet to the mix:

![](figures/fig-2-4.svg)

This is the *3-body problem*, and it's not solved yet &mdash; even with people *trying* to solve it for hundreds of years! Until we solve it (if ever?) we have to resort to a technique called *simulation* if we want to predict these planets' movements.

In short, simulations approximate the path by which each body moves (something we don't have equations to mathematically describe) as a sequence of little straight lines (which we do have equations for &mdash; simple ones, actually!). The result looks like the blue path in the diagram below, which approximates the "true" path in red:

![](figures/fig-2-5.svg)

These simulations are the kind of thing you might have found NASA's computers working on! They're big, long, laborious tasks of computation, but they tell us critical things astronomers need to know. I don't want to get bogged down in the physics, so we'll focus on a small but key step: figuring out how hard gravity is pulling on a body at an instant in time.

Per *Newton's law of universal gravitation*, we can calculate that using this formula:

$$F = G\dfrac{m_1 m_2}{r^2}$$

This is the 'normal' way of writing the formula: using notation you learn in high school algebra. It's just a more compact way of saying

$$F = (G \times m_1 \times m_2) \div (r \times r)$$

Make sense?

So here's how we'll use this formula, as computers: someone will give us a collection of numbers, one for each letter to the right of the equals sign. We'll multiply and divide the numbers the way the formula tells us to, leaving us with just one number. That resulting number is $F$: the thing they're paying us to calculate! We won't bother understanding the physics behind this formula, because as computers, that's not our job &mdash; we're just here to do some arithmetic!

For example, let's say the project scientists give us this table of values:

<div class="overflows" markdown="block">

| $G$                    | $m_1$                  | $m_2$                  | $r$                | $F$  |
| ---------------------- | ---------------------- | ---------------------- | ------------------ | ---- |
| $6.67 \times 10^{-11}$ | $5.97 \times 10^{24}$  | $6.39\times 10^{23}$   | $1.25 \times 10^7$ |      |
| $6.67 \times 10^{-11}$ | $4.87 \times 10 ^{24}$ | $5.97 \times 10^{24}$  | $1.67\times 10^7$  |      |
| $6.67 \times 10^{-11}$ | $6.39 \times 10^{23}$  | $4.87 \times 10 ^{24}$ | $2.02 \times 10^7$ |      |

</div>

See how the $F$ column is empty? It's our job to fill it in! We need to use the rule:

$$F = (G \times m_1 \times m_2) \div (r \times r)$$

To find $F$, we need to figure out which numbers $G$, $m_1$, $m_2$ and $r$ each stand for. We can find those by reading from table. The first row says:

* $G$ should be $6.67 \times 10^{-11}$
* $m_1$ should be $5.97 \times 10^{24}$
* $m_2$ should be $6.39\times 10^{23}$
* $r$ should be $1.25 \times 10^7$

If we replace each letter in the equation with the corresponding number, we end up with this long, messy-looking thing:

<div class="overflows" markdown="block">

$$F = ((6.67 \times 10^{-11}) \times (5.97 \times 10^{24}) \times (6.39\times 10^{23})) \div ((1.25 \times 10^7) \times (1.25 \times 10^7))$$

</div>

Notice how there are no longer any letters to the right of the equals sign? Now we multiply and divide all those numbers together! I won't show all the steps &mdash; to be honest, I used a calculator anyways &mdash; but it all shakes out to this:

$$F = 1.63 \times 10 ^{24}$$

And boom, now we know what to write for the $F$ column in the first row! Let's add it:

<div class="overflows" markdown="block">

| $G$                    | $m_1$                  | $m_2$                  | $r$                | $F$                    |
| ---------------------- | ---------------------- | ---------------------- | ------------------ | ---------------------- |
| $6.67 \times 10^{-11}$ | $5.97 \times 10^{24}$  | $6.39\times 10^{23}$   | $1.25 \times 10^7$ | $1.63 \times 10 ^{24}$ |
| $6.67 \times 10^{-11}$ | $4.87 \times 10 ^{24}$ | $5.97 \times 10^{24}$  | $1.67\times 10^7$  |                        |
| $6.67 \times 10^{-11}$ | $6.39 \times 10^{23}$  | $4.87 \times 10 ^{24}$ | $2.02 \times 10^7$ |                        |

</div>

As computers, our job is now to repeat this process for every row in a table like this. How about you give it a try? Can you find the values of $F$ for the next two rows, by repeating the process we did for the first row?

Feel free to use a calculator like I did &mdash; I promise it's not cheating! 🙂 The kind of calculator you're used to didn't exist back when computing was a person's job, but those people did have their own kind of calculator: mechanical ones, such as slide rules! Nobody cared if computers used calculators for their work: anything that helps them be more accurate and/or finish faster is fair game! That's why you're good to use a calculator too, if you like.

When you're finished, you can check your answers against mine below:

<div class="overflows" markdown="block">

| $G$                    | $m_1$                  | $m_2$                  | $r$                | $F$                    |
| ---------------------- | ---------------------- | ---------------------- | ------------------ | ---------------------- |
| $6.67 \times 10^{-11}$ | $5.97 \times 10^{24}$  | $6.39\times 10^{23}$   | $1.25 \times 10^7$ | $1.63 \times 10 ^{24}$ |
| $6.67 \times 10^{-11}$ | $4.87 \times 10 ^{24}$ | $5.97 \times 10^{24}$  | $1.67\times 10^7$  | $6.96 \times 10 ^{24}$ |
| $6.67 \times 10^{-11}$ | $6.39 \times 10^{23}$  | $4.87 \times 10 ^{24}$ | $2.02 \times 10^7$ | $5.09 \times 10^{23}$  |

</div>

If you got the right answers, then congratulations: you're now a computer! Hope you enjoyed the experience!

We started this chapter by saying a computer was a 'programmable calculator.' This example highlighted the calculation aspect of computing, but what do we mean by *programmable*? For that, let's do a related exercise ...

## Hired Help

Let's say you and your team have been doing a really big, long version of this simulation, with lots and lots of little calculations you have to string together. You and your team of professional computers aren't getting through the calculations fast enough, so you hire help: you bring in a bunch of students from the local middle school!

For the sake of this example, let's say the middle schoolers know nothing about physics and don't really care to learn &mdash; they just want to pick up a little money to pay for Fortnite skins! They're studious though: they're good at arithmetic, and they follow directions perfectly.

Let's write these students some directions for how to compute a row of the table from our previous example!

To help make our instructions crystal clear, let's imagine we give these middle schoolers a specific brand of calculator. This calculator has buttons to do the following things:

* You can **punch in** a number, digit by digit
* You can **add** a new number to the current number
* You can **subtract** a new number from the current number
* You can **multiply** the current number by a new number
* You can **divide** the current number by a new number
* You can also **clear** the number, which resets the calculator

We'll also give these students scratch paper. That way you can have them jot down some numbers they've already calculated and punch them back in later.

That's it! So, given your experience computing rows of our simulation table above, could you tell a middle schooler exactly what to do on that calculator and scratch paper and compute one row of the table? Come up with a set of directions you could give them!

If you have trouble getting started, try this: imagine how *you* would calculate the first line of the table using that calculator and the scratch paper, and watch your own process very closely. Write down the exact set of steps you went through, as a sort of story. Then, turn your story into directions by removing all details about the specific row you were working on! The result should be a set of directions that work for *any* row of the table.

Once you have your directions, you can continue on to the next section and check your solution against mine. I included both my "story" of doing the first row of the table, and the set of directions I gleaned from my story.

### My Solution

There are many ways to turn our computation into calculator steps. Here's how I would have done it for the first line of the table. For reference, here's that row again:

<div class="overflows" markdown="block">
| $G$                    | $m_1$                 | $m_2$                | $r$                | $F$  |
| ---------------------- | --------------------- | -------------------- | ------------------ | ---- |
| $6.67 \times 10^{-11}$ | $5.97 \times 10^{24}$ | $6.39\times 10^{23}$ | $1.25 \times 10^7$ |      |

</div>

Let's start by calculating $(G \times m_1 \times m_2)$:

<div class="overflows" markdown="block">

| Step                                                  | Calculator Value |
| ----------------------------------------------------- | ---------------- |
| **clear** the calculator                              | `0`              |
| **punch in** $G$, which is $6.67\times 10^{-11}$      | `6.67e-11`       |
| **multiply** by $m_1$, which is $5.97 \times 10^{24}$ | `3.98e14`        |
| **multiply** by $m_2$, which is $6.39 \times 10^{23}$ | `2.55e38`        |

</div>

On that piece of paper, we'll write down the value we computed for $(G \times m_1 \times m_2)$, which is $2.55 \times 10^{38}$. Next, let's compute $r \times r$:

<div class="overflows" markdown="block">

| Step                                                     | Calculator Value |
| -------------------------------------------------------- | ---------------- |
| **clear** the calculator                                 | `0`              |
| **punch in** $r$, which is $1.25 \times 10^7$            | `1.25e7`         |
| **multiply** by $r$ again, which is $1.25 \times 10^I 7$ | `1.56e14`        |

</div>

On that piece of paper, we'll write down the value we computed for $r \times r$, which is $1.56 \times 10^{14}$. Now our piece of paper has two numbers on it:

> $(G \times m_1 \times m_2) = 2.55 \times 10^{38}$
>
> $(r \times r) = 1.56 \times 10^{14}$

We're ready to put those together to calculate $(G \times m_1 \times m_2) \div (r \times r)$, the whole thing!

<div class="overflows" markdown="block">

| Step                                                         | Calculator Value |
| ------------------------------------------------------------ | ---------------- |
| **clear** the calculator                                     | `0`              |
| **punch in** $(G \times m_1 \times m_2)$, which our paper says is $2.55 \times 10^{38}$ | `2.55e38`        |
| **multiply** by $(r \times r)$, which our paper says is $1.56 \times 10^{14}$ | `1.63e24`        |

</div>

And voilà, the value for $F$ is:

$$ F =1.63 \times 10^{24}$$

Now, to come up with some directions for those middle school students, I can just put all the steps together and remove information about the exact numbers I was working on!

<div class="overflows" markdown="block">

| Directions                                                   |
| ------------------------------------------------------------ |
| **clear** the calculator                                     |
| **punch in** the number for $G$ in the table row             |
| **multiply** by the number for $m_1$ in the table row        |
| **multiply** by the number for $m_2$ in the table row        |
| Write down that number as $(G \times m_1 \times m_2)$ on your scratch paper |
| **clear** the calculator                                     |
| **punch in** the number for $r$ in the table row             |
| **multiply** by the number for $r$ in the table row          |
| Write down that number as $(r \times r)$ on your scratch paper |
| **clear** the calculator                                     |
| **punch in** the number for $(G \times m_1 \times m_2)$ from your scratch paper |
| **multiply** by the number for $(r \times r)$ from your scratch paper |
| Write down that number of $F$ in the table row               |
| Repeat for the next row of the table                         |

</div>

The exact sequence of steps you chose might be different from mine, but that's okay! As long as your steps work, they're valid.

Take a second look at your direction. In computing, we'd call these directions a *program*. If you've never programmed before, then congratulations on writing your first program! 🎉

If you look it up, a dictionary will tell you the word "program" just means "sequence." That make sense, right? If you go to a piano recital, you might get a piece of paper, also called a "program," which lists the sequence of performances you're about to see. A computer program is also a sequence: a sequence of calculations!

We're now ready to put together what we've learned about programming with what we learned about calculating.

## Programmable Calculators

Now you can see why we were saying "computer" means *programmable calculator*. A computer &mdash; human or machine &mdash; accepts a program (sequence of calculations) and then performs those calculations step by step. Programs are like recipes, while computers are like cooks following those recipes. In our hired help example, the directions we came up with were the program, and the middle schoolers following the directions were the computers! If we were to follow those directions, we'd be the computers instead!

Programs and computers are so linked, it's almost like they're two sides of the same coin. A program does nothing until it's computed, and a computer does nothing unless programmed, but combine the two and something interesting happens! That's why, in the introduction to this book, we said that we need to understand the interaction between software (programs) and hardware (computers) to really get what's going on in your computer.

## Welcome to the Machine

I don't think it'll come as a shock if I tell you that computing-the-job is gone. Human computers were replaced by computing machines a long time ago &mdash; so long, we've all kinda mostly forgotten that computing ever was a human's job in the first place! As if often the case, the reason we replaced humans with machines was efficiency. The machines one-upped us in three important ways:

**Faster**: Early electronic computers could do almost a hundred rows of our simulation table *every second* &mdash; way faster than a human could hope to be able to even read numbers from the table or write down answers, let alone do any of the math!

**Cheaper**: You have to pay people wages if you want them to compute for you; computers only cost the electricity it takes to run them! Sure, buying a computer costs you a bunch of money up front, but then again, so does training people.

**Accurate**: People make mistakes, and when they do, they have to check their work: that costs even more time and money! Electronic computers are unerringly accurate.

There is one downside from the move from man to machine: unlike people, a machines aren't capable of noticing when there's a mistake in the *program* &mdash; they just do exactly what the program says, no matter what!

In the next chapter we'll talk a little about how these computing machines work and why they're made that way. But first, now that you know a little more about computers, there's one last thing I want to tell you about this book...

## What this book is really about

When I say a computer is a "programmable calculator," I'm sort of asking you to take a leap of faith with me. Most people, even people who have used computers all their lives, have never programmed their computers to perform calculations for them. What does a fancy calculator have anything to do with "normal stuff" like watching YouTube, writing essays for school, or messaging people?

One of the most beautiful yet surprising things about computing is that all these things really do, fundamentally boil down to running calculations. Computers were originally invented to automate the work of doing arithmetic for us, just like we described in this chapter, but then we discovered over time our computers could also do all this other stuff too &mdash; stuff our computers were never originally designed to do! Stuff that has changed the way we live.

Yet, it's a bit too simplistic to reduce something like streaming a YouTube video to "just a math problem." That hides a lot of what's going on &mdash; and a lot of the important discoveries we've made since the olden days. That's the stuff this book is about. You'll finish this book with a very good idea of how you get from programming a calculator to modern computing.

We'll get there, but first we have some more foundation to lay. Onward to the next chapter!

## Something Ends, Something Begins

This chapter hopefully gave you a clearer idea of what computers and programs each do, and how they relate to each other. We also started a journey through the history of computing, starting at a time when computers where people, not machines.

In the next chapter, we're going to move to the next era of computing's history. We'll see how people first started trying to make computing machines to replace humans and how we ended up with electronic computers: the kind we use today. We'll learn what a "program" looks like in an electronic world, and a little about how digital computers compute on those programs.

Ready? Let's go!
