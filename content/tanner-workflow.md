F.E.R.A.L. AI-Assisted POC Workflow Summary
How we used GPT, GitHub Copilot, documentation, and small steps to turn Jen’s vision into a local

mock-up

Why this document exists
Jen, this is a plain-language summary of how we approached the first F.E.R.A.L. proof-of-concept. The goal
is not to make development feel mysterious. The goal is to show that the process can be broken into small,
understandable steps, especially when AI tools are used thoughtfully.
The biggest lesson: we did not start by coding. We started by protecting the heart of the idea, shaping the
user experience, and documenting boundaries before asking Copilot to build anything.

The main idea we were testing
The working question for the mock-up became:
Can the interface emotionally deliver what the documents describe?
That question guided the whole process. We were not trying to build the full app yet. We were trying to see
whether a simple local browser experience could feel warm, practical, low-shame, and useful in the moment.

The tools we used
ChatGPT / GPT
GPT was used mostly as the planning partner, senior developer reviewer, product/UX discussion partner,
and prompt-writing assistant. It helped us slow down, clarify tradeoffs, and turn fuzzy ideas into focused
instructions for Copilot.
 Discussed product strategy, app boundaries, UI/UX patterns, and architecture choices.
 Helped interpret the Master Document into implementation-safe guidance.
 Generated prompts for GitHub Copilot so each build step stayed focused.
 Reviewed Copilot’s plans and outputs from a senior developer/product owner perspective.
 Helped avoid accidental scope creep, medicalized language, storage assumptions, and over-
engineering.
GitHub Copilot
Copilot was used as the coding assistant inside Visual Studio Code. Once the instructions were clear,
Copilot created and modified files, wired flows, and tested behavior locally.
 Converted and organized project documentation.
 Created the local browser POC using plain HTML, CSS, and JavaScript.
 Built one journey at a time instead of trying to build the whole application.
 Added print, copy, reflection, and local-only crisis support behavior.
 Ran browser checks and corrected regressions when something landed in the wrong place.
Visual Studio Code

F.E.R.A.L. POC Workflow Summary

Visual Studio Code was the development workspace. It let us edit files, talk to Copilot, run the local mock-up
in a browser, use the terminal, and work toward GitHub publishing.
GitHub / GitHub Desktop
GitHub was used to preserve and share the project. GitHub Desktop and command-line Git were part of the
publishing process. This part got confusing, which is normal. Git is powerful, but the first setup can be
awkward. The important troubleshooting lesson was to slow down, verify the folder path, and confirm which
folder was actually a Git repository.

The roles we used while thinking
One helpful part of the process was pretending to wear different hats. This kept us from only thinking like
developers.
 Jen as vision owner: the voice, lived experience, emotional truth, and community purpose.
 Tanner as product owner and junior/full-stack contributor: asking what is smallest, safest, most useful,
and maintainable.
 GPT as senior lead full-stack developer / reviewer: challenging assumptions, reviewing architecture, and
writing focused Copilot prompts.
 Copilot as implementation assistant: building what was clearly requested inside the repo.
 Future users as overwhelmed humans: people arriving tired, stressed, guilty, confused, or needing
something useful right now.

How we structured before building
1. We converted the Master Document into the source of truth
The Master Document was treated as more than notes. It became the source for tone, emotional journeys,
product philosophy, accessibility rules, and content direction.
 MASTER_DOCUMENT.md became the human source document.
 UX_PRINCIPLES.md became the implementation interpretation of that source.
 POC_PLAN.md became the scope and validation guide.
 README.md became the simple orientation document for the repo.
2. We separated emotional truth from implementation rules
This mattered a lot. For example, “two taps maximum” was preserved as emotional intent, but clarified so
Copilot would not treat it as a rigid architecture rule. The implementation goal became: simple to use, not
necessarily simplistic underneath.
3. We documented what this POC is not
This helped protect the project from growing too fast.
 Not a production app.
 Not a medical platform.
 Not a diagnosis or treatment tool.
 Not a stored health record.
 Not an account-based system.
 Not a backend or database project yet.

F.E.R.A.L. POC Workflow Summary

4. We built one emotional journey at a time
Instead of building the whole app, we built complete little slices:
1. My stomach hurts → Feral Spaghetti
2. Track what’s happening → Guided Reflection
3. I’m overwhelmed → Support card
4. Write This Down → Reflection handoff
This kept the project small enough to understand and test emotionally.

