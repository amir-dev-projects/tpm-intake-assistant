# tpm-intake-assistant
To assist TPM's during the request or requirement intake process.

# Project request intake

A short guided form I built for collecting requirements on new project requests. You answer a few questions at a time, it flags answers that are too vague, and at the end it gives you a summary and a readiness rating.

Live page: https://amir-dev-projects.github.io/tpm-intake-assistant/

It runs in your browser. Nothing you type is sent anywhere.

## Why I made it

I'm a technical program manager. When requests come into a project funnel, the first conversation is usually spent figuring out basics that should have been written down already. In my experience the same things go wrong a lot:

- The request is a solution ("we need a dashboard") with no problem behind it.
- "Success" has no number, so nobody can say later whether it worked.
- There's a deadline but nobody knows what's driving it.
- No sponsor is named.
- Security and data questions come up late, after the scope is set.

I wanted requesters to do a first pass on their own, in a consistent format, so my time with them goes to the parts that need a person.

## How I use it

I run it with the requester, and they don't have to touch the form:

1. We book a call, about 30 minutes. I explain what we're doing and why, and that "I don't know" is a fine answer.
2. I share my screen and ask the questions in plain language. I type the answers in as we talk, so they can describe the request the way they'd explain it to a colleague.
3. When an answer is vague, I ask for an example or a number and help them get to something clearer. When something is unknown, I write down who might know and take on finding out.
4. At the end I read the summary back, and they tell me what I got wrong or missed.
5. I send a short note with what we agreed, the open items I'm following up on, and when it goes to prioritization.

I own the process and the follow-up. The requester only has to tell me about the problem.

## What the page does

- Ten steps, each with a few questions: request basics, problem, value and success, scope, people, requirements, security and compliance, technical context, timeline and resources, and risks and rollout.
- A "Don't know" button on open questions. It records "Unknown" and asks who can answer it. Those show up as open questions in the summary.
- Flags on answers that look weak. They're suggestions. You can fix the answer or press Next again to move on.
- A summary page with a readiness rating, the top three gaps, and everything the requester entered. You can copy it as Markdown, download it as a `.md` file, or print it.
- Answers are saved in your browser, so a refresh won't lose them. "Start over" clears them.

## What gets flagged

The checks are simple pattern matching:

- Vague words such as "asap", "improve", "better", "scalable", "everyone"
- Success metrics with no number in them
- A problem statement that starts like a solution ("we need", "build", "implement")
- Very short answers
- A hard deadline with no known driver
- A target date that is already in the past
- Confidential or regulated data with no security review planned

There is no AI inside this page. It matches words and patterns. It will miss some vague answers and sometimes flag a fine one, so I treat the flags as prompts to ask a better question, not as a verdict.

## Readiness rating

- **Ready:** every required question is answered and nothing is flagged.
- **Needs more info:** something required is missing, unknown, or flagged. The summary lists the top three gaps.
- **Not actionable:** there's no problem statement or no named sponsor. I won't start triage without both.

The rating is a rough screen. It doesn't say whether a project is a good idea or how big it is.

## Privacy

Everything runs in the browser, and answers are stored in that browser's local storage only. I still wouldn't paste confidential details into any web page you don't control. If you use this for real requests, host a copy inside your own organization.

## Using it yourself

It's a single file, `index.html`, with no dependencies. Open it in a browser, or host it with GitHub Pages.

To change the questions, open the file and find the `STEPS` list near the top of the script. Each question has a label, a short name for the summary, a type (text, long text, or dropdown), and whether it's required. You can reword, add, or remove questions without touching the rest. The flag rules are in the section marked "Checks".

## Limits

- It captures one person's view. For large or cross-team requests it doesn't replace talking to the other stakeholders.
- The flags are keyword checks, as described above.
- There's no server, so nothing is shared or collected for you. Requesters have to send you their summary.
- I've tested it by clicking through it, not with a group of real requesters.

## What I'd measure

If I run this across a team, I'd track how long it takes to get from a new request to a clear scope, how many follow-up calls each request needs, how many requests arrive with a named sponsor and a measurable goal, and how often scope changes after intake. I'd also look at which questions people skip or get stuck on, and change those first.

## How I built it

I wrote the question list, the flag rules, and the readiness logic based on how I run intake. I used an AI assistant to help write the page itself, then tested it and fixed the problems I found.

## License

MIT. Use it, change it, share it.
