---
layout: chapter
title: "Going Electric: Analog Computers"
---

To get a clear picture of what Shannon found out and later published in *A Symbolic Analysis of Relay and Switching Circuits*, let's start by learning about the state of the art in computing machines as it existed for thousands of years before Shannon's ideas. 

Welcome to the world of **analog computing**.

## What are Analog Computers?

Like all computers, analog computers are programmable calculators. What makes them "analog" is that they do their work using moving parts instead of electrical circuitry.

Analog computers were the only kinds of computing machines that existed up until Claude Shannon and the invention of the digital computer around 1940, and in fact, we didn't even start calling them "analog" until we needed to distinguish them from the newer, digital kind of computer. When we call analog computers "analog," we're mostly mean they're "not digital."

Closely related to analog computers are a class of analog *calculators*: devices people use to help them do basic calulations like addition, multiplication, finding square roots, etc. The abacus is an example of an analog computer that goes all the way back to ancient times; the slide rule is another, more recent example. These devices are meant to *aid* a human computer, rather than replace them altogether; on this page, we're going to think about building true computing machines that can cut humans out of the loop altogether!

## Computing in the 19<sup>th</sup>-and-a-Half Century

So, quick thought experiment: say I teleported you back in time, to the mid- to late-1800s. Based on what you've learned so far in the book, and using the technology that was available during the 1800s, how would you try to make a machine that can carry out complex, multi-step calculations for us? The kind you might otherwise hire a human to crank through.

Think about it for a bit! If you get stuck, then try thinking about the problem from the opposite direction: what machinery *was* available during that time? Is there anything you could co-opt and use in your computer? Read on for the author's solution...

<center>* * *</center>

If you had to build a full-fledged computing machine in the 1800s, I bet the inside of your machine will look a lot like the inside of this thing:

[ doodle of a pocket watch ]

Around this time period, pocket watches were growing ever more popular: they were not just convenient, but also getting rapidly cheaper year over year. Cheap, American-made pocket watches pushed the Swiss out of the low-end market for pocket watches, forcing them to focus on the kind of high-end precision-crafted timekeeping they're still known for today.

So if you wanted to build a computing machine in this era, you'd probably want to use the same kinds components as a pocket watch: wheels, rods, springs, and gears.

