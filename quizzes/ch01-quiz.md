# Chapter 1 Quiz: Thinking Is Now a Utility
*Instructor resource, not published in the book.*

## Multiple Choice (10 questions)

**1.** A procurement team has thirty vendor agreements. It has only ever compared three of them for hidden price escalators, because a full comparison would take weeks of a junior analyst's time. According to the chapter, what does the cognition economy change most directly for this team?

- A. The team no longer needs anyone with business knowledge, because the model already knows the vendors.
- B. Checking all thirty becomes cheap enough to do. The advantage shifts toward knowing which questions to ask and which documents to supply.
- C. The team should hire more analysts, because AI output must be checked line by line.
- D. The comparison stays just as expensive, because metered pricing charges per document rather than per question.

**2.** The chapter compares rented reasoning to electricity from the grid. Which statement identifies the analogy's limit, as the chapter describes it?

- A. Electricity is billed monthly, while AI reasoning can only be paid for by subscription.
- B. Electricity requires owning a generator, while AI reasoning requires none.
- C. A kilowatt-hour can be stored for later, while reasoning must be used immediately.
- D. Every kilowatt-hour is identical, while rented reasoning varies in quality from task to task and its output has to be checked.

**3.** A café manager asks a chat assistant, "Can our supplier raise prices on us?" She does not attach the supply contract. She gets a careful but generic explanation of how supply agreements usually work. Based on the chapter, what is the most likely cause of the unhelpful answer?

- A. A failure of aim: the relevant contract was never in the model's context.
- B. A failure of intelligence: the model lacks the reasoning ability to interpret contracts.
- C. A hallucination: the model invented the generic explanation.
- D. A permission problem: the assistant was not allowed to read the question.

**4.** On Monday, you spend a session having Claude analyze your company's lease. On Friday, you open a new session and ask, "Based on the lease we discussed, when can we terminate?" You do not supply the lease again. What should you expect?

- A. An accurate answer, because a language model retains what it learned about your business the way a new hire would.
- B. An accurate answer, because the lease is now part of the model's parametric knowledge.
- C. The model will not have the lease unless a tool feeds it back in, so any specific answer is at risk of being generic or invented.
- D. An error message, because models refuse to answer questions that reference earlier sessions.

**5.** You want Claude to answer one question about staff scheduling. You have 200 company files available, and only about six are relevant. Which approach best follows the chapter's guidance on context?

- A. Load all 200 files, since modern context windows are large enough to hold them.
- B. Supply the smaller, well-chosen set of relevant files, because a model given a very long pile may give some parts less attention.
- C. Supply no files and rely on the model's training, which already covers typical scheduling policies.
- D. Load the files one per session so that each gets full attention.

**6.** In the course workspace, you ask Claude Code a question about a Word document. Which description of what happens matches the chapter?

- A. Claude runs a converter program, pandoc, to turn the Word file into plain text and then reads the text. You do not have to request this step.
- B. You must first convert the Word file to PDF, because Claude Code can only read PDFs.
- C. Claude reads the Word file directly, exactly as it reads a PDF, with no intermediate step.
- D. Claude infers the document's contents from its file name and folder location.

**7.** Claude Code stops and offers a permission prompt with the options **Yes**, **Yes, and don't ask again**, and **No**. Which response reflects what the chapter calls "the most valuable habit in this course"?

- A. Always choose "Yes, and don't ask again" so the workflow is not interrupted.
- B. Always choose "No," since any action outside the course folder is unsafe.
- C. Ignore the prompt, because reading and writing in the course folder is already allowed.
- D. Read what Claude proposes before approving, because the prompt is your moment of control.

**8.** A shipping company adds a 12 percent fuel surcharge to an invoice. The operations manager's experience says surprise surcharges are usually negotiable. Claude, given the contract, quotes a clause permitting surcharges of up to 15 percent. Following the chapter's lesson from the worked example, what should the manager do?

- A. Side with experience, since general industry knowledge is more reliable than a single document.
- B. Dispute the charge anyway, because the model may be hallucinating whenever it contradicts the user.
- C. Trust the documents over general wisdom, and verify the quoted clause in the contract before acting.
- D. Ask the model the same question again without the contract, to get an unbiased second opinion.

**9.** Since 2023, courts have sanctioned lawyers who cited nonexistent court decisions produced by AI chat tools. According to the chapter, what do these incidents have in common?

- A. The models were given the correct case files but misread them.
- B. The lawyers asked for precise facts that were not in the model's context, relied on parametric knowledge where it is weakest, and never opened the cited cases.
- C. The lawyers used metered API keys instead of subscriptions, which reduced answer quality.
- D. The model was asked to perform arithmetic on case citations and slipped.

**10.** The finance lead at a fitness-studio chain uses AI to explain month-to-month changes. She follows one standing rule: totals are recalculated in the spreadsheet itself and never accepted from the model's prose. Which failure from the chapter does this rule guard against?

- A. Stale knowledge from the knowledge cutoff.
- B. Overreach on business judgment.
- C. Missing context from unsupplied files.
- D. Mental arithmetic errors when a model adds numbers "in its head."

## Short Answer (3 questions)

**11.** Explain the course's guiding sentence, "the model brings the intelligence, you bring the knowledge," using the chapter's new-hire analogy. Then explain why the chapter argues that the person who knows the organization's documents becomes *more* valuable in the cognition economy, not less.

**12.** In the worked example, the lab's request to Claude contained four specific demands beyond simply asking a question. Identify these four demands. Then explain how the request as a whole, together with Step 5, turns "an answer you have to trust" into "an answer you have verified."

**13.** Explain why a large language model produces hallucinations and why you cannot detect one by its tone. Then describe the chapter's three-part habit for important answers and what to do depending on the result.

## Answer Key

**1. B.** The chapter says rented reasoning makes previously too-expensive questions affordable, which moves competitive advantage toward knowing which questions to ask and which documents to supply.

**2. D.** The chapter states that kilowatt-hours are identical, while rented reasoning varies in quality and must be checked in a way you never check whether your lights came on.

**3. A.** The chapter says most disappointing answers are failures of aim, and it uses this exact case: asking about supplier prices without supplying the contract yields a generic, useless answer.

**4. C.** The chapter says the model starts every day as day one and remembers nothing between sessions unless a tool feeds the information back in.

**5. B.** The chapter notes that a model given a very long pile can give some parts less attention, so a smaller, well-chosen pile often beats an enormous one.

**6. A.** The chapter explains that Claude runs pandoc to convert a Word file to plain text and chooses that tool itself, "the way you would: with whatever program opens it."

**7. D.** The chapter calls reading what Claude proposes before approving the most valuable habit, because the permission prompt is your moment of control.

**8. C.** The worked example teaches that when general wisdom and your specific documents disagree, you trust the documents and check the quote.

**9. B.** The chapter describes the shared anatomy: case details absent from context, reliance on parametric knowledge for precise detail, and no one opening the cited cases before filing.

**10. D.** The chapter describes her rule as the arithmetic failure turned into a standing policy, since models can slip when adding "in their head."

**11. Model answer:** An AI model is like a brilliant new hire on day one. It brings general reasoning, fluent writing and broad background knowledge from training, but it knows nothing about your specific business, such as your customers, contracts or internal concerns. It also starts every session from zero, so anything about your company has to be supplied in its context. Because intelligence is now cheap and rentable, the bottleneck is access rather than brains. Documents that organizations once treated as storage become fuel, since the value of the rented analyst depends almost entirely on what is put in front of it. The person who knows where the right files are, which are current and what question they should answer therefore becomes more valuable. Their role grows into supplying the knowledge that turns raw intelligence into a useful answer.

**12. Model answer:** The request asked Claude to:

- quote the clause,
- give a clear yes or no,
- say what Copperline could do next, and
- name the files it used.

The request also told Claude to save the answer as a file. Each demand makes the answer easier to check. A quote and file names point to exactly where the claim can be confirmed, and a clear yes or no leaves no vague hedging to interpret. In Step 5, the user runs the same Word-to-text converter in an ordinary terminal pane and reads clause 3 directly. Confirming that it matches Claude's quote takes about thirty seconds, and that personal check against the source is what converts a fluent answer into a verified one.

**13. Model answer:** A language model generates each answer by predicting the most plausible continuation, one token at a time. It does not retrieve verified records, so it can produce something plausible that is not true, such as a nonexistent clause or case. Hallucinations are most likely when the answer depends on something outside the model's context. A hallucination sounds exactly as confident and fluent as a fact. Unlike a bluffing person, the model has no reliable inner sense of when it has crossed into invention, so the check has to come from you. The three-part habit is:

1. Ask for the quote.
2. Ask for the file name.
3. Open the file and check one quote yourself.

If the quote matches, the rest of the answer earns provisional trust. If it does not, start over with a sharper request.
