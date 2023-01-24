---
layout: chapter
title: Going Electric
---

Now we know that, for most of human history, "computers" were people you hired to help you run calculations. You'd give them a *program* of calculation steps you wanted them to carry out, they'd follow your directions and run those calculations. At the end, they would hand you back whatever results your program directed them to produce. Of course, people don't do that anymore: now we have machines to do all this for us!

Over the next few chapters, we're going bridge the gap from human computers to computing machines. We'll see some fundamental design ideas that go into modern computers, and using those ideas, we'll design a classic computer &mdash; the kind you might see in a museum today. That will be our foundation for designing more advanced machines (more like the one you're using to read this book) over the course of the book.

In this chapter, we're going to answer some of the most fundamental questions about computing machines: How do you make a machine that can do math? How do you make it programmable? How is electricity and circuitry involved? What does "digital" computing mean? We won't go too far into details of electronics or circuitry, but we will see the big ideas and *a-ha!* moments that lead to the invention of modern computing.

## First Computing Machines

Speaking of modernity, you might be surprised to learn that computing machine are by no means a modern invention. For as long as we've had human computers, people have also been designing and building computing machines!

So why did we need human computers at all?

For starters, early computing machines were just, kind of ... underwhelming. They were complicated and difficult to build, requiring the kind of precision craftsmanship which made them very expensive, and they required regular maintenance to keep them from jamming up or breaking down. Most of the time, the cost of design, build and upkeep made them more trouble than just hiring someone to do your math for you.

On top of that, early computers also weren't very flexible. You had limited, if any ability to program them. Imagine, for example, you're in the middle of a project, and you get a surprising answer to a calculation problem. You might want to explore this weird answer by doing a different kind of calculation, or check the answer by calculating the same thing in a different way. If your computer is a human, you can just *ask* them to do this new thing;  but if you're using one of those old computing machines, you probably need a whole new machine!

To put that another way: in this book, we've been saying a computer is a *programmable calculator*, and by that definition, early computers were more like calculators than computers. They could do math, but you really can't program them to do any kind of math other than exactly what they were built to do.

Putting it all together, you can see how computing machines only made economical sense over hiring a person when you had one calculation you knew you would need to do over and over and over again, so many times that it'd justify the cost of building a machine instead of just doing it by hand yourself, or hiring someone to help you. But this math all changed in the late 1930s, and for that you can thank a fella named *Claude Shannon*. He'll be the main main character of this upcoming chapter.

## Meet Claude Shannon

[a royalty-free picture, or doodle him by hand]

This is Claude Shannon. To get know Mr. Shannon, start by imagining this scene: it's America in the early 1900s, and you're being given a tour of a place where people do research in math and technology. What kinds of things do you think you'll see on this tour? What do you think the researchers will look like?

For starters, it's likely all the researchers you see will be men. During the early 1900s, sexism was still the norm throughout most of the West, and women were usually forced to the sideline in math and technology research. Women with a knack for math and the sciences during this period had to either attach themselves to men to help publish their ideas, or accept 'lesser' work like computing (the human, by-hand kind). So if you see any women during this tour, most likely they'll be cranking out calculations programmed by men.

What will those men look like? Professional society during that time was a lot more formal than we are today. Most likely, the people you see will all be wearning suits and labcoats and bowties and pocket protecters and thick glasses and they'll have neatly combed hair and clean shaves and they'll refer to each other as "Mr." and "Dr." and so on.

So! You're on this tour, and you see a man in a white labcoat and black bowtie walk up to a man in a neatly ironed suit vest.

[doodle the scene]

The man in the labcoat asks,

"Good morning Mr. So-and-so! Do you by chance have the results from the differential ballistic analsysis program we requested from your department this past Friday?"

"Yes, Dr. Labcoat," responds Mr. So-and-so, "the results are preliminary, but analysis suggests the projectile &mdash;"

At that moment you're interrupted by a wiry man in a tweed suit, who rides up in front of you on a unicycle, carrying a large brass trombone. He lifts it up, blows into the mouthpiece and pulls back on the slide, but instead of playing a loud note, flames leap from the end of the trombone:

[doodle the scene]

Meet Claude Shannon!

[doodle the scene again but this time label Shannon]

In between his tinkering and antics you might expect from a circus performer, Shannon came up with two really big ideas that forever changed the course of computing. The first of those two ideas is the main focus of this chapter; the second, we'll hit on later in this book.

I'm being a little dramatic here: it's not likely Shannon ever hazed a tour group with his unicycle and his trombone. But the story isn't much of an exaggeration either: Shannon really was an accomplished juggler and unicycler, and really did once build himself a flame-throwing trombone for no reason other than having fun building things. Later in his life, Shannonw as hired by Bell Labs and paid a living wage to research, really, whatever he wanted, and it seems in hindsight he must have taken the "whatever you want" part to heart. But our story starts much earlier in Shannon's career. This chapter is about what Shannon published in his masters thesis...

### *A Symbolic Analysis of Relay and Switching Circuits*

Kind of a mouthful, right? This is the title of Claude Shannon's masters thesis, which he published in 1937. If it sounds like gobbledegook, know this: by the time you've finished reading this chapter, you'll know exactly what this title is trying to say!

Shannon's masters thesis was disguised as an incremental improvement in the way telegraph networks can be built: after all, if you're going to publish, it's best to choose a topic with clear and obvious applications. But hidden inside the thesis is something much more interesting: a description of a totally new way to think about making machines that can do math. In fact, it's this idea that still fundamentally powers your computer today! That's why we're so interested in Shannon and this thesis so early in our exploration of modern computers.

On the next page, we'll start by looking at what the "state of the art" in computing machines looked like *before* Claude Shannon's masters thesis. Enter the world of what we today call *analog computing* ...