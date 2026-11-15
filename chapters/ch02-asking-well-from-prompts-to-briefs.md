---
title: "Asking Well: From Prompts to Briefs"
short_title: "Asking Well"
description: "Why a vague request gets a vague answer, and how to brief an AI assistant the way you would brief a capable new colleague: goal, context, constraints and what good looks like, then iterate and check. Built around the course's second lab, an inventory of which jobs at Copperline Coffee Co. have become rentable."
label: ch-02-asking-well-from-prompts-to-briefs
tags: ["prompting", "briefing", "iteration", "verification", "claude", "cognition-economy"]
---

:::{figure} ../images/ch02-napkin-to-blueprint.png
:label: fig-ch02-napkin-to-blueprint
:alt: A loose napkin sketch on one side of a table and a precise blueprint of the same idea on the other, with a pencil between them
:width: 100%
:align: center

The same idea, stated twice. Notice that nothing new is invented between the napkin and the blueprint: the plan simply says what the sketch left unsaid. That is the whole move this chapter teaches.
:::

:::{epigraph}
A problem well stated is a problem half solved.

-- Charles F. Kettering
:::

Two people at Copperline Coffee Co., the invented roaster whose files run through this course, sit down at the same assistant on the same afternoon. Both want the same thing: to know how much of the company's work an AI could now take off people's hands. The first types a single line, *what could AI do for a coffee company?*, and gets back a tidy, confident list about chatbots, demand forecasting and personalised marketing emails. It is not wrong. It is also useless, because it would have been the same list for any coffee company on earth. The second spends four minutes writing a paragraph that names the files to read, the decision the answer will feed, the rules to follow and the shape the answer should take. What comes back is a table of Copperline's own recurring jobs, each traced to the meeting note or email it came from, sorted by whether it can be handed over.

Same model, same afternoon, same intelligence. The difference was the request.

