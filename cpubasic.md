---
layout: chapter
title: CPU Basics
---

In this book, we're going to talk at length about the kinds of challenges CPU designers run into when they try to go multi-core, and how imperfect solutions to these problems end up becoming problems for you, the lock-free software developer. To talk cogently about what goes on inside of CPUs, it'd certainly be helpful to start off with a basic idea of how CPUs work: how you program one, and how they run programs.

There is one cardinal rule in this chapter:

> Sketch a cruddy knockoff of Douglas Adams Don't Panic

As you'll soon see, the assembly language for a CPU and the design for that CPU are intertwined; you can't talk about one without the other. So yes, we'll talk about assembly sometimes in this book. I promise, it will not be as bad as you're thinking.

<center><b>Assembly is the easiest language you'll ever learn.</b></center>

The people who told you not to bother learning assembly &mdash; or that assembly is scary &mdash; were right, in the sense that actually accomplishing anything in assembly is very difficult. There are no docs, no libraries, no frameworks, the tools are ancient, the debuggers are primitive, and even basic things like printing to the console are surprisingly difficult. You don't want to build big software programs in assembly if it can be avoided. But, all that said, the language itself is incredibly simple &mdash; even if its simplicity makes it difficult to use in practice.

In fact, in a modern world of complex software methodologies, tools, frameworks, integration problems, containerization, microservices, serverless, transpilers, repeatable builds, distribution ... there are people who yearn for the "good old days" when the only thing you need to know was an assembly language. Because even if it means doing a lot more of the work yourself, assembly is simple!

In this chapter, we're going to lay down a rough sketch of what a CPU does, what the programming language for a CPU looks like, and how you'd hook up circuitry so that the CPU can interpret that program using electrical signals. Just remember

> The don't panic thing again

## Inside a Computer

Let's see you had a classic desktop tower computer like this

> Picture of a desktop

The monitor, keyboard and mouse are all there for you, the human, to interact with code running on the computer. Let's take a closer look at the tower, which is the actual computer part

> Same picture, arrow annotation "the computer part"

If you opened that thing up, you'd see something like this inside:

> Shot of a computer internals, annotated with words



























