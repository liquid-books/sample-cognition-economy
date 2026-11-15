---
title: "Thinking Is Now a Utility"
short_title: "Thinking as a Utility"
description: "What it means that reasoning can now be rented by the minute, what an AI assistant such as Claude actually does when it answers, how knowing facts differs from reasoning with them, and where the whole arrangement breaks."
label: ch-01-thinking-is-now-a-utility
tags: ["cognition-economy", "claude", "large-language-models", "context", "ai-literacy"]
---

:::{figure} ../images/ch01-reasoning-on-the-meter.png
:label: fig-ch01-reasoning-on-the-meter
:alt: A utility meter on an office wall connected by a cable to a desk of business documents that glow where the cable reaches them
:width: 100%
:align: center

Reasoning now comes through the wall and is metered by use. Notice that the light falls only on the documents the cable reaches: the power is general, but what it works on is yours.
:::

:::{epigraph}
Any sufficiently advanced technology is indistinguishable from magic.

-- Arthur C. Clarke, *Profiles of the Future*
:::

Picture the sharpest analyst you have ever worked with. Now picture handing that person every document on your desk at once: the supplier contract nobody has reread since it was signed, last quarter's profit and loss, the expansion plan, the unanswered emails. What is the first question you would ask?

The course this book accompanies, *The Cognition Economy: An Introduction to AI Using Claude*, opens with that question, because the analyst exists. You can rent one today, by the month or by the minute. It reads Word files, spreadsheets and PDFs, connects a number in one file to a limit in another, and hands back a document you can forward to your boss. It is also capable of being confidently wrong, and the habits that protect you from that matter more than any clever phrasing.

This chapter follows the course's first lab, which puts the documents of an invented business, Copperline Coffee Co., in front of Claude. Copperline roasts coffee, runs four cafes, sells beans wholesale to offices and restaurants, and has an online shop. Every person, number and email in its files is made up, so you can try anything without risk. By the end you will understand four things: what it means that thinking has become a utility, what an assistant like Claude actually does between your question and its answer, why knowing facts and reasoning with them are different skills, and where the machinery fails. Clarke's line suggests that advanced technology looks like magic. The goal here is to make it look like something better: a tool you understand well enough to use with confidence.

(sec-ch01-rentable)=
## From Renting Muscle to Renting Reasoning

In 1800, if you needed ten tons of ore moved, you hired fifty men. A couple of decades later you could hire a steam engine and the few people needed to run it. The fifty men had not become worse at lifting. Lifting had become something you could rent.

Electricity followed the same path a century later. Early factories ran their own generators in the basement, with their own engineers to keep them going. Once the grid arrived, a factory owner stopped thinking about generators at all. You plugged into the wall, the power came, and at the end of the month a meter told you how much you had used. Nobody running a bakery today owns a power station. The bakery rents the electricity it needs, exactly when it needs it, in exactly the amount it needs.

Now map that onto the work in your own week. Reading a forty-page contract to find the one clause that matters, summarizing a meeting, drafting a careful reply, checking whether a forecast agrees with last year's numbers: all of that used to require a person with a salary, an afternoon and the right training. That kind of work is what economists loosely call cognition, the work of reading, judging and connecting. And like lifting in 1820 and power in 1900, it can now be rented. You connect to a model through a subscription or an account, send it work, and pay for what you use. The course calls this shift the **cognition economy**, and its central claim is simple: when something becomes rentable, every business built on owning it has to rethink itself.

:::{prf:definition} Cognition as a utility
:label: def-ch01-cognition-utility

The arrangement in which reasoning work, such as reading, analyzing, summarizing and drafting, is supplied on demand by an AI model and paid for by use or by subscription, the way electricity is supplied by a grid and paid for by the meter.
:::

The analogy has an honest limit. A kilowatt-hour from the grid is identical to every other kilowatt-hour, while a minute of rented reasoning varies in quality from task to task, and you have to check its output in a way you never check whether your lights came on.

