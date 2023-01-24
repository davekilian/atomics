---
layout: chapter
title: Representing Numbers
---

TODO

Including an old draft of the binary page below. This was originally in the intro chapter, but I cut out everything except the discussion of binary. Things like hex should go here. We should also rehash binary.







---

A computer is a programmable calculator, so if we're going to build one, we're going to need to deal with numbers. Just about every modern computer uses binary to represent numbers, so understanding how computers work means learning a thing or two about binary. If that sounds intimidating, don't worry! Binary looks weird, but it's easy to understand once you get the basic idea &mdash; like everything else in computing, binary was invented by humans, to be convenient for humans. Once you get the basic idea it won't seem so cryptic anymore.

Binary is an example of a number system: it's just a way of writing numbers down. There are many number-writing systems, each providing its own way of writing down numbers. Different systems might each have a different way of representing any particular number: for example, if I asked you to write down the number of days in a week, you'd probably write $7$, but if I asked an ancient Roman to do the same thing, the Roman (using Roman numerals) would probably write that as $VII$. Two systems for writing down numbers, but it's the same number either way!

> If you're now trying to visualize what $7$ means without using a numbering systems, try not to for now. It's an interesting mathematical or philosophical question, but it's not important for this discussion, and you could end up more confused than when you started!
>
> To put it simply, numbers are tied to your numbering system the same way words are tied to languages: two languages can have two different words that mean the same thing, but to have a word you need a language.

There are many numbering systems, and there have been more throughout history. The system you and I learned in school is based on people using fingers to count &mdash; that's why there are 10 digits, after all, and it's probably why "digit" can either mean "number" or "finger." We use one digit to represent each of our fingers, rolling over to $10$ on our last finger so we can keep counting from there.

But what if humans had fewer fingers? Or more? Imagine what our numbering system would be like if humans only had three fingers. We'd start by counting off, 1 ..., 2 ..., and then we're already on our last finger. So 10? Then we'd need to roll over to keep counting: 1, 2, 10, 11, 12, 20, 21, 22. Now we're stuck again, so we'll have to roll over and keep going &mdash; 1, 2, 10, 11, 12, 20, 21, 22, 100, 101, 102, 110, 111, ...