[](#ch-01-thinking-is-now-a-utility) argued that reasoning has become something you can rent by the minute, and that the model brings the intelligence while you bring the knowledge. This chapter is about the moment of rental itself: the words you hand over when you ask. It follows the course's second lab, *From Renting Muscle to Renting Cognition*, in which Claude reads Copperline's staff handbook, four leadership meetings and an inbox of twelve emails, and builds an inventory of every job people there do again and again. The lab's real lesson is hidden inside its instructions. Getting a good inventory depends far less on the cleverness of the machine than on the quality of the brief.

You will learn why vague requests produce vague answers, how to brief an assistant the way you would brief a sharp new colleague, how to improve an answer over a few rounds instead of rolling the dice again, and how to check what comes back before you put your name on it.

(sec-ch02-vague)=
## Why a Vague Request Gets a Vague Answer

Walk up to the counter at any café and say, "A coffee, please." You will get a coffee. Most likely it will be a medium cup of the house drip, black, in a paper cup, because that is what a coffee is when nobody says otherwise. The barista did not fail you. They filled every gap you left (size, roast, milk, sugar, for here or to go) with the most common choice. If you wanted an oat flat white to drink in, the problem was not the barista's skill. It was the five decisions you handed to them without noticing.

An AI assistant does the same thing, at scale and without complaint. Every request you write leaves gaps: who the answer is for, what it will be used for, how long it should be, which sources count, what to leave out. The assistant does not leave those gaps empty. It fills each one with the most typical choice, the answer that would suit the average person who might type those words. When your words are few, the average person who might type them is nearly everyone, so the answer is written for nearly everyone. That is why it reads as generic. It *is* generic, by construction.

:::{prf:definition} Prompt
:label: def-ch02-prompt

The text you send an AI assistant to ask for something. A prompt can be one word or several pages; the word says nothing about its quality.
:::

:::{prf:definition} Underspecification
:label: def-ch02-underspecification

The condition of a request that leaves decisions unmade. An assistant answers an underspecified request by filling each open decision with a typical default, so the answer fits the average asker rather than you.
:::

The barista picture fails in one honest way. A good barista can see you, notice your gym bag or your laptop, and ask "for here?"; an assistant sometimes asks clarifying questions too, but far more often it simply guesses, and its guesses arrive in fluent, finished prose that hides how much was assumed.

:::{figure} ../images/ch02-cafe-default-order.png
:label: fig-ch02-cafe-default-order
:alt: A barista reaching for the house drip coffee while a wall of unused options sits behind the counter
:width: 80%
:align: center

"A coffee, please." Look at everything behind the counter that never got chosen. Each unused option is a decision the customer handed over without noticing, which is exactly what a short prompt does.
:::

As [](#fig-ch02-cafe-default-order) suggests, the cost of a vague request is invisible at the moment you make it. You only see it in the answer, and even then it can look like the assistant's fault.

Here is why this matters more than it first appears. For most of working history, the gap between a vague request and a precise one was absorbed by people. You told an analyst "look into the Riverside numbers," and the analyst knew you, knew the board was in November, knew you hated long memos, and filled the gaps correctly because they had spent two years learning how. That silent gap-filling was part of what you paid a salary for. When reasoning becomes rentable, that layer disappears. The assistant will read thirty files in a minute, but it arrives knowing nothing about you, your company or your deadline. The skill that used to live in your colleague's head now has to live in your request. People who learn to write the request well get something close to a tireless senior analyst; people who don't get a polite search engine. The tool is the same for both, and the gap between their results is wide enough to show up in careers.

:::{figure} ../images/ch02-vague-versus-brief-output.png
:label: fig-ch02-vague-versus-brief-output
:alt: Two pages side by side, one of generic bullet points and one a sourced table with each row clipped to a document
:width: 80%
:align: center

Two answers from the same model. On the left, advice that would fit any company. On the right, a table where every row is pinned to a document the company actually wrote. The difference came entirely from the request.
:::

:::{dropdown} Deep dive: why the defaults are averages
An assistant like Claude produces its answer by repeatedly choosing words that fit what came before, drawing on patterns from an enormous amount of text. When your request is short, many very different answers fit it equally well, and the model drifts toward the ones that are most common across all that text: the typical structure, the typical examples, the typical length. Each detail you add removes a large set of possible answers and leaves fewer, more specific ones. This is why adding a single sentence such as "the reader is a CFO who has two minutes" can change an answer more than any amount of rewording. You are not persuading the model to try harder. You are narrowing the space of answers it is choosing from.
:::

(sec-ch02-brief)=
## Brief It Like a Capable New Colleague

Think about the best handover you ever gave a new team member. Perhaps a sharp hire joined on Monday and you needed them to take on a real task by Wednesday. You did not say "sort out the suppliers." You sat down for ten minutes and told them what you were trying to achieve, what they needed to know about the company and the people involved, what they must not do, and what a finished piece of work would look like when it landed on your desk. You might even have shown them last year's version. Then you let them get on with it, because they were capable, and checked their first draft carefully, because they were new.

That handover is the right model for working with an AI assistant. The assistant is the capable part: it reads faster than anyone, reasons well, writes cleanly and never resents a fourth revision. It is also permanently new: it does not know your company, your audience, your history or your taste unless you say so. A request written as a handover, rather than as a search query, gives the assistant what a good colleague would need. This kind of request is a {term}`Brief`. Anthropic's own guidance for Claude makes the same point in plain terms, suggesting you treat the model as a brilliant new employee who lacks context on your norms and needs explicit instructions.

:::{prf:definition} Brief
:label: def-ch02-brief

A request written the way you would hand work to a capable new colleague. A complete brief states the goal, supplies the context, sets the constraints and describes what a good answer looks like.
:::

The colleague analogy has one important limit. A new hire accumulates memory: by the third week, you no longer need to explain who Dana is or why the board meets in November. An assistant, by default, starts every new session with none of that, so the handover is not a one-time cost but a habit, and the later labs in this course are largely about ways to make that context persist.

:::{figure} ../images/ch02-handover-note.png
:label: fig-ch02-handover-note
:alt: A new colleague's desk with a handwritten note, keys, a tabbed folder and an example report laid out
:width: 80%
:align: center

A good handover anticipates what a capable newcomer cannot yet know. The note gives purpose, the folder gives context, and the example on top shows what finished work looks like.
:::

Why does this reframing matter so much? Because it changes what you think you are doing. If you believe you are typing a query, you optimise for short and clever, and you blame the tool when the result is bland. If you believe you are briefing a colleague, you optimise for complete and clear, and you take ownership of the result. The second mindset is what turns an assistant from a novelty into a teammate. Consider the before and after at Copperline: before, an operations lead who wanted a clear picture of where staff time goes would have needed to commission a consultant or give up a week of her own evenings. After, the same picture can be drafted in minutes, from the company's own documents, by anyone who can write a good paragraph. The scarce skill is no longer the reading or the counting. It is knowing what to ask for, and saying it.

### The four parts of a brief

A brief has four parts, shown in [](#fig-ch02-four-parts-of-a-brief). None of them is technical. Each answers a question a sensible new colleague would ask you before starting.

::::{grid} 1 1 2 2

:::{card} Goal
What is this for?
^^^
The decision or outcome the answer will serve, and who will read it. "Help me decide which jobs to automate first" is a goal; "list some jobs" is not.
:::

:::{card} Context
What do I need to know?
^^^
The documents to read, the company and people involved, the history. This is the flashlight beam from Chapter 1, aimed on purpose.
:::

:::{card} Constraints
What are the rules?
^^^
Limits on sources, length, tone and actions. "Use only these files," "do not change anything," "mark any number you estimated."
:::

:::{card} What good looks like
How will I know it's done?
^^^
The shape of a finished answer: a table with named columns, a one-page memo, five bullets. An example is often the fastest way to say it.
:::

::::

:::{figure} ../images/ch02-four-parts-of-a-brief.png
:label: fig-ch02-four-parts-of-a-brief
:alt: A sheet divided into four bands labelled Goal, Context, Constraints and What good looks like, with an arrow to a finished report
:width: 80%
:align: center

The anatomy of a brief. Read it top to bottom: purpose first, then the material, then the rules, then the finish line. Skip a band and the assistant fills it with a default.
:::

[](#tbl-ch02-brief-parts) turns those four parts into questions you can ask yourself before you press Enter, with an example of each drawn from the Copperline lab.

:::{list-table} The four parts of a brief, as questions to ask yourself
:label: tbl-ch02-brief-parts
:header-rows: 1

* - Part
  - Question to ask yourself
  - Copperline example
* - Goal
  - What decision will this answer feed, and who reads it?
  - "Show the leadership team which recurring jobs could be handed to an assistant, so they can pick where to start."
* - Context
  - Which documents and facts does a newcomer need?
  - "Read the staff handbook excerpt, the four leadership meeting notes and the twelve emails in the inbox. Copperline has about sixty staff, four cafes, a wholesale arm and an online shop."
* - Constraints
  - What must it not do, assume or invent?
  - "Only list jobs the files show evidence of. Name the source file for each. Mark any hours figure that is your estimate."
* - What good looks like
  - What shape is a finished answer?
  - "A table with columns for job, who does it, how often, estimated hours per week, rentable or not, and why, saved as a file I can open."
:::

:::{important} The part people skip
Of the four parts, *what good looks like* is the one most often left out, and it is often the one that matters most. Without it, the assistant decides the format, the length and the level of detail for you. Naming the columns of a table, or saying "one page, plain English, for a CEO," costs a sentence and saves several rounds of revision.
:::

:::{tip} The newcomer test
Before you send a brief, read it as if you were a smart person who joined the company this morning. Could you start work without walking back to ask a question? If you would need to ask "for whom?", "from which files?" or "how long?", add the answer now.
:::

(sec-ch02-worked)=
## Worked Example: Which Parts of Copperline's Week Just Became Rentable?

The course's second lab asks a practical question borrowed from economic history. When the steam engine arrived, lifting did not get harder; it became something you could rent. Reading a contract, summarising a meeting and drafting a reply are now rentable in the same way. So which jobs at Copperline does that touch, and how many hours of the week? The lab answers it by having Claude read the company's own description of its work, a description it never meant to write: a staff handbook excerpt in PDF, notes from four leadership meetings held in September and October, and twelve emails in the operations inbox. Follow the steps below and you will see each part of a brief earn its place.

### Step 1: Try the vague version, and notice what happens

Start the way most people would, with Claude Code open in the workspace folder:

> *What work at Copperline could AI do?*

The reply will be reasonable and broad. It may mention customer service chat, inventory forecasting, social media posts and scheduling. Some of it will even be true of Copperline. But look at what is missing: no file is named, no person at the company is mentioned, nothing is counted, and nothing would change if you swapped "Copperline" for any other roaster. The assistant answered the average version of your question. Every gap in [](#tbl-ch02-brief-parts) was filled with a default.

### Step 2: Write down your prediction first

Before writing the real brief, the lab asks you to commit to a guess: which kinds of job do you expect to be rentable, and which do you expect to stay firmly with people? Write two or three lines in a file of your own. This takes a minute and it matters later. Without a prediction, every answer seems obvious in hindsight, and you lose the chance to learn where your instincts about AI are right and where they are not. A prediction also gives you something to check the answer against, which you will need in Step 5.

:::{figure} ../images/ch02-prediction-before-asking.png
:label: fig-ch02-prediction-before-asking
:alt: A person at a laptop above a coffee roastery pausing to write a prediction on a notepad before sending a request
:width: 80%
:align: center

The pen comes before the Enter key. Writing your prediction first is what lets you learn something from the answer instead of simply agreeing with it.
:::

### Step 3: Write the brief

Now rewrite the request with all four parts. The tabs below show the vague version and the brief side by side so you can see exactly what was added.

::::{tab-set}
:::{tab-item} The vague request
*What work at Copperline could AI do?*

Seven words. No goal beyond curiosity, no files, no rules, no shape. Everything else is left to the assistant's defaults.
:::
:::{tab-item} The brief
**Goal.** I want to show Copperline's leadership which recurring jobs could be handed to an AI assistant, so they can decide where to start.

**Context.** Read `copperline/operations/staff-handbook-excerpt.pdf`, the four files in `copperline/operations/meeting-notes`, and the twelve emails in `copperline/operations/inbox`. Copperline has about sixty staff, four cafes, a wholesale arm and an online shop.

**Constraints.** Only list jobs these files show evidence of; do not invent typical coffee-shop tasks. For every job, name the file it came from. Where you estimate hours, say so. Do not change any of the files.

**What good looks like.** A table with columns: job, who does it, how often, estimated hours per week, and one of "rentable now", "rentable with a person checking" or "stays human", with a one-line reason. Below it, a total of hours in each group. Save it as `answers/work-inventory.md`.
:::
::::

Notice that nothing in the brief is technical. It reads like a note to a new analyst. The lab's checkpoint looks for an inventory file in the workspace, which is one practical reason to say where to save it, but the deeper reason is that a saved file is something you can open, check and forward.

:::{dropdown} Why three categories instead of two
A simple yes-or-no split invites the assistant to overclaim. Many of Copperline's jobs are partly rentable: an assistant could draft the reply to an unhappy wholesale customer, but a person should read it before it goes out. Giving the middle category its own name, "rentable with a person checking," tells the assistant that this answer exists and is often the honest one. Categories are part of *what good looks like*: you are defining the boxes the answer must fit into.
:::

### Step 4: Read the first draft, then iterate

Claude will read the PDF directly, open each meeting note and email, and build the table. Read it the way you would read a new colleague's first draft: interested, generous and alert. Typical things to notice are that two different jobs have been merged ("handling email" may cover both wholesale orders and customer complaints, which deserve different treatment), that an hours figure looks suspiciously round, or that a job you know matters is missing because the files never mention it.

Each of these becomes a short follow-up, not a fresh start. The exchange runs like this:

:::{mermaid}
sequenceDiagram
    participant Y as You
    participant C as Claude
    participant F as Copperline files
    Y->>C: Brief with goal, context, rules, shape
    C->>F: Reads handbook, notes, inbox
    F-->>C: Text of each document
    C-->>Y: First inventory table
    Y->>C: Split "handling email" into types
    C-->>Y: Revised table with sources
    Y->>C: Which hours are estimates?
    C-->>Y: Estimates marked, reasons given
:::

The diagram shows the rhythm that matters: one full brief at the start, then small, specific corrections, each naming exactly what to change. You never retype the whole request, and you never say only "make it better."

Once the table settles, it helps to see the result as positions rather than rows. The chart below is an illustrative way to read an inventory like Copperline's, placing a few kinds of job by how much judgement they need and how routinely they recur. The positions are judgements for discussion, not measurements.

:::{mermaid}
quadrantChart
    title Reading a work inventory
    x-axis Little judgement --> Heavy judgement
    y-axis Occasional --> Weekly routine
    quadrant-1 Rent with a person checking
    quadrant-2 Rent now
    quadrant-3 Rent when it comes up
    quadrant-4 Keep human
    Summarise meeting notes: [0.2, 0.85]
    Draft wholesale order replies: [0.35, 0.75]
    Answer a customer complaint: [0.7, 0.7]
    Update the staff handbook: [0.4, 0.2]
    Renegotiate supplier contract: [0.9, 0.2]
    Hire a cafe manager: [0.85, 0.35]
:::

The upper left is where the hours are: frequent, low-judgement work such as turning meeting notes into action lists. The lower right is where they are not, but where the stakes are: the renegotiation of the supplier contract you met in [](#ch-01-thinking-is-now-a-utility) is rare, high-judgement work an assistant can prepare for but should not conduct.

### Step 5: Check the answer

Three checks, each taking a minute or two, separate an inventory you can present from one you merely hope is right. First, pick two rows at random and open the file each one cites; confirm that the job really appears there. Second, add up one category's hours yourself, or ask Claude to show the sum line by line, and confirm the total matches. Third, set the result beside the prediction you wrote in Step 2. Where you disagree with Claude, decide who is right and why. That last comparison is where the learning happens: most people find their instincts were right about the obvious cases and wrong about at least one job they assumed was safely human.

:::{note} What the worked example proves
The improvement between Step 1 and Step 5 did not come from a better model, a secret phrase or technical skill. It came from four paragraphs of plain English, two short follow-ups and five minutes of checking. That is the whole craft, and it transfers to any assistant you will use.
:::

(sec-ch02-iterate)=
## Iterate Like an Editor, Not a Slot Machine

If you have ever had a suit or a dress altered, you know the fitting. You put it on, the tailor pins the hem, notices the shoulders pull, adjusts the waist, and asks you to turn around. Nobody throws the garment away after the first fitting because the sleeves were long. Each round fixes one or two specific things, and the garment gets closer to you with every pass.

Working with an assistant should feel the same. The first answer is a fitting, not a verdict. You look at it, name exactly what is off ("the second paragraph assumes the reader knows the Riverside loss; explain it in one sentence"), and the next version is closer. This is {term}`Iteration`: improving an answer through a short series of specific corrections, each one building on the last. The alternative, which many beginners fall into, is to treat the assistant like a slot machine: pull the lever, dislike the result, pull it again with the same words and hope for luck. Regenerating without changing anything mostly produces a different average, not a better answer.

:::{prf:definition} Iteration
:label: def-ch02-iteration

Improving an assistant's answer over several rounds by giving specific, targeted corrections, rather than starting over or repeating the same request.
:::

The tailor analogy breaks down in one place: a tailor remembers every pin, but in a very long conversation an assistant can lose track of early instructions as later ones pile up, so after many rounds it is often better to fold everything you have learned into a fresh, improved brief.

The loop below shows the decision you make after each round.

:::{mermaid}
flowchart LR
    A["Read the draft"] --> B{"Good enough to check?"}
    B -->|Yes| C["Verify, then use it"]
    B -->|No| D["Name one specific fix"]
    D --> E["Assistant revises"]
    E --> A
    B -->|"Many rounds, drifting"| F["Write a fresh brief"]
    F --> A
:::

Read the loop from left to right. Every pass either ends in verification or produces one named fix, and the escape hatch at the bottom is there for long conversations that have wandered. The point is that each round adds information. "Make it better" adds none. "Shorter" adds a little. "Cut it to one page by dropping the history section, and lead with the recommendation" adds a great deal.

:::{figure} ../images/ch02-tailor-fitting-pins.png
:label: fig-ch02-tailor-fitting-pins
:alt: A jacket on a dress form marked with pins from several fittings, with untouched bolts of fabric behind it
:width: 80%
:align: center

Each pin is one specific correction. The untouched fabric behind is the slot-machine approach: starting again from nothing in the hope that luck does the tailoring.
:::

Why does iteration deserve its own section? Because it changes the economics of asking. Before assistants, revising a colleague's draft cost goodwill and a day; you asked for a second version only when the first was really wrong, and you lived with a lot of "fine." Now a revision costs one sentence and thirty seconds, and the assistant never sighs. That means the bar for "finished" can rise. A board memo can go through six fittings before lunch. A customer apology can be tried in three tones and you can pick the one that sounds like your company. People who absorb this stop accepting first drafts, and their work gets visibly sharper, not because they write better than before, but because they now edit more than before. [](#fig-ch02-tailor-fitting-pins) is the picture to keep: every round adds one pin.

:::{tip} Corrections that work
The most effective follow-ups name a location, a change and, where it helps, a reason. "In row four, split wholesale order emails from complaint emails, because complaints need a person to read them" gives the assistant everything it needs in one line.
:::

(sec-ch02-check)=
## Check Before You Sign

When a cashier hands you change for a large note, you glance at it. You do not recount the till or audit the shop; you check one thing quickly, because you are about to walk away and a mistake will be yours to absorb. Most of the time the change is right. The glance costs two seconds and protects you on the occasion it is not.

Checking an assistant's answer works the same way. You do not redo the work; if you had to, renting it would be pointless. You run a few cheap, targeted checks on the parts that would hurt most if wrong: one quoted clause, one total, one claim that surprised you. This is {term}`Verification`, the habit of confirming an answer against its sources before you rely on it. It matters because assistants can produce a {term}`Hallucination`, a statement that sounds confident and fluent but is not supported by anything, such as a quotation that was never written or a number that was never in the file. [](#ch-01-thinking-is-now-a-utility) showed one form of this habit: asking for the quote, not just the answer, and then checking one.

:::{prf:definition} Verification
:label: def-ch02-verification

Confirming the parts of an assistant's answer that matter most against their original sources, using quick, targeted checks, before you act on the answer or share it.
:::

The cashier analogy breaks down in one respect: a short-changed customer notices a wrong coin at once, but an assistant's error can sit inside a perfectly formatted, perfectly reasonable paragraph, so you have to decide in advance where to look rather than waiting for something to look wrong.

That is why the best verification starts in the brief. If your constraints say "name the source file for every row" and "mark any figure you estimated," you have built the checking points into the answer before it exists. [](#tbl-ch02-checks) lists the checks that cover most everyday work.

:::{table} Quick checks and what each one catches
:label: tbl-ch02-checks

| Check | How long it takes | What it catches |
|:------|:------------------|:----------------|
| Open one cited source | One to two minutes | Invented or misread quotations |
| Recompute one total | One minute | Arithmetic and copying slips |
| Ask "what did you assume?" | Thirty seconds | Silent defaults that do not fit you |
| Compare with your prediction | Two minutes | Answers that are plausible but wrong for your situation |
| Ask what is missing | Thirty seconds | Gaps in the documents themselves |
:::

:::{figure} ../images/ch02-magnifier-one-clause.png
:label: fig-ch02-magnifier-one-clause
:alt: A magnifying glass held over one paragraph of a printed contract, with a tick in the margin
:width: 80%
:align: center

Verification is not rereading the whole document. It is choosing the one passage that would hurt most if wrong and looking at it closely.
:::

Here is why this habit is the one that protects your reputation. An assistant lets one person produce, in an hour, what used to take a team a week. That multiplies output, and it multiplies the reach of any error too. A wrong figure in a memo you drafted by hand affected one memo; a wrong figure in a template you generated and sent to forty clients affects forty relationships. The people who thrive with these tools are not the ones who trust them most or least. They are the ones who know exactly which three things to check, and check them every time, the way [](#fig-ch02-magnifier-one-clause) shows. Five minutes of checking is what turns rented reasoning into work you can sign.

:::{warning} Fluent is not the same as true
An answer's polish tells you nothing about its accuracy. Assistants write wrong answers in the same calm, well-organised prose as right ones. Treat confident tone as neutral information, and let the sources decide.
:::

:::{seealso} The verify step in the lab
In the course labs, a second terminal pane runs ordinary commands that are not Claude. Using it to open the original file and compare a quoted line is the workspace version of the cashier's glance, and it is worth doing on every lab, not only the ones that ask for it.
:::

(sec-ch02-cases)=
## Briefing in Practice: Four Cases

The four cases below are illustrative composites drawn from common workplace situations in 2025 and 2026, not reports about specific organisations. Each shows a different part of the brief doing the heavy lifting.

### The clinic manager and the patient letter

A practice manager at a small physiotherapy clinic needed to tell patients that appointment reminders would now arrive by text message instead of phone call. Her first request to an assistant was "write a letter about our new reminder system." The result was cheerful, long and full of phrases like "exciting new technology," which was wrong for a patient group that skewed older and included several people who had complained about too many messages.

Her second attempt was a brief. The goal: reassure patients and reduce calls to the front desk. The context: most patients were over sixty, some had poor eyesight, and the old phone reminders would stop on a named date. The constraints: under two hundred words, no jargon, no claims about privacy that the clinic's policy did not support, and a clear way to opt back into phone calls. What good looks like: short paragraphs, the date in bold, the opt-out phone number repeated at the end.

The letter that came back was nearly usable as written. She ran one check: she asked the assistant what it had assumed, and it listed an assumption that texts would come from a dedicated number. That was not yet decided, so she removed the sentence. Context did the main work here. Without knowing who the readers were, no amount of rewording would have produced the right tone.

### The founder and the product listings

The owner of a two-person online shop selling handmade ceramics wanted descriptions for thirty new pieces. Asking one at a time, "describe this blue mug," produced thirty descriptions that each sounded fine and together sounded like thirty different shops.

He changed approach and put the effort into *what good looks like*. He pasted three of his own best older descriptions as a model, named the voice ("warm, specific, a little dry, never 'perfect for any occasion'"), set a length, and listed the facts each listing must include: dimensions, glaze, whether it was dishwasher safe. He then gave the assistant a simple spreadsheet of the thirty pieces as context.

The examples did more than any adjective could. The new descriptions read as if one person had written all of them, because the assistant was matching a pattern instead of inventing one. His verification was mechanical and quick: he checked every dishwasher claim against the spreadsheet, because a wrong one would mean a broken mug and a refund. Two had been guessed where his sheet was blank. He fixed them and added a constraint to his saved brief: "If a fact is missing from the sheet, write MISSING, do not guess."

:::{figure} ../images/ch02-ceramics-check.png
:label: fig-ch02-ceramics-check
:alt: A ceramicist holding a mug while comparing it with a laptop screen and a printed sheet with one row circled
:width: 80%
:align: center

Verification aimed where an error costs money. A wrong dishwasher claim means a broken mug and a refund, so that is the fact checked on every listing.
:::

### The graduate student and the literature summary

A master's student in public policy was preparing a short review of research on four-day working weeks. Her first prompt, "summarise the research on four-day weeks," returned a smooth overview citing several studies. Two of the citations looked exactly right and did not exist when she searched for them. This is the textbook hallucination, and it is especially likely when you ask an assistant to recall sources from memory rather than read sources you supply.

Her fix was a constraint and a change of context. She downloaded the papers her supervisor had recommended, uploaded them, and wrote: "Use only these six papers. For every claim, give the paper and the page. If the papers disagree, say so. If a question cannot be answered from them, say that instead of filling the gap." What good looks like: a two-column table of claim and source, followed by three paragraphs on where the evidence was weak.

The output was narrower and far more useful. She then checked three page references at random, found them accurate, and only then began writing in her own words. The lesson she took away was simple: an assistant reading your documents is a different, safer tool than an assistant remembering the world.

### The operations lead and the weekly report

At a regional logistics firm, an operations lead used an assistant every Monday to turn the previous week's incident log into a report for senior managers. For months the reports were acceptable but each week's arrived in a slightly different shape, and managers complained they could not compare weeks.

The problem was that she wrote a new request every Monday from memory. She sat down once, wrote a careful brief with all four parts, including a fixed table layout and a rule to flag any incident type that had doubled since the previous week, and saved it as a text file. Each Monday she pasted the brief and the new log. The reports became consistent overnight.

Iteration still had a role, but a different one. When a manager asked for delays to be split by region, she did not fix that week's report alone; she added the split to the saved brief, so every future report carried the improvement. A brief, in other words, is not only a request. It is a small asset that gets better each time you use it, which is exactly the idea later labs in this course develop into skills and reusable instructions.

:::{note} What the four cases share
In each case, the first request was short, the result was plausible, and the plausible result was wrong for the situation. In each case the fix was a missing part of the brief, followed by one check aimed at the costliest possible error.
:::

:::{figure} ../images/ch02-narrowing-the-answers.png
:label: fig-ch02-narrowing-the-answers
:alt: Many paper boats on a pool, narrowed by four barriers until one boat reaches a dock
:width: 80%
:align: center

Each part of a brief is a barrier that removes answers that would not fit you. Goal, context, constraints and a picture of the finish line leave very few boats, and the one that arrives is yours.
:::

(sec-ch02-struggle)=
## Productive-Struggle Problem

Copperline's CEO, Dana, has read the work inventory from the worked example and wants more. She asks you to use an assistant to propose which *one* recurring job the company should hand over first, and to give her a page she can take to the November board. She adds three conditions: the board is sceptical of AI, the CFO has already questioned some of the company's numbers, and staff in the cafes are worried about their hours.

Write the brief you would give the assistant. Decide what the goal really is: recommending a job, persuading a sceptical board, reassuring staff, or some balance of the three. Decide which documents belong in the context and which would only add noise. Decide which constraints protect Dana from embarrassment in front of the CFO. Describe what a good page looks like, including how it should treat the cafe staff. Then imagine the first draft disappoints you in some specific way, and write the two follow-up corrections you would send. Finally, name the three things you would verify before the page reaches Dana, and explain why those three and not others. There is no single correct brief; a strong answer is one where every sentence earns its place and you can explain what would go wrong without it, as illustrated in [](#fig-ch02-narrowing-the-answers).

(sec-ch02-discussion)=
## Discussion

1. This chapter claims that the skill of filling gaps, once held by experienced colleagues, now has to live in your request. If that is true, what happens to the way junior professionals learn their craft when they no longer need a senior person to interpret vague instructions for them?
2. A brief makes your assumptions visible. Describe a request from your own work or study where writing the four parts down would expose a disagreement about the goal that nobody had noticed. Is that exposure a benefit or a cost?
3. Verification costs time, and the whole point of renting reasoning is to save time. Where would you draw the line between checking enough and checking so much that the assistant is no longer worth using? Does the line move depending on who will read the result?
4. In the Copperline inventory, the middle category was "rentable with a person checking." Is that a stable category, or a waiting room on the way to "rentable now"? Defend your view with an example.

:::{important} Discussion Guidelines
Write a main response that addresses at least one of the questions above in depth, and include at least one scholarly or credible citation (for example, a peer-reviewed article, a reputable industry report, or official documentation from an AI provider) to support a claim you make. Then respond to at least TWO peers with substantial feedback: extend their argument, challenge an assumption with reasons, or connect their example to your own experience. Replies such as "I agree" or "great post" do not count toward the requirement.
:::

(sec-ch02-inclass)=
## 🎯 In-Class Assignment: Brief Before You Ask (10 pts)

**Details and instructions will be provided in class.**

**Points:** 10

## Hands-On Lab

### Group Build: From a Fuzzy Problem to a Briefed Solution

This lab practises the whole chapter on a problem your group actually has. You will use an AI assistant twice: first as a thinking partner to find and sharpen the problem, then as a collaborator to build a solution.

**Part A: Find and sharpen a real problem.** As a group, start an AI assistant conversation by describing, in a few loose sentences, a recurring frustration from your work or study: a report nobody reads, a handover that always goes wrong, a process that eats Friday afternoons. Ask the assistant to interview you about it, one question at a time, until you can state the problem in two sentences: who is affected, what goes wrong, and how you would know it had been fixed. Notice how its questions push you toward goal, context, constraints and what good looks like. Keep the final problem statement and note which question from the assistant changed your understanding most.

**Part B: Brief the assistant and build a solution.** Write a full four-part brief asking the assistant to develop a solution. Choose the form that fits your problem: a short policy, a redesigned process, a checklist, a template, a one-page strategy. Supply any context documents you are allowed to share. Run at least three rounds of iteration with specific corrections, and keep a short record of each correction and what it changed. Then verify: pick the claims or steps that would cause the most harm if wrong, and check them against a source, a colleague's knowledge or your own experience.

**Part C: Prepare to present.** Prepare to discuss with the full class what problem you identified, how the assistant helped you sharpen it, what your solution looks like, and what the assistant got right and what it missed or got wrong. Be ready to show your final brief and to point to the one correction that made the biggest difference.

(sec-ch02-glossary)=
## Glossary

:::{glossary}
Brief
: A request written the way you would hand work to a capable new colleague, stating the goal, context, constraints and what a good answer looks like.

Prompt
: Any text sent to an AI assistant to ask for something, regardless of length or quality.

Underspecification
: The state of a request that leaves decisions unmade, so the assistant fills them with typical defaults.

Default
: The most common choice an assistant falls back on when a request does not say otherwise.

Goal
: The part of a brief that names the decision or outcome the answer will serve and who will read it.

Context
: The documents, facts and background an assistant needs to reason about your particular situation.

Constraint
: A rule in a brief that limits sources, length, tone, actions or assumptions.

What good looks like
: The part of a brief that describes the shape of a finished answer, often with an example or named format.

Example
: A sample of the output you want, included in a brief so the assistant can match its pattern.

Iteration
: Improving an answer over several rounds through specific, targeted corrections.

Regenerating
: Asking for a new answer to the same request without changing it, which usually produces a different average rather than a better answer.

Verification
: Confirming the parts of an answer that matter most against their sources before relying on them.

Hallucination
: A fluent, confident statement from an assistant that is not supported by any source, such as an invented quotation or citation.

Spot check
: A quick verification of one randomly or deliberately chosen item, such as a single cited clause or total.

Work inventory
: A structured list of the recurring jobs in an organisation, with who does them, how often and how long they take.

Rentable work
: Work that can now be handed to an AI assistant and paid for by use, instead of requiring a dedicated person's time.

Claude Code
: The tool used in the course labs, in which Claude works in a terminal beside your files, reading, converting and writing documents on request.

Saved brief
: A brief kept as a reusable file and improved over time, so recurring work comes back consistent.
:::

(sec-ch02-takeaways)=
## Key Takeaways

Stop treating your request as a search query and start treating it as a handover. Before you press Enter, check that it says what the answer is for, what the assistant needs to know, what rules apply and what a finished answer looks like. If you would need to ask a question before starting the work yourself, the brief is not done. The four minutes this takes are the cheapest improvement available to you in any AI tool.

Treat the first answer as a fitting. Read it, name one specific thing to change, and let the assistant revise. Do not regenerate the same words and hope. When a conversation has drifted over many rounds, fold what you learned into a fresh brief, and if the task recurs, save that brief so the next answer starts where the last one finished.

Finally, decide in advance where you will look, and look every time. Ask for sources and estimates to be marked, open one cited file, recompute one number, and compare the answer with the prediction you wrote down first. Rented reasoning becomes your work the moment you share it, and a few minutes of checking is what makes it work you can stand behind.