[](#fig-ch01-muscle-to-reasoning) puts the two rentals side by side, and the timeline below places them in a longer sequence of things that became rentable.

:::{figure} ../images/ch01-muscle-to-reasoning.png
:label: fig-ch01-muscle-to-reasoning
:alt: Split image contrasting a steam engine moving ore with a person whose paperwork is being processed by a rented reasoning engine
:width: 80%
:align: center

The same pattern two centuries apart. Notice that in both halves the work did not disappear; what changed is who owns the engine that does it.
:::

:::{mermaid}
timeline
    title What became rentable
    Early 1800s : Steam engines rent muscle
    1880s : Electric grids rent power
    2006 : Cloud services rent computing
    2022 to 2026 : AI models rent reasoning
:::

Each line in that timeline marks a moment when something businesses once had to own outright became something they could switch on. The last line is the one this book is about.

Why should you care? Because the cost structure of knowledge work just changed under your feet. Before, a small business owner who wanted every supplier contract checked against every invoice had two options: hire someone, or hope. A procurement team that wanted to compare thirty vendor agreements for hidden price escalators had to budget weeks of a junior analyst's time, so it compared three and guessed about the rest. Today the same check costs a few minutes of rented reasoning, which means the questions you never asked because they were too expensive to answer are suddenly affordable. The competitive advantage moves away from who can afford the most analysts and toward who knows which questions to ask and which documents to supply. That is a much more level field, and it rewards exactly the kind of business knowledge you already have.

### How the meter actually runs

You can pay for Claude in two ways, and the course lets you use either. [](#tbl-ch01-two-ways-to-pay) compares them.

:::{table} Two ways to rent Claude's reasoning
:label: tbl-ch01-two-ways-to-pay

| | Subscription (Claude Pro or Max) | API key (Anthropic Console) |
|:--|:--|:--|
| How you pay | A flat monthly fee, with usage limits | By the amount of text processed |
| What it resembles | An unlimited-calls phone plan with a fair-use cap | A metered electricity bill |
| How you connect | Sign in with your Claude account | Paste a key that starts with `sk-ant-` |
| Best for | Steady personal use across the week | Variable or automated workloads |
:::

The "amount of text" on the metered side is counted in **tokens**, small chunks of text that are usually a short word or part of a longer one. You do not need to count them yourself, but knowing they exist explains why sending a huge pile of documents costs more than sending one memo.

:::{note} Your credentials, your bill
In the course's workspace, your sign-in or key lives in a private container that is deleted when your session ends. CourseLabs never sees it and is never billed for your usage. Everything you run is charged to your own account, which is exactly how a utility should work: you see your own meter.
:::

(sec-ch01-model-and-knowledge)=
## The Model Brings the Intelligence, You Bring the Knowledge

Think about the first day of a brilliant new hire. They graduated at the top of their class, have read widely, write well and can reason through almost any problem you describe. But on day one they do not know who your biggest customer is, what your supplier contract says, or why the CFO winces every time the fifth cafe comes up. Their intelligence is real. Their knowledge of *your* business is zero.

An AI model is that new hire, with two differences in degree. It has read far more than any person could, an enormous slice of the books, articles, code and web pages written in many languages. And it starts every single day as day one. Anything it learned about your company in yesterday's conversation is gone unless you put it back in front of it.

The technical name for this kind of model is a **large language model**. "Large" refers to the scale of what it learned from and the size of the system itself. "Language model" refers to what it fundamentally does: it has learned the patterns of human language so thoroughly that it can read, write and reason in it. Claude, made by Anthropic, is one such model; others power ChatGPT and Gemini. The course compresses everything that matters about this into one sentence you will see in every lab: **the model brings the intelligence, you bring the knowledge.**

:::{prf:definition} Large language model
:label: def-ch01-llm

An AI system trained on a very large body of text to predict and produce language, which as a result can read, summarize, write and reason in ordinary human language. It knows general patterns from its training but knows nothing about your organization unless you supply it.
:::

The new-hire analogy breaks in one important place: a person who reads your contract on Monday still remembers it on Friday, while the model remembers nothing between sessions unless a tool feeds the information back in.

:::{figure} ../images/ch01-first-day-analyst.png
:label: fig-ch01-first-day-analyst
:alt: A capable new hire at a desk beside tall stacks of closed company binders, with a coffee roastery visible behind
:width: 80%
:align: center

A brilliant mind on day one. The closed binders are the point: intelligence arrives ready to work, but the knowledge of this particular business has to be handed over.
:::

As [](#fig-ch01-first-day-analyst) suggests, the bottleneck is no longer brains. It is access. Here is why that matters to you. For decades, organizations treated their internal documents as storage: filed, backed up and rarely reread. The contract was signed, the board memo was read once, the meeting notes went into a folder. In the cognition economy those documents become fuel. The value of a rented analyst depends almost entirely on what you can put in front of it, which means the person who knows where the right files are, which ones are current and which question they should answer has become more valuable, not less. Your job does not shrink to pressing a button. It grows into the role of the person who supplies the knowledge that turns raw intelligence into a useful answer.

### Context is the flashlight beam

The course's second guiding sentence is an image. Imagine that brilliant analyst standing in a dark room. Your desk is in there somewhere, covered in papers, but the analyst cannot see any of it. Hand them a flashlight and point it at the contract, and now they can read the contract. Point it at the spreadsheet too, and they can compare the two. Whatever the beam does not touch might as well not exist.

In AI, the beam is called **context**: all the material the model can see while it works on your request, including your question, the conversation so far and any documents you have supplied or let it open. There is a ceiling on how much fits at once, called the **context window**, and modern models have large windows, large enough to hold many long documents at the same time.

:::{prf:definition} Context
:label: def-ch01-context

Everything an AI model can see while it produces a particular answer: your request, the earlier conversation and any files or tool results placed in front of it. The model reasons only over its context and what it absorbed in training; anything outside both is invisible to it.
:::

Where the flashlight image falls short is that a real beam lights everything it touches equally, while a model given a very long pile of material can give some parts less attention than others, so a smaller, well-chosen pile often beats an enormous one.

:::{figure} ../images/ch01-flashlight-on-desk.png
:label: fig-ch01-flashlight-on-desk
:alt: A flashlight beam in a dark room lighting a contract, an invoice and a note on a desk while other papers stay in shadow
:width: 80%
:align: center

Context is the flashlight beam. Notice the papers just outside the circle: they may hold the answer, but the model cannot reason about what the beam does not reach.
:::

The practical consequence of [](#fig-ch01-flashlight-on-desk) is enormous. Most disappointing AI answers are not failures of intelligence; they are failures of aim. Someone asks a chat assistant whether their supplier can raise prices, without supplying the contract, and receives a careful, generic, useless answer about how supply agreements usually work. Point the beam at the actual contract and the same model gives a precise answer with the clause number. Learning to aim the beam is the single most transferable skill in this book, and the next chapter, *Asking Well: From Prompts to Briefs*, is devoted to doing it deliberately.

::::{grid} 1 1 3 3

:::{card} The model brings
General reasoning, fluent writing, broad background knowledge, and the ability to read many formats quickly.
:::

:::{card} You bring
The documents, the business situation, the question worth asking, and the judgment about what a good answer looks like.
:::

:::{card} Together you check
Quotes against sources, numbers against spreadsheets, and conclusions against what you know to be true.
:::

::::

(sec-ch01-what-happens)=
## What Actually Happens When Claude Answers

Your phone keyboard suggests the next word as you type. Write "See you" and it offers "tomorrow" or "soon," because it has seen those words follow "See you" many times. That suggestion engine is tiny and has read relatively little, so its guesses are shallow.

Now imagine a suggestion engine that has absorbed an enormous library and has been trained not just to guess one word but to produce the most useful continuation of an entire conversation, one piece at a time. To predict well what comes after "Clause 3 permits a price increase of up to 18 percent, and the invoice shows 16 percent, so," the system has to track what those numbers mean, which is bigger, and what follows logically. At small scale, prediction is autocomplete. At very large scale, the same mechanism produces behavior that looks and works like reasoning. That mechanism is called **next-token prediction**: the model writes its answer one token at a time, each chosen in light of everything before it.

:::{dropdown} A closer look at tokens
A token is a fragment of text, often a whole short word, sometimes a piece of a longer one, sometimes punctuation. When you send a request, your words and documents are broken into tokens; the model reads them all, then produces its reply token by token. This is why pricing on the metered plan is quoted per token, why very long documents cost more to process, and why a model can occasionally stumble on tasks like counting the letters in a word: it sees chunks, not individual letters.
:::

The phone-keyboard comparison undersells the result in one direction and oversells it in another: the model is far more capable than autocomplete, yet it is not looking anything up in a database, so its fluent sentences can be wrong in exactly the places where it has no source to lean on.

### An assistant at a computer, not a chat window with a paperclip

The course does not use Claude in a chat window. It uses **Claude Code**, which runs in a terminal, a text window where you type requests in plain English. That choice can look odd for a business audience, so it helps to see the two side by side.

::::{tab-set}
:::{tab-item} Chat window
You paste text or attach a file, and Claude replies with text. It works only with what you hand it, in the form you hand it. If you want a Word document out, you copy the reply into Word yourself. Excellent for quick questions and drafts.
:::
:::{tab-item} Claude Code in a workspace
Claude works inside a folder of files on a computer. It can open thirty files, decide which ones matter, convert formats it cannot read directly, calculate, and save a finished Word document where you asked. It shows every step and asks before doing anything it has not been allowed to do.
:::
::::

The difference is **tool use**: the model can operate programs on the computer to get its work done. When you ask it to read a Word file, it does not pretend to see the file. It runs a small converter (a program called pandoc) that turns the Word file into plain text, then reads the text. For an Excel workbook it runs a short Python step that reads the cells. A PDF it can read directly. You never asked it to use these programs, and you did not need to know they existed. As the course puts it, Claude reads a file the way you would: with whatever program opens it. [](#fig-ch01-how-claude-reads) shows the four routes.

:::{figure} ../images/ch01-how-claude-reads.png
:label: fig-ch01-how-claude-reads
:alt: Four document types, PDF, Word, Excel and plain text, each with an arrow to a single reader, labeled with how each is read
:width: 80%
:align: center

Four formats, four routes, one reader. The point to notice is that the assistant chooses the route itself; the conversion is a tool it picks up, not a step you perform.
:::

:::{prf:definition} Tool use
:label: def-ch01-tool-use

The ability of an AI assistant to operate other programs, such as file converters, calculators or document builders, as part of answering a request, so that it can act on real files rather than only on text pasted into a conversation.
:::

The sequence below traces what happens, in order, when you ask Claude Code a question about a Word document.

:::{mermaid}
sequenceDiagram
    participant Y as You
    participant C as Claude Code
    participant T as Tools
    participant F as Files
    Y->>C: Asks a question in plain English
    C->>F: Finds the relevant documents
    C->>T: Converts the Word file to text
    T-->>C: Returns plain text
    C->>C: Reasons over the text
    C->>Y: Asks permission for anything new
    Y-->>C: Approves or declines
    C->>F: Saves the answer as a file
    C-->>Y: Shows its steps and the answer
:::

Two lines in that diagram deserve attention. The first is the permission step. In the course workspace, reading and writing files inside the course folder is already allowed, so Claude simply proceeds. For anything else it stops and offers a short menu: **Yes**, **Yes, and don't ask again** for this kind of action, or **No**, with a chance to say what to do instead. The second is the last line: every step appears in the terminal, so you can always see how it reached its answer.

:::{important} The most valuable habit in this course
Read what Claude proposes before you approve it. A permission prompt is your moment of control, and treating it as a nuisance to click through gives that control away. This habit is worth more than any clever prompt.
:::

Why does this matter beyond convenience? Because it changes what kind of help you are renting. A chat assistant is a brilliant consultant on the phone: you describe the situation, and it advises. An assistant at a computer is a colleague at the next desk: you point at the folder, and it does the work, leaving a finished file. For a business person, the second is the difference between getting advice about your contracts and getting your contracts actually checked. It turns AI from a writing aid into a working analyst, and that is where the hours start to come back.

(sec-ch01-facts-vs-reasoning)=
## Knowing Facts Versus Reasoning With Them

Think of the difference between a quiz champion and a good detective. The quiz champion holds an astonishing store of facts and can produce any of them on demand. The detective may know fewer facts but can take three clues from three different places, notice that they do not fit together, and work out what happened. Most real work in a business needs the detective more than the quiz champion.

An AI model has something of both. From training, it carries general knowledge: what a supply agreement usually contains, what a notice period is, how profit and loss statements are laid out. That knowledge is called **parametric knowledge**, because it is stored in the settings, or parameters, of the model itself. But your contract with your bean supplier was never in its training, and even if it had been, you would not want it relying on a fuzzy memory. What you want is **reasoning over context**: the model reading your actual documents in its context and connecting them, the way a detective connects clues.

The quiz-and-detective split is cleaner than reality, because inside a model, facts and reasoning are not stored in separate drawers; its memory of facts behaves more like vivid but imperfect recollection than like a lookup in a reference book.

[](#tbl-ch01-facts-reasoning) sets the two side by side.

:::{table} Recalled knowledge versus reasoning over your documents
:label: tbl-ch01-facts-reasoning

| | Recalled from training | Reasoned over your context |
|:--|:--|:--|
| Source | Patterns absorbed before the model was released | Files and text placed in front of it now |
| Example | "Supply contracts often include price escalators." | "Clause 3 of *this* contract caps escalation at 18 percent." |
| Freshness | Frozen at the knowledge cutoff | As current as the documents you supply |
| How to check it | Hard: there is no page to point to | Easy: ask for the quote and the file name |
:::

:::{figure} ../images/ch01-connecting-the-clues.png
:label: fig-ch01-connecting-the-clues
:alt: An investigation board with an email, a contract page and an invoice connected by strings to a single card in the middle
:width: 80%
:align: center

Reasoning is connection. Notice that no single pinned document holds the conclusion; it exists only where the strings meet.
:::

Here is the payoff, and it is the reason this distinction appears in the first chapter. The answers that save you an afternoon are almost never facts you could look up. They are connections across files that nobody has open at the same time: the email that mentions a charge, the contract that limits it, the clause that sets a deadline for changing the limit. Inside a real organization those files live in different folders, owned by different people. A rented reasoner that can hold all of them in one beam, as in [](#fig-ch01-connecting-the-clues), does work that previously required someone senior enough to know all three existed. And because reasoning over context can be checked against the source, it is also the kind of AI output you can actually trust once verified.

(sec-ch01-worked-example)=
## Worked Example: Is the Supplier Allowed to Do That?

This is the central exercise of the course's first lab, walked through step by step.

:::{figure} ../images/ch01-roastery-invoice.png
:label: fig-ch01-roastery-invoice
:alt: A roastery manager at a workbench frowning at a printed invoice, with sacks of green coffee beans behind him
:width: 80%
:align: center

The kind of moment the worked example begins with. Notice the instinct in the scene: the charge looks wrong, and the first impulse is to push back before anyone has reread the contract.
:::

**The situation.** Sam, who runs Copperline's roastery, has emailed the CFO. The green bean supplier added a 16 percent "market adjustment" to the September invoice, about \$9,800, and Sam wants to refuse it. The email is in the company's inbox folder; the supply agreement, a Word document, is in the contracts folder. Picture Sam in [](#fig-ch01-roastery-invoice), invoice in hand.

**Step 1: Predict before you ask.** Write down your own guess: can Copperline refuse the charge? Most people say yes, it sounds like a surprise fee. The prediction matters because it lets you notice when the answer surprises you, which is when you learn the most.

**Step 2: Write a request that can be checked.** The lab's request asks for more than an opinion:

> Sam's email in copperline/operations/inbox says our supplier added a 16 percent market adjustment. Check copperline/contracts/green-bean-supply-agreement.docx: is the supplier allowed to do that? Quote the clause, say yes or no, and say what Copperline could do next. Save your answer as answers/market-adjustment.md and name the files you used.

Notice the four demands built into it: quote the clause, give a clear yes or no, suggest a next step, and name the source files. Each one makes the answer easier to verify.

**Step 3: Watch the steps.** In the terminal you see Claude find the email, locate the contract, convert the Word file to text, and read it. Nothing is hidden.

**Step 4: Read the answer.** It is not the one most people expect. Clause 3 of the agreement lets the supplier add up to 18 percent in any quarter in which it declares exceptional market conditions, at its sole discretion. Sixteen is under eighteen, so the charge is allowed as written. The useful advice is therefore not "fight it" but "this clause is the problem": renegotiate the cap at renewal. And Claude spots something you did not ask about: clause 1 requires 120 days' notice to renegotiate, so there is a deadline to watch.

**Step 5: Verify one quote yourself.** Before trusting any of this, run the same converter Claude used, in an ordinary terminal pane, and read clause 3 withyour own eyes. The lab does this with one line typed into the lower terminal pane, which is an ordinary terminal and not Claude. It runs the same Word-to-text converter and prints only the section headed "3. Price." The clause reads exactly as Claude quoted it. That check takes thirty seconds. It is what turns an answer you have to trust into an answer you have verified.

**Step 6: Get the work back out.** An answer sitting in a terminal is not something you can forward to the CEO, so the lab's final request asks for a real document. Claude writes a one-page Word briefing for Dana, Copperline's CEO, titled "Three things to decide before the November board." It has one short paragraph on each of three topics: the supplier's market adjustment and what the contract allows, the Riverside cafe's operating loss of \$8,700 in the third quarter, and the revenue assumption in the fifth-cafe memo compared with the Main Street cafe's actual revenue. Each paragraph ends with the file it came from. Claude builds the document with a short Python step, saves it, and you download it and open it in Word like any other file.

That third topic deserves a second look, because it needed three files nobody asked for by name. Main Street's revenue is in the spreadsheet, the fifth cafe's forecast is in the CEO's memo, and the CFO's doubt about that forecast is in the leadership meeting notes. Whether Claude finds all three is a good test of whether it is reasoning or just summarizing.

:::{dropdown} Why the "obvious" answer was wrong
The instinct to fight the charge comes from parametric knowledge: in general, surprise fees on invoices are often disputable. The correct answer comes from reasoning over context: *this* contract, at clause 3, permits *this* charge. The two kinds of knowledge pointed in opposite directions, and the documents won. Whenever general wisdom and your specific documents disagree, trust the documents and check the quote.
:::

:::{figure} ../images/ch01-checking-the-clause.png
:label: fig-ch01-checking-the-clause
:alt: A magnifying glass and a pointing finger resting on one paragraph of a contract page
:width: 80%
:align: center

Ask for the quote, not just the answer, then check one. The finger on the page is the habit: a thirty-second check that converts a fluent answer into a verified one.
:::

The six steps in the worked example share a shape that repeats through the whole course. The flowchart below draws it.

:::{mermaid}
flowchart LR
    A["Documents in"] --> B["Claude reads and reasons"]
    B --> C["You check one quote"]
    C -->|Matches| D["Document out"]
    C -->|Does not match| B
:::

Documents go in, Claude reads and reasons, you verify, and a document a person can open comes out. The loop back from "Does not match" is the part beginners skip. What changes from lab to lab in the rest of the course is how much of the thinking you hand over and how carefully you aim the light, but the loop stays the same. As the course puts it: documents in, judgment applied, a document out.

Look at what the market-adjustment question took. Claude found the right email, opened a Word contract, read nine clauses, matched a number in one file to a limit in another, and noticed a deadline in a third clause. That is a junior analyst's afternoon, and it took less than a minute. Sam was about to send a confident, angry email to a supplier that was within its rights. A minute of rented reasoning turned that into a calm plan for the renewal negotiation, with a date on the calendar. Multiply that by every contract, invoice and memo in a business and you begin to see what the cognition economy rearranges.

(sec-ch01-where-it-fails)=
## Where It Fails

Think of a colleague who missed a meeting but is asked about it anyway. A careful colleague says, "I wasn't there." An eager one, wanting to help, pieces together what *probably* happened from what usually happens in such meetings, and tells you in a confident, fluent voice. Most of it may even be right. The problem is that you cannot tell which parts are memory and which are invention, because they sound the same.

A language model behaves like the eager colleague. Because it produces each answer by predicting the most plausible continuation, it will sometimes produce something plausible that is not true: a clause number that does not exist, a statistic that was never published, a court case nobody decided. This is called a **hallucination**. It is most likely when the model is asked about something outside its context, such as a document you never supplied, a fact it half-remembers from training, or a detail too specific for general knowledge to cover.

:::{prf:definition} Hallucination
:label: def-ch01-hallucination

A confident, fluent statement produced by an AI model that is not supported by its sources or by fact. It arises because the model generates plausible language rather than retrieving verified records.
:::

The colleague comparison is imperfect in one telling way: a person who bluffs usually knows they are bluffing, while the model has no reliable inner sense of when it has crossed from knowledge into invention, which is why the check has to come from you.

:::{figure} ../images/ch01-the-mist-book.png
:label: fig-ch01-the-mist-book
:alt: A library shelf of solid books with one translucent, misty book among them and a hand reaching for it
:width: 80%
:align: center

A hallucination has the same shape as a fact. Notice that only the reach for it, the attempt to use and check it, reveals that it is not there.
:::

As [](#fig-ch01-the-mist-book) suggests, you cannot spot a hallucination by its tone. You spot it by checking it. And this is the part that should make you more confident, not less. The worked example showed that the remedy costs one sentence in your request ("quote the clause and name the file") and thirty seconds of reading. A rented reasoner that is right most of the time and cheap to verify is enormously useful; one that is right most of the time and impossible to verify is dangerous. The habits in this chapter move your work from the second category into the first. People who learn this early get the speed of AI without its embarrassments; people who skip it eventually forward a confident fiction to someone important.

Hallucination is the best-known failure, but not the only one. The grid below gathers the four you will meet most often.

::::{grid} 1 1 2 2

:::{card} Missing context
The answer is generic or wrong because the right document was never in the beam. Fix it by supplying the file, or by asking Claude which files it used.
:::

:::{card} Stale knowledge
Training stops at a **knowledge cutoff**. Ask about recent prices, laws or events without supplying a source and you may get last year's world.
:::

:::{card} Mental arithmetic
Asked to add a long column "in its head," a model can slip. Asking it to calculate with a tool, as Claude Code does with spreadsheets, is far more reliable.
:::

:::{card} Overreach on judgment
Claude can tell you what a contract allows. Whether to accept the charge to protect a supplier relationship is a business decision that stays with you.
:::

::::

:::{warning} What you upload leaves your desk
Whatever Claude reads is sent to Anthropic under your own account's terms. Choose files the way you would for any outside service: do not upload client data, personal information about other people, or anything your employer has not cleared for AI tools. The Copperline files exist precisely so you can practice without that risk.
:::

:::{tip} A three-part habit for every important answer
Ask for the quote, ask for the file name, then open the file and check one quote yourself. If the quote matches, the rest of the answer earns provisional trust. If it does not, start over with a sharper request.
:::

(sec-ch01-cases)=
## Rented Reasoning at Work

The cases below are composites of how professionals were using AI assistants in 2025 and 2026. They are illustrative, not reports on particular named organizations, except where a pattern is a matter of public record.

### The restaurant owner and the delivery contracts

An owner of three neighborhood restaurants had signed agreements with two food-delivery platforms and a linen service over several years, each renewed automatically. Commission rates had crept upward, and she suspected one contract allowed changes she had never noticed. Paying a lawyer to read all three for a hunch felt extravagant, so for years she simply did not look.

In early 2026 she uploaded the three agreements and her last six monthly statements to Claude and asked which clauses permitted rate changes, what notice each required, and whether the statements matched the contracted rates. She added the sentence the worked example taught: quote every clause you rely on.

The answer was mixed in an instructive way. One platform's rate increase was permitted by a clause she had signed; one statement showed a fee that no clause appeared to support; and the linen contract renewed for a full year unless cancelled sixty days in advance, a deadline only weeks away. She checked the quoted clauses herself and then took a single, focused question to her lawyer about the unsupported fee. The rented reasoning did not replace the lawyer. It made the lawyer's hour count.

### The HR manager and the handbook nobody reads

An HR manager at a logistics firm of a few hundred people answered the same questions every week: how parental leave interacts with vacation, who approves overtime, what the policy on remote days actually says. The answers were scattered across a handbook PDF, a dozen policy emails and a slide deck from a benefits briefing.

Using a Claude Project, which keeps a set of documents attached to a shared workspace, she loaded the handbook and the policy updates and asked Claude to draft an onboarding FAQ in which every answer cited its source section. Reading the draft, she found two answers where the handbook and a later email disagreed. Claude had flagged one of them; the other it had silently resolved in favor of the older document.

That miss became the most useful finding of the exercise. She fixed the FAQ, but she also fixed the underlying policy conflict, which nobody had noticed because nobody had ever read every document side by side. The case shows both sides of this chapter: reasoning across files surfaces contradictions people miss, and the same reasoning can quietly choose wrong when sources conflict unless you ask it to show you the conflicts.

### The lawyers and the invented cases

This one is public record. Since 2023, courts in several countries have sanctioned or reprimanded lawyers who filed documents citing court decisions that did not exist, invented by general-purpose AI chat tools asked to find supporting precedent. The pattern continued into 2025 despite wide publicity.

Every one of these incidents has the same anatomy. The lawyer asked the model for facts it did not have in its context, specific case names and citations, and relied on parametric knowledge for exactly the kind of precise detail where it is weakest. The model obliged with plausible fictions. Nobody opened the cited cases before filing.

Set beside the worked example, the lesson is almost mechanical. The Copperline request supplied the source and demanded a quote that could be checked in the source. The failed legal filings supplied no source and checked nothing. The same technology produced a sound answer in one setting and a professional disaster in the other. The difference was not the model; it was the habit.

### The graduate student and the reading pile

A public-policy graduate student facing a literature review had forty PDFs of reports and papers on housing policy. Her early attempts with a chat tool, asking it to "summarize the research on rent control," produced confident overviews she could not trace to anything she had read.

She changed her approach to match this chapter's logic. She loaded her own forty sources into a tool built for reasoning over a fixed set of documents, Google's NotebookLM, and asked questions that could only be answered from them: which studies measured effects on new construction, where their findings disagreed, and which methods each used, with a citation to the page. Every claim came back linked to a passage she could open.

Her writing still had to be her own, and her argument still had to be her own; the tool could not tell her which studies were most credible. But the hours she used to spend finding where she had read something went into thinking about it instead. Aiming the beam at her own pile, rather than at the model's general memory, was the whole difference.

### The finance lead and the month-end surprise

A finance lead at a regional chain of fitness studios used Microsoft Copilot in Excel and Claude to review monthly results. Her favorite question was not "what were the numbers" but "which location changed most from last month, and what in the notes explains it." The spreadsheet held the numbers; the managers' comments sat in separate weekly reports.

One month the answer pointed to a single studio whose costs had jumped. Claude connected the jump to a manager's note about emergency repairs to a heating system, then pointed out that the repair invoice had been coded to the wrong expense category. It was exactly the Copperline pattern, a number in one file explained by text in another, and it took minutes instead of the day she used to spend chasing managers.

She kept one rule throughout: totals are recalculated in the spreadsheet itself, never accepted from the model's prose. It is the arithmetic failure from [](#sec-ch01-where-it-fails) turned into a standing policy, and it is why she trusts the rest.

:::{seealso} Going further
The course's tool is documented in Anthropic's [Claude Code overview](https://code.claude.com/docs/en/overview). The book the course follows, *The Cognition Economy* by Dr. Ernesto Lee, is free to read at [cognitioneconomy.net](https://cognitioneconomy.net/).
:::

:::{figure} ../images/ch01-briefing-on-the-desk.png
:label: fig-ch01-briefing-on-the-desk
:alt: An executive reading a one-page printed briefing with its source documents stacked beside it on the desk
:width: 80%
:align: center

The end of the loop: a document a person actually opens. Notice the stack of sources beside the briefing; a good briefing names them, so the reader can check any line.
:::

[](#fig-ch01-briefing-on-the-desk) is where every case above ends: a person with a decision to make, a page that helps them make it, and the sources within reach.

(sec-ch01-struggle)=
## Productive-Struggle Problem

You manage operations for a regional bakery with five shops. The owner has heard about rented reasoning and wants to "put AI on the paperwork," but she is nervous. On your desk sit the lease agreements for all five shops, two years of monthly sales spreadsheets, a folder of supplier emails, a staff scheduling policy, and a stack of customer complaint forms, some of which include customers' names and phone numbers.

Decide which three questions you would put to an assistant like Claude first, and why those three. For each, name the documents you would put in the beam, the part of the answer you would insist on checking yourself, and the failure from this chapter you think is most likely. Then decide what you would *not* upload, and how you would still get value from those materials without handing them over. Finally, write the two-paragraph explanation you would give the owner about what she should and should not expect. There is no single right answer; a strong response makes its trade-offs explicit.

(sec-ch01-discussion)=
## Discussion

1. The steam engine and the electric grid each made some skills less valuable and others more valuable. Which skills in your own field do you expect to rise in value now that reasoning can be rented, and which do you expect to fall? Defend one prediction you think most people would disagree with.
2. The worked example shows Claude giving advice that ran against the user's instinct. When an AI assistant contradicts your judgment, what should decide who is right? Is there a kind of question where you would side with your instinct even after seeing a quoted clause?
3. Verification takes time. At what point does checking an AI's work cost so much that renting reasoning stops being worth it? Describe a task in your work that falls on each side of that line.
4. "The model brings the intelligence, you bring the knowledge." Who in an organization owns the knowledge, and what happens to that person's influence when their documents become the fuel for rented reasoning?

:::{important} Discussion Guidelines
Write a main response that engages with at least two of the questions above. Your main response must include **at least one scholarly or credible citation**, such as a peer-reviewed article, a reputable industry report, official product documentation, or reporting from an established news outlet, linked or referenced so a reader can find it. Then respond to **at least TWO peers** with substantial feedback: extend their argument, challenge an assumption with evidence, or offer a counter-example from your own experience. Replies such as "I agree" or "great post" do not count.
:::

## 🎯 In-Class Assignment: The Desk You Would Light Up (10 pts)

**Details and instructions will be provided in class.**

**Points:** 10

## Hands-On Lab

### Group Build: Point the Beam at a Real Problem

This lab repeats the shape of the course's first lab on a problem your group chooses: documents in, judgment applied, a document out.

**Part A: Find and sharpen the problem.** Using Claude or another AI assistant as a thinking partner, identify a real problem in your own work or study context that depends on information scattered across several documents: a policy that contradicts another, a recurring question nobody can answer quickly, a decision waiting on numbers spread across files. Describe the situation to the assistant and ask it to help you narrow the problem into a single, specific, answerable statement. Push back on its suggestions until the statement names who is affected, what decision it supports and which documents hold the answer. Use only documents you are permitted to share with an AI service, or realistic substitutes you create.

**Part B: Build a solution with AI.** Put the relevant documents in front of the assistant and work toward a solution that fits your problem: a one-page decision briefing, a revised policy, a checklist, a process change or a short recommendation. Require it to quote its sources and name the files it used. Verify at least two quotes yourselves. Where its first answer falls short, ask again with better context and keep a note of what changed the result.

**Part C: Prepare to present.** Get ready to discuss with the full class what problem you identified, how the AI helped you sharpen it, what your solution looks like, and what the AI got right or missed. Be specific about at least one moment where verification caught something, or where you expected a failure that never came.

(sec-ch01-glossary)=
## Glossary

:::{glossary}
Cognition economy
: An economy in which reasoning work can be rented on demand from AI models, the way muscle was rented from steam engines and power from the electric grid.

Cognition as a utility
: The arrangement in which reading, analysis and drafting are supplied by an AI model and paid for by use or subscription.

Large language model
: An AI system trained on a very large body of text that can read, write and reason in ordinary language.

Claude
: A family of large language models made by Anthropic, used throughout this course.

Claude Code
: A version of Claude that works in a terminal on a folder of files, able to read documents, run tools and save results.

Terminal
: A text window in which you type requests or commands; in the course, the place where you talk to Claude Code.

Context
: Everything a model can see while producing an answer: your request, the conversation so far and any supplied files or tool results.

Context window
: The maximum amount of material a model can hold in its context at one time.

Token
: A small chunk of text, often a short word or part of a word, that models read and produce and that metered pricing counts.

Next-token prediction
: The mechanism by which a model writes its answer one token at a time, each chosen in light of everything before it.

Parametric knowledge
: General knowledge stored in a model's internal settings during training, as opposed to information supplied in its context.

Reasoning over context
: Drawing conclusions from the specific documents and information placed in front of the model rather than from training memory.

Knowledge cutoff
: The point after which a model's training data ends, so later events are unknown to it unless supplied.

Tool use
: An assistant's ability to operate other programs, such as file converters or calculators, while completing a request.

Hallucination
: A confident, fluent statement from a model that is not supported by its sources or by fact.

Permission prompt
: The point at which Claude Code stops and asks you to approve, approve permanently, or decline an action before taking it.

API key
: A secret code from the Anthropic Console that connects software to Claude and bills usage to your account by the amount processed.

Verification
: Checking an AI answer against its source, most simply by asking for a quote and the file name and then reading the original.
:::

(sec-ch01-takeaways)=
## Key Takeaways

Treat reasoning as something you can now switch on, the way you switch on the lights. The questions you never asked because answering them cost an analyst's afternoon are now cheap. Make a short list of them this week: the contract nobody has reread, the numbers that should agree but have never been compared, the policy that might contradict another.

Remember who brings what. The model brings intelligence; you bring knowledge. Most weak answers are failures of aim, not of intelligence, so before you blame the tool, ask whether the right documents were in the beam. Your knowledge of where the right files live and which question matters is now one of the most valuable things you have.

Make verification a reflex, not an afterthought. Ask for the quote and the file name, then check one quote yourself. Read every permission prompt before approving it. Recalculate any total that matters with a tool, not from prose. Keep sensitive files off the desk unless they are cleared. These habits cost seconds and protect you from the confident fictions that have embarrassed professionals in public.

Finally, keep the loop in mind for every task: documents in, judgment applied, a document out. The next chapter, *Asking Well: From Prompts to Briefs*, shows how to aim the beam deliberately, by briefing an assistant the way you would brief a capable new colleague.