What we just invented was a different numbering system; one that's similar to ours but only has three digits. The crux to understanding all this is our three-fingered friends didn't skip any numbers when they went from 2 to 10! They're just speaking a different numeric 'language,' one that means something different by "10" than we do. (It's sort of like [false friends](https://en.wikipedia.org/wiki/False_friend), but for numbers instead of words.)

In case it helps, here's a quick chart comparing our numbering system to theirs; each row of the table gives the different ways the different systems write the same number:

| Their System | Our System |
| :----------: | :--------: |
|      0       |     0      |
|      1       |     1      |
|      2       |     2      |
|      10      |     3      |
|      11      |     4      |
|      12      |     5      |
|     100      |     6      |
|     101      |     7      |
|     102      |     8      |
|     110      |     9      |
|     111      |     10     |
|     112      |     11     |
|     120      |     12     |
|     121      |     13     |
|     122      |     14     |
|     200      |     15     |
|     201      |     16     |
|     202      |     17     |
|     210      |     18     |
|     ...      |    ...     |
|     222      |     26     |
|     1000     |     27     |
|     ...      |    ...     |

So their system is the same as ours, but they have fewer digits between 0 and 10, so they have to roll over more often. The number of digits between 0 and 10 is called the system's **basis** or sometimes **radix**. The basis (radix) of our system is 10, so we call it "base 10," whereas our friends' system has a basis (radix) or 3, so we call it "base 3." This is because our system has 10 digits (0, 1, 2, 3, 4, 5, 6, 7, 8 and 9) and their system only has three (0, 1 and 2).

> By the way, if you find the term "base 10" terribly confusing, you're completely justified. How can we call our system "base 10" if the whole problem is defining what "10" means? Wouldn't our three-fingered friends also call *their* system "base 10?"
>
> The answer is yup, they probably would. That's why, when we talk about bases, we always use *our* numbering system. So when we say our numbering system is "base 10," we always mean the 10 you learned in school.

If you get how counting in base-3 works, and how base 3 numbers relate to base-10 numbers, then congrats, you already get binary: binary is just base-2!

Let's use our imaginations again &mdash; this time, let's imagine humans that only have 2 fingers instead of 10. These humans only have the digits 0 and 1, so their version of 10 is our version of 2. Our two-fingered friends would count like this:

<center>1, 10, 11, 100, 101, 110, 111, 1000, 1001, 1010, ...</center>

Get it? Try to keep counting from here &mdash; what are the next few numbers?

The correct answer is: 1011, 1100, 1101, 1110, 1111, 10000, and so on. If that's what you got, then congratulations: you know binary!

Since we're taling about bases already, there's another numbering system you might want to know if you spend time working on computers: hexadecimal. So far we've been talking about numbering systems with fewer than 10 digits; hexadecimal is an example of a numbering system with *more* than 10 digits. There are 16 hexadecimal digits, which means "10" in hexadecimal is equal to "16" in our system.

To represent hexadecimal, we have a problem: we the real humans have only invented 10 unique digits, but we need 6 more to represent hexadecimal numbers. By convention, the way you do this is to grab letters from the English alphabet to stand in for the missing digits. So counting in hexadecimal (or "hex," as it's sometimes called) looks like this:

<center>1, 2, 3, 4, 5, 6, 7, 8, 9, A, B, C, D, E, F, 10, 11, 12  ...</center>

Can you guess the next few digits in the sequence? Try to count to, say, 32 in hexadecimal numbers.

Got it? The rest of the sequence should be: 13, 14, 15, 16, 17, 18, 19, 1A, 1B, 1C, 1D, 1E, 1F, 20. If you got that, then you're golden!

For completeness, here's a table of all the different numbering systems we talked about so far, showing how you count in each row-by-row:

| Base-2<br>(Binary) | Base-3<br>(Ternary) | Base-10<br>(Decimal) | Base-16<br>(Hexadecimal) |
| :----------------: | :-----------------: | :------------------: | :----------------------: |
|         0          |          0          |          0           |            0             |
|         1          |          1          |          1           |            1             |
|         10         |          2          |          2           |            2             |
|         11         |         10          |          3           |            3             |
|        100         |         11          |          4           |            4             |
|        101         |         12          |          5           |            5             |
|        110         |         100         |          6           |            6             |
|        111         |         101         |          7           |            7             |
|        1000        |         102         |          8           |            8             |
|        1001        |         110         |          9           |            9             |
|        1010        |         111         |          10          |            A             |
|        1011        |         112         |          11          |            B             |
|        1100        |         120         |          12          |            C             |
|        1101        |         121         |          13          |            D             |
|        1110        |         122         |          14          |            E             |
|        1111        |         200         |          15          |            F             |
|       10000        |         201         |          16          |            10            |
|       10001        |         202         |          17          |            11            |
|       10010        |         210         |          18          |            12            |
|        ...         |         ...         |         ...          |           ...            |
|       11010        |         222         |          26          |            1A            |
|       11011        |        1000         |          27          |            1B            |
|        ...         |         ...         |         ...          |           ...            |

So that's all there really is to binary and hexadecimal; if you get it, you're ready to move on and start building computers.

A reasonable question to ask at this point is, why people design computers using binary and hexadecimal. Wouldn't it be easier to use the numbering system everyone already knows?

There are good, non-arbitrary reasons to use these numbering systems. We'll talk about this in more depth later, but binary is useful because computer circuitry is based on switching, and binary works naturally with switching: you use "switched off" to represent $0$ and "switched on" to represent $1$, and then build little networks of interconnected switches to implement binary calculations by switching this electrical circuitry on or off. We'll see later in the chapter exactly how this works.

Hexadecimal is also widely used because its digits line up evenly with binary digits: every hexadecimal digit corresponds to a unique four-digit binary sequence, and every four-digit binary sequence corresponds to a hexadecimal digit. This makes it easier (both for people and code) to switch between binary (which the underlying circuitry uses) and hexadecimal, which is a little more compact and easier to read.

> That hex digits line up nicely with binary digits comes from the fact that hex is base-16, and 16 is a power of two. Octal (base-8 numbering) also has this property, but each octal digit corresopnds to a three-digit binary sequence instread of four. 8 and 16 are the powers of two closes to 10, our preferred basis, so you'll see both octal and hex used; of the two, hex is more common.

Each digit of a binary number is called a **bit** (in fact, the term "bit" is just short for "binary digit.") One bit by itself can only represent 0 or 1, which isn't very useful on its own; it's common to work with multi-bit numbers instead. A collection of 8 bits is usually called a **byte**. ("Byte" doesn't stand for anything meaningful, it's just a pun &mdash; a byte is a few bits.) An 8-bit byte can represent any number from 0 to 255, which is more useful. (A *bit* more useful &mdash; ha ha.)

That a byte is 8 bits is why hexadecimal is more popular than octal: one hex digit corresponds to 4 bits, so any byte can be written compactly as two hex digits. In contrary, an octal digit corresponds to 3 bits, and 3 doesn't divide into 8 evenly.

It's common in computers to end up needing to deal with lots of bytes. We use the [standard SI prefixes](https://www.nist.gov/pml/weights-and-measures/metric-si-prefixes) (kilo, mega, giga, tera, and so on) to represent progressively larger collections of bytes. However, instead of using increments of 1,000 like SI calls for, we use increments of 1,024 (1,024 is close to 1,000 and is also a power of 2, which is useful in several cases). Here's a quick breakdown:

| Unit          | Meaning         | Number of Bytes       | Number of Bits        |
| ------------- | --------------- | --------------------- | --------------------- |
| Kilobyte (KB) | 1,024 bytes     | 1,024                 | 8,192                 |
| Megabyte (MB) | 1,024 kilobytes | 1,048,576             | 8,388,608             |
| Gigabyte (GB) | 1,024 megabytes | 1,073,741,824         | 8,589,934,592         |
| Terabyte (TB) | 1,024 gigabytes | 1,099,511,627,776     | 8,796,093,022,208     |
| Petabyte (PB) | 1,024 terabytes | 1,125,899,906,842,624 | 9,007,199,254,740,992 |

> The choice of 1,000 vs 1,024 bytes for scaling is a source of confusion in computing. For example, hard drive manufacturers typically use increments of 1,000 since it makes their drives sound bigger; but most software uses increments of 1,024 by convention; so when you plug in a hard drive that was advertised as 100 GB (100,000,000,000 bytes), software reports it as only being about 97 GB, because $100,000,000,000 \div 1,024$ is roughly 97.
>
> There have been attempts to get people to use different prefixes to describe 1,000-byte vs 1,024-byte increments, but so far none has taken off very widely. In a majority of cases, the distinction is not too important anyways, because 1,000 and 1,024 are so close to each other.

## In Summary

* Binary is a numbering system built out of only two digits: $0$ and $1$
* A bit is a single binary digit; a byte is 8 binary digits
* Hexadecimal is base-16 numbering system useful as a notation for writing byte values compactly
* We use the SI prefixes (kilo, mega, giga, tera, ...) with increments of 1,024 to denote large collections of bytes

Got it? With all the numbers and notation stuff out of the way, we're ready to start building electrical circuitry that represents binary numbers. Onward!