# Chapter 2 Quiz: Asking Well: From Prompts to Briefs
*Instructor resource, not published in the book.*

## Multiple Choice (10 questions)

**1.** A colleague types "What could AI do for a coffee company?" and gets a confident list about chatbots and demand forecasting that would fit any roaster. According to the chapter, what best explains this result?

A. Short prompts cause the assistant to switch to a simpler, less capable model.
B. The assistant fills every decision the request leaves open with the most typical default, so the answer fits the average asker.
C. The assistant cannot reason about a specific company unless it has been trained on that company's data.
D. The assistant spends less effort on short requests because it assumes the user is not serious.

**2.** An analyst writes a brief that states a clear goal, names the files to read and sets rules about sources. She leaves out any description of the finished answer. Based on the chapter, what is the most likely consequence?

A. The assistant will refuse to proceed until she specifies a format.
B. The answer will be inaccurate, because format instructions are what prevent hallucination.
C. The assistant will choose the format, length and level of detail itself, which will probably cost her several rounds of revision.
D. Nothing important will be lost, because the goal already implies the format.

**3.** Which of the following lines from a Copperline brief is a *constraint* rather than goal, context or what good looks like?

A. "Mark any hours figure that is your estimate."
B. "Read the twelve emails in the operations inbox."
C. "A table with columns for job, who does it, how often and estimated hours per week."
D. "So the leadership team can pick where to start."

**4.** In the worked example, Claude's first inventory lists a single job called "handling email" that covers both wholesale orders and customer complaints. What response does the chapter recommend?

A. Regenerate the answer with the same brief and hope the next version separates them.
B. Discard the conversation and start again with a shorter, simpler request.
C. Accept the row as it is, since the files group all email together.
D. Send a short follow-up asking for the row to be split into wholesale orders and complaints, with a reason such as complaints needing a person to read them.

**5.** Why does the Copperline brief use three categories ("rentable now," "rentable with a person checking," "stays human") instead of a simple yes-or-no split?

A. Three categories make the final table shorter and easier to total.
B. A yes-or-no split invites the assistant to overclaim, and naming the middle category tells it that a partial, supervised answer exists and is often the honest one.
C. The lab's checkpoint will only accept an inventory with exactly three categories.
D. Two categories would force the assistant to estimate hours, which it cannot do accurately.

**6.** Before writing the real brief, the lab asks you to write down which jobs you expect to be rentable. What is the main purpose of this step?

A. It gives you something to check the answer against, so you can learn where your instincts were right or wrong instead of finding every answer obvious in hindsight.
B. It provides the assistant with extra context that improves its first draft.
C. It is required so the assistant knows which categories to use.
D. It replaces the need for verification later in the process.

**7.** The graduate student's first summary of research on four-day weeks included two citations that did not exist. Which change does the chapter credit with making her output safer and more useful?

A. Asking the assistant to double-check its citations before answering.
B. Rewording the request to sound more academic and formal.
C. Supplying six specific papers, restricting the assistant to them and requiring a paper and page for every claim.
D. Regenerating the answer until the citations matched real papers.

**8.** You have been revising a report with an assistant over many rounds, and it has started ignoring an instruction you gave near the beginning. According to the chapter, what should you do?

A. Repeat the instruction in capital letters in your next message.
B. Accept the drift, since long conversations cannot be corrected.
C. Switch to a slot-machine approach and regenerate until it complies.
D. Fold everything you have learned into a fresh, improved brief and start from that.

**9.** At the logistics firm, weekly reports arrived in a slightly different shape every Monday. What fixed the problem, and what does the case show about briefs?

A. The manager asked for shorter reports. Briefs work best when they are brief.
B. The operations lead wrote one careful four-part brief, saved it and reused it each week, adding improvements to it. A brief can be a reusable asset that gets better over time.
C. The operations lead switched assistants. Consistency depends mainly on the tool chosen.
D. Senior managers began editing each report themselves. Verification matters more than briefing.

**10.** The chapter says "the best verification starts in the brief." What does this mean in practice?

A. You should ask the assistant to verify its own answer before you read it.
B. A long enough brief removes the need to check the answer afterwards.
C. Constraints such as "name the source file for every row" and "mark any figure you estimated" build checking points into the answer before it exists.
D. You should verify every sentence of the brief against company records before sending it.

## Short Answer (3 questions)

**1.** The chapter argues that a skill which once "lived in your colleague's head" must now live in your request. Explain what that skill is, why an experienced human analyst could supply it, and why an AI assistant cannot.

**2.** The ceramics shop owner improved his thirty product descriptions by focusing on one part of the brief. Identify that part, explain why it worked better than adjectives alone, and describe the verification he ran and what he changed in his saved brief as a result.

**3.** Distinguish iteration from regenerating. Then write one example of an effective follow-up correction for a draft report and explain which features make it effective, according to the chapter.

## Answer Key

**Multiple Choice**

1. **B.** The chapter explains that an assistant fills each gap in a request with the most typical choice, so a few words produce an answer written for nearly everyone, which makes it generic by construction.
2. **C.** "What good looks like" is the part most often skipped, and without it the assistant decides format, length and detail, which costs extra rounds of revision.
3. **A.** Marking estimates is a rule that limits what the assistant may assume or present. B is context, C is what good looks like and D is the goal.
4. **D.** The chapter says problems in a first draft should become short, specific follow-ups rather than fresh starts or regenerations, and its example correction names the split and the reason.
5. **B.** A binary split encourages overclaiming, and giving the middle category a name tells the assistant that the supervised answer exists and is often the honest one.
6. **A.** Writing a prediction prevents hindsight bias and provides a comparison point for the checks in Step 5, which is where the learning happens.
7. **C.** Restricting the assistant to supplied papers with page references turned it from "an assistant remembering the world" into the safer "assistant reading your documents."
8. **D.** In long conversations an assistant can lose track of early instructions, so the chapter recommends folding what you learned into a fresh brief.
9. **B.** A saved four-part brief with a fixed layout made the reports consistent, and adding the regional split to the brief carried the improvement into every future report.
10. **C.** Requiring sources and marked estimates in the constraints creates ready-made points to check before the answer is even produced.

**Short Answer: Model Answers**

**1.** The skill is filling the gaps in a vague request correctly: knowing who the work is for, what it will feed, when it is due, how long it should be and what the requester dislikes. An experienced analyst could do this because they had spent years learning the person, the company and its calendar. For example, they would know that the board meets in November and that the boss hates long memos, and that knowledge was part of what their salary paid for. An AI assistant reads quickly and reasons well, but it arrives knowing nothing about you, your company or your deadline, and by default it starts each session without memory. It therefore fills gaps with generic defaults. That context has to be written into the request, which is what a brief does.

**2.** He focused on *what good looks like*. He pasted three of his best older descriptions as a model, named the voice and set a length. He also listed the facts each listing required and supplied a spreadsheet as context. The examples worked better than adjectives because the assistant could match an existing pattern instead of inventing one, so the thirty descriptions read as if one person had written them all. His verification targeted the costliest error: he checked every dishwasher-safe claim against the spreadsheet and found two that had been guessed where his sheet was blank. He fixed them and added a constraint to his saved brief: "If a fact is missing from the sheet, write MISSING, do not guess."

**3.** Iteration means improving an answer over several rounds through specific, targeted corrections, each building on the last, like a tailor's fitting. Regenerating means asking for a new answer to the same unchanged request, the slot-machine approach. It usually produces a different average rather than a better answer, because no new information is added. An effective correction would be: "In section two, cut the history of the project to one sentence, because the readers already know it, and lead with the recommendation." It works because it names a location, a specific change and a reason. That gives the assistant everything it needs in one line, whereas "make it better" adds no information.