[ doodle of a pocket watch's internal gear assembly ]

A pocket watch really isn't a bad model for a computing machine; in fact, *every* mechanical watch does at least a little computing! Inside a watch, there's a timekeeping assembly which actually measures the passage of time, producing one 'tick' every second. But the rest of the watch? The stuff that hooks up the timekeeping part to the watch face and its three hands is fundamentally a counting machine. And counting isn't too far off from basic arithmetic!

Think of the lowly gear: a little wheel surrounded by small bumps which are called "teeth."

[ doodle of a single gear with teeth labeled ]

You can use a gear to count by picking one tooth to serve as the number "0," and counting how many teeth past zero the gear has rotated. In the diagram below, the zero-tooth has been rotated 7 teeth from the 12 o'clock position, so we'd 'read' the value of the gear as 7:

[ doodle as described above ]

We can implement a form of multiplication and division by connecting two gears together. By picking gears with different numbers of teeth, we can cause the gears to rotate at predictably different speeds. For example, in the diagram below, the little gear has exactly half as many teeth as our main, counting gear, so a full rotation of the little gear causes only half a rotation of our counting gear: division by two!

[ doodle as described above ]

Addition with gears is a little more tricky, but doable. We won't go into the details here, but the key idea is to realize you can combine counting with multiplication to make addition. For example, to add 5, instead of counting 1 'tick,' you pass that one tick through more gears which multiply by 5; the result is 5 tickets instead of one. Addition by 5! Subtraction works almost the same way: you just run all the gears in reverse.

And voilà: addition, subtraction, multiplication, and division &mdash; in a way that makes it easy to chain the different operations together, without help from a human! Sounds like a computing machine, eh?

A design like this is pretty much the best you're going to get during the 1800s. That's why we should now be unsurprised to learn it's the design chosen by an English mathemtician named Charles Babbage for his 1800s-era computing machine: *The Difference Engine*.

## The Difference Engine

[ royalty-free picture of babbage, or make a fun doodle. [Maybe this one?](https://en.wikipedia.org/wiki/Charles_Babbage#/media/File:Charles_Babbage_by_Antoine_Claudet_c1847-51-crop.jpg) ]

Charles Babbage was an academic mathematician active throughout the early 1800s. Among the things he worked on, he's best known for his early ideas on computing machines.

In Babbage's time, it was common for governments and universities took it upon themselves to ease computational work by publishing *reference tables*: books filled with tables of completed calcultions. With a reference table in hand, regular folk like you and me could look up the numbers we wanted to know instead of calculating them by hand. For example, here's part of a reference table of square roots:

<div class="overflows" markdown="block">

| Number | Square Root   |
| ------ | ------------- |
| 0      | 0             |
| 1      | 1             |
| 2      | 1.41421356237 |
| 3      | 1.73205080757 |
| 4      | 2             |
| 5      | 2.2360679775  |
| ...    | ...           |

</div>

As the story goes, Babbage once took it upon himself to check some popular, widely-used reference tables by redoing the calculations by hand, only to disappointedly find they contained several mistakes. That got him thinking. These reference tables are relatively simple to make: you just do the same calculation steps over and over on every possible set of numbers ... which sounds like something you could build a machine to do! That machine would be expensive, but then again, it's also expensive to make these tables &mdash; and doubly expensive for people to use tables that contain mistakes! A machine could make the same tables, probably faster than humans, with a guarantee of never ever making one mistake.

So was born the idea for Babbage's **Difference Engine**: a design for a mechanical computer specifically for building certain kinds of reference tables for publishing.

[ doodle or royalty-free image of the completed design. [Maybe this one?](https://en.wikipedia.org/wiki/Charles_Babbage#/media/File:Difference_engine_plate_1853.jpg) ]

Just like our design above, Babbage designed his Difference Engine as a complex mass of wheels, gears, rods, and springs all connected together: the same basic ideas as the pocket watch gears we talked about before. Babbage made a small-scale prototype to prove the concept worked, then brought the idea to the British government, who agreed this machine would be valuable. The British funded Babbage to build a full scale difference engine.

It was never finished.

Years later, the British government cut the Difference Engine project after having already paid *10 times* the initial estimated budget, still with no end in sight! What went wrong? Well, it's exactly like we said before: with the technology of the time, machines like the Difference Engine were just more complex than they were worth! The design for the full-scale Difference Engine called for over 25,000 parts, weighing in at a total of over 4 tons! Even when there was a will and a way, it just wasn't economical to build these machines yet!

> To be fair, another important reason the Difference Engine failed was because Babbage got distracted designing a newer and even grander design: a computing machine he dubbed the *Analytical Engine*. It never got built either, but the design is important nonetheless; we'll talk more about it in this book's next chapter!

And so was the state of the art in computing machines in the 1800s: we had ideas, but couldn't quite iron out the details or make the costs work out. A hundred years later, however, this situation had shifted.

## Onward to the 20<sup>th</sup> Century!

By the early 1900s, several things that were holding back Babbage and the Difference Engine had improved thanks to the ongoing march of technical advancement.

A hundred years after Babbage, **electricity** had evolved from a curiosity to an increasingly popular way to power everything from businesses to homes. It was now feasible to build computing machines powered by big, beefy motors: you no longer needed to make the machine small enough to be human-powered!

At the same time, **materials** had improved significantly. All the interest in building railroads throughout the 1800s had led to several breakthroughs in making stronger, durable metals cheaply. The parts you'd want for a computing machine were now cheaper *and* more reliable.

Finally, innovations in **processes** like the invention of the assembly line in factories made mass-producing parts cheap and commonplace. You could now very easily obtain 25,000 gears and other parts, and they'd be relatively cheap compared to what they cost Babbage in the early 1800s &mdash; not to mention lighter and stronger!

All of a sudden, full-fledged computing machines were starting to look *very* feasible. Around 1930 or so, a man named Vannevar Bush was one of the first people to feel the winds were changing.

## Vannevar Bush and the Differential Analyzer

[ royalty-free picture or doodle of Bush. Maybe [this one?](https://en.wikipedia.org/wiki/File:Vannevar_Bush_portrait.jpg) ]

Vannevar Bush is the kind of person you want as a technical leader. An accomplished engineer and inventor himself, he had a knack for people, both in convincing people to fund his work, and in finding people even better suited to work on his own projects than himself. During World War II, he directed all of the United State's wartime scientific research, and was the de facto liaison between the scientific community, the government, and the broader community. But before all of that, he was building a computing machine at MIT.

[ royalty-free picture or doodle of the differential analyzer ]

By 1930, the world had moved on passed the reference tables Babbage was working on. As we turned our gaze toward the heavens, trying to figure out how to fly or even go to space, we were faced with a different kind of problems: a part of calculus called a **differential equation**.

Remember all the way back to the last chapter, when we were trying to simulate steps of the three-body problem?

![](../figures/fig-2-4.svg)

Remember how we said nobody knows if it's even *possible* to find an exact mathematical description of how these bodies will move under each other's gravity? The three body problem is really a set of differential equations, just like the ones that were vexing airplane and rocket engineers in the early 1900s. And like with the three-body equations, these newer differential equations were looking *intractable*: it didn't look hopeful that we'd ever find ways to exactly solve them using calculus. We needed some way to simulate our way through them; that is, we needed a new computing machine: the **differential analyzer**.

The principles for a calculus-solving computing machine had already been figured out in the late 1800s, with a mechanical computing device called a **ball-and-disk integrator**:

[ public domain image hopefully ]

It's hard to describe exactly what this device does unless you already know calculus. For now, let's just say this: just as calculus is the math of dealing with infinitely many, infinitely small quantities, a ball-and-disk integrator works like a system of gears with infinitely many, infinitely small teeth. As you keep adding more and more teeth to a gear, the results look progressively less like gears and progressively more like wheels:

[ my own doodle showing this ]

By the early 1900s, people had already made differential analyzers &mdash; computing machines based on the ball-and-disk integrator &mdash; for small differential equations, but ran into problems trying to scale them up to the large differential equations aeronautical engineers were trying to solve. It seemed like making a big differential analyzer was infeasible until, one day, it didn't. Vannevar Bush, always with his ear to the ground, and his team were some of the first people to notice. Bush secured funding from MIT to build his own large-scale differential analyzer based on state-of-the-art mechanical and electrical technology.

One day, they hired on an MIT grad student named Claude Shannon. Remember him?

[ bring back the doodle with the unicycle and the flamethrower ]

## Claude Shannon's Big Idea

Vannevar Bush's Differential Analyzer was designed to find solutions to differential equations of up to 18 variables; for example, that'd be like being able to solve the three-body problem, the four-body problem, and so on, all the way up to the eighteen-body problem.

*Up to.*

A key aspect of Bush's Differential Analyzer design was reconfigurability &mdash; a precursor to what you and I would call *programmability*. The Differential Analyzer could solve systems of up to 18 variables, but if you had only, say, 3 variables you needed to solve for, you wouldn't want to deal with the machinery for those other 15 unused variables. So Bush's Differential Analyzer had a complex network of switches for disconnecting and reconnecting parts of the machine, allowing an operator to decide which components of the machine would be used and which would remain offline. The student they hired on to work these switches was none other than Claude Shannon.

[ doodle-shannon standing over the machine ]

Day-in, day-out, Shannon sat there, thinking about switches, optimizing switches, flipping switches, troubleshooting switches, maintaining switches, probably answering questions about switches... Eventually, all this thinking about switches gave him a weird idea about switches:

<center>You can do any math you want using just these switches.</center>

If you have a network of interconnected switches, you can set up that network in a way that lets you do addition, subtraction, multiplication, division ... any math you want. You don't need gears, wheels, rods, balls, disks, or springs. You don't need any moving parts. You just need electricity and switches, connected together in very specific ways. Today, we call such a circuit a **digital circuit**, and we call the computers based on those circuits **digital computers**. The switch-network is the principle your computer is running on, right in front of you, right now! One small idea for Claude turned out to be one giant leap for mankind.

Claude Shannon published this idea in his masters thesis, *A Symbolic Analysis of Relay and Switching Circuits*, in 1937. His thesis was met with the collective forehead-slaps and *oohhh duhh*'s of the entire community of computing machine designers. The 'digital revolution' had begun!

Up ahead in this chapter, we're going to go over what exactly Shannon figured out and published in his masters thesis. What does it mean to do math using networks of switches? Shannon's idea was to connect two different fields: the mathematics of **Boolean algebra** and the engineering of **switching circuits**. In fact, when he was asked about his thesis, Shannon once implied he made this connection simply by being lucky enough to be the first person who knew both disciplines well. So, let's go learn the basics of each!

Coming up next, we're going to learn a little about Boolean algebra, a niche branch of mathematics invented by George Boole in the mid-1800s. After that, we'll take a shallow dive into electronics and switching circuits. Once we know a little about both, we'll be ready to put it together, and deconstruct what Shannon published in his thesis &mdash; and thereby construct the basis of a modern computer.

Get hyped!

