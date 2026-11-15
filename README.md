# TPM Intake Assistant

I built the TPM Intake Assistant to make the early stage of project
intake more structured and useful. It helps me understand a project
request, identify what is missing, and prepare for the conversations and
decisions that need to happen before a request moves forward.

I wanted something practical and easy to use. I also wanted to keep it
simple: no account, no backend, no paid service, and no external API.
The application runs in the browser, and the information stays in the
browser where the intake was created.

**Live application:** [Open TPM Intake
Assistant](https://amir-dev-projects.github.io/tpm-intake-assistant/)  
**GitHub repository:**
[amir-dev-projects/tpm-intake-assistant](https://github.com/amir-dev-projects/tpm-intake-assistant)

------------------------------------------------------------------------

## Why I built it

In my experience, a project request can arrive before the problem is
properly understood. The initial information may be limited, and
important questions are often still open.

What problem are we trying to solve? Who is affected? What would success
look like? Who is responsible for the decision? Are there technical
dependencies, security concerns, deadlines, or resource constraints?

I built this application to bring those questions into one place. I
wanted the intake to guide a useful conversation, not just collect
answers in a form. It should help me see what we know, what we don’t
know yet, who can help clarify it, and what needs attention next.

My intention is not to replace TPM judgment or stakeholder discussions.
I use the application to prepare for those discussions and make them
more focused.

## How I structured the intake

I organized the application into 12 steps. The first ten steps collect
information about the request. The last two help me assess the
information and prepare a report.

| Step | Section                 | What I capture                                                                  |
|------|-------------------------|---------------------------------------------------------------------------------|
| 1    | Request basics          | Request title, requester, sponsor, submission date, and a short summary         |
| 2    | Problem                 | The problem, who is affected, how it is handled today, and available evidence   |
| 3    | Value and success       | Desired outcome, success measures, cost of inaction, and related business goals |
| 4    | Scope                   | What is included, what is excluded, and what done should look like              |
| 5    | People                  | Users, approvers, consulted stakeholders, and operational owners                |
| 6    | Requirements            | Functional requirements, integrations, data, and non-functional needs           |
| 7    | Security and compliance | Data classification, regulated data, and security review status                 |
| 8    | Technical context       | Affected systems, dependencies, and build-or-buy considerations                 |
| 9    | Timeline and resources  | Target date, reason for the date, budget, and committed people                  |
| 10   | Risks and rollout       | Risks, assumptions, constraints, rollout, adoption, and support                 |
| 11   | Assessment              | Readiness, blockers, important gaps, suggestions, and follow-up actions         |
| 12   | Report & Downloads      | The complete report and options to copy, download, or print it                  |

### Making the intake easier to complete

I added a few features to make the form easier to work through:

- **Progress tracking:** I can see how many required questions have been
  addressed, both across the full intake and within the current section.
  The navigation also shows which sections are complete or still in
  progress.
- **Example answers:** I added examples to selected questions to show
  the type of detail that is useful.
- **Don’t know option:** I don’t want people to guess when they don’t
  have an answer. They can mark information as unknown and, where
  useful, name a person or team who may be able to clarify it.
- **Answer checks:** I added simple checks to highlight answers that may
  need more detail. For example, the application can flag vague wording,
  very short answers, a success measure without a number, or an answer
  that describes a solution before explaining the problem.
- **Flexible navigation:** I can move between sections, update answers,
  and return to the assessment or report.

These checks are there to prompt a better conversation. They are not
meant to judge the requester or stop the intake from moving forward.

## How I assess a request

I wanted the assessment to be clear and easy to understand. Instead of
showing one score, I separate the findings into three groups:

- **Blockers:** Issues that prevent meaningful triage. For example, the
  problem is not clear or there is no identified sponsor.
- **Important gaps:** Information that still needs clarification before
  the request can be evaluated with confidence.
- **Suggestions:** Other areas where more detail could make the request
  stronger.

I use three intake statuses:

| Status                  | How I interpret it                                                                           |
|-------------------------|----------------------------------------------------------------------------------------------|
| **Not actionable**      | The core problem or accountable sponsor is missing or unknown.                               |
| **Needs clarification** | The problem and sponsor are identified, but important information still needs clarification. |
| **Ready for Triage**    | The request contains the core information needed to begin triage.                            |

I use the wording **Ready for Triage** deliberately. It does not mean
the project is approved, funded, prioritized, or ready to start
delivery. It only means there is enough core information to begin a
triage discussion.

The assessment is based on required-field checks and straightforward
pattern matching. I kept the rules visible and simple. They are not a
substitute for reading the answers in context, and a person should
always review the findings.

## TPM Decision Support

I wanted the application to do more than tell me whether information is
missing. It should also help me work out what to do about it.

For that reason, I added decision-support sections to help me prepare
the next conversation around a request.

### Decisions requiring attention

I use this section to see which decisions may need stakeholder
attention, who may be the right person to make or support the decision,
and what information is still needed.

### Ownership gaps

I use this section to check whether important responsibilities have been
identified. This can include approvers, people who need to be consulted,
the team that will operate the solution after launch, and teams needed
to deliver the work.

A missing name in the intake does not necessarily mean that nobody owns
the responsibility. It means I need to confirm it.

### Dependencies to validate

I use this section to review dependencies and technical touchpoints
captured in the request. It helps me identify what needs to be confirmed
with other teams before making delivery assumptions.

### Recommended next steps

Based on the answers and assessment findings, the application prepares a
set of suggested follow-up actions. These can relate to missing
information, ownership, success measures, security review, dependencies,
or stakeholder alignment.

### Stakeholder discussion questions

I also wanted to make it easier to prepare for conversations with
different groups. The application creates questions for relevant
stakeholders, such as the sponsor, product, engineering, security and
privacy, delivery, and operations.

I treat these as prompts, not decisions made on behalf of the
stakeholders. The recommendations are based on the information entered
in the intake. The application does not invent project facts, assign
actual owners, approve funding, or decide which initiative should be
prioritized.

## The executive report

The **Report & Downloads** page brings the intake information and
assessment together in one place. This is one of the parts I wanted to
get right because I need an output that is useful outside the
application and can be shared in a stakeholder discussion.

The report includes:

- Executive summary and decision snapshot
- Business context and information provided by the requester
- Assessment findings: blockers, important gaps, and suggestions
- Decisions and clarifications required
- Recommended next steps
- Decisions requiring attention
- Ownership gaps and follow-up prompts
- Dependencies to validate
- Stakeholder discussion questions
- Open questions
- The complete intake record

I kept the report structured so that it is easy to review and follow. It
also makes a distinction between information supplied in the intake and
findings or recommendations produced by the assessment.

### Download and sharing options

I added several ways to use the report:

- **Copy executive report:** I can copy the report and use it in another
  document or message.
- **Download Markdown (.md):** I can save a Markdown version of the
  report.
- **Download Word (.docx):** I can download an editable Word document
  and open it in Microsoft Word or Google Docs.
- **Print report:** I can print the report or save it as a PDF through
  the browser.

The report files are generated in the browser using the current intake
answers. I don’t need to send the information to an external
document-generation service.

## How I expect to use it

I see this as a way to support the conversation between the requester
and the TPM. I don’t expect every requester to know all the technical,
security, operational, or delivery details at the beginning.

A typical intake could work like this:

1.  I start by understanding the request and the problem behind it.
2.  I work through the questions with the requester and capture what is
    known.
3.  When an answer is unclear, I ask for an example, evidence, a number,
    or more context.
4.  If something is unknown, I record it as unknown rather than making
    an assumption. I also identify who may be able to provide the
    answer.
5.  I review the assessment and use it to prepare the follow-up with the
    sponsor and relevant teams.
6.  I share the report so everyone has a common view of the request,
    open questions, decisions, and next steps.

For me, the value is not in completing every field. The value is in
getting a clearer understanding of the request and knowing what needs to
happen next.

## Privacy and data handling

I kept the application browser-based and local:

- The application runs in the browser.
- I use the browser’s `localStorage` to keep answers available after a
  refresh in the same browser.
- The application does not send intake answers to a server or external
  API.
- The **Start over** option clears the saved answers in that browser.
- Reports are generated and downloaded on the user’s device.

One important point: because the application is published through a
public GitHub Pages site, I would not use it for confidential, personal,
regulated, or company-sensitive information unless the organization has
approved that use. For real organizational information, I would use an
environment that meets the organization’s security and data-handling
requirements.

## Running it locally

The application is a single HTML file.

1.  Clone or download this repository.
2.  Open `index.html` in a modern browser.
3.  Start a new intake or continue an intake saved in that browser.

I can also use the [live GitHub Pages
application](https://amir-dev-projects.github.io/tpm-intake-assistant/).

There is no build step, package installation, backend, or API key
required.

## Technology and implementation

I built the application with:

- HTML
- CSS
- Vanilla JavaScript
- Browser `localStorage` for saving intake answers
- Client-side generation of Markdown reports
- Client-side generation of Word (`.docx`) reports

I chose this approach to keep the application lightweight and easy to
run. I didn’t want to introduce a backend or depend on paid services for
something that can run in the browser.

I designed the intake structure, the questions, the assessment
categories, the readiness rules, and the decision-support flow around
the way I think a TPM should approach an early project request.

## Current scope and limitations

I have intentionally kept this version focused on one project request at
a time. It is an intake and decision-support tool, not a portfolio
management system.

At this stage, it does not:

- Compare multiple initiatives or calculate portfolio rankings.
- Decide whether a request should be funded, approved, or prioritized.
- Replace sponsor decisions or stakeholder discussions.
- Replace technical discovery, security or privacy reviews, or financial
  approval.
- Verify whether the information entered by a requester is accurate.
- Provide shared storage, multi-user collaboration, or centralized
  administration.

The intake is saved in one browser. When a request involves several
teams, I still need to validate the information with the people
responsible for those areas.

## What I would like to learn from using it

If I use this application with a team, I would be interested in
understanding whether it helps:

- Reduce the time needed to clarify a new request.
- Reduce the number of follow-up conversations needed to collect basic
  information.
- Improve how often requests have a named sponsor and a measurable
  outcome.
- Identify scope questions and dependencies earlier.
- Show which questions are difficult for requesters to answer, so I can
  improve the intake.

These are areas I would like to observe and measure. I haven’t presented
them as results or benefits already achieved.

## License

This project is licensed under the [MIT License](LICENSE).