Key UX decisions we made
 The home screen asks, “What do you need right now?” instead of looking like a complex menu.
 The interface should feel cognitively shallow, even if the app eventually has more depth.
 The app should help people return to real life, not trap them inside the app.
 Print and Copy are first-class actions because people use screenshots, notes, texts, and paper in real
life.
 “Write This Down” was chosen instead of “Journal” or “Save” because it does not imply stored history.
 Guided Reflection is not persistent journaling. It is a temporary place to organize thoughts and print or
copy them.
 Action buttons were grouped as “Take this with you” and “What would help next?” to reduce mobile
clutter.
 Unbuilt paths should feel gentle, not broken.

Safety-support boundary
A requirement came up to support crisis-related language. We took that seriously but carefully. The POC
includes local-only crisis keyword support, but it is intentionally simple pattern matching, not contextual
interpretation.
 If certain crisis-related words are typed, the app shows a warm 988 support prompt.
 It does not log, store, or transmit what the user typed.
 It does not score risk or analyze intent.
 It is not clinical detection, monitoring, or emergency response.
 The user remains in control.
This was an important example of caring about safety without pretending the prototype is a crisis platform.

What prompt engineering did for us
Prompt engineering was not just “asking AI to code.” It was the process of turning intent into clear, bounded
instructions.
 We told Copilot exactly which files to use and which docs to treat as source guidance.
 We specified what not to build, which was just as important as what to build.
 We asked for one journey at a time.
 We included acceptance criteria so Copilot knew what “done” meant.

F.E.R.A.L. POC Workflow Summary
 We reviewed outputs and sent correction prompts when the result drifted.
 We used GPT to create prompts that protected the product philosophy before Copilot touched the code.

A helpful pattern for learning with AI
This workflow is repeatable:
1. Describe the goal in plain language.
2. Clarify what the app should not do.
3. Decide the smallest useful slice.
4. Ask GPT to help shape a focused Copilot prompt.
5. Give Copilot the relevant docs and acceptance criteria.
6. Run and test the result manually.
7. Fix only the next visible problem.
8. Stop before adding too much.

ADHD-friendly development notes
A few things helped keep the process manageable:
 Work in small loops. One path, one problem, one test.
 Keep a visible checklist of what “done” means.
 Do not let AI add ten extra ideas when you asked for one.
 Name the next step before starting it.
 When stuck, stop typing commands and describe what is on screen.
 Screenshots are useful. They let someone else see the exact problem.
 If a tool feels confusing, the answer is usually to verify location, file path, and current state before doing
more.
 Celebrate working slices. A small working path is better than a huge unfinished plan.

Troubleshooting notes from this build
 Git and GitHub setup can be confusing because the folder you see and the repository Git tracks may not
be the same folder.
 When Git says “not a git repository,” check the exact folder path.
 When GitHub only shows one file, the real files may be in a nested folder or outside the repository root.
 When stuck inside a terminal editor like Vim, do not panic. Press Esc, then use a safe exit command or
ask for help before continuing.
 Before pushing, run a quick check: does the repo contain README.md, docs, and src?

What exists now
The current POC is a local browser mock-up. It can be opened by launching src/index.html. It includes:

F.E.R.A.L. POC Workflow Summary
 A warm home screen with “What do you need right now?”
 A Feral Spaghetti path for practical food help.
 A guided reflection path for capturing what happened.
 An “I’m overwhelmed” path to test emotional support.
 A “Write This Down” handoff from content cards into reflection.
 Print and Copy outputs.
 Local-only 988 support prompt behavior for crisis-related text entry.

Suggested feedback questions for Jen
 Does this feel like F.E.R.A.L.?
 Does it sound like you?
 What feels wrong?
 What feels missing?
 What made you smile?
 What made you hesitate?
 Did anything feel too clinical, too polished, or too app-y?
 Would someone understand what to do next?

Recommended next development steps
After Jen reacts to the POC, the next steps should stay small:
1. Review Jen’s emotional feedback before adding features.
2. Adjust tone and layout if something does not feel like her.
3. Add the “Help me grocery shop” journey next if the current emotional model feels right.
4. Continue one journey at a time.
5. Avoid storage, accounts, and backend complexity until there is a clear reason.

Closing thought
The biggest win was not that AI wrote code. The biggest win was that we used AI to slow down, protect the
vision, and build a tiny working version without losing the human voice. That is the habit worth carrying
forward.
