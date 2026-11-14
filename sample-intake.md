> This is a fictional example. The company, people, and numbers are made up. It shows the summary the intake page produces after a requester call.

# Route support tickets to the right team automatically

Support agents sort incoming tickets by hand, and it delays first replies. We want tickets sent to the right queue without manual sorting.

## Readiness

**Needs more info.** 2 open items to close before triage.

Top gaps:
1. Security review: unknown, ask Wei Chen, Information Security.
2. Security review: Sensitive or regulated data usually needs a security review. Confirm.

## Request

- **Requester:** Priya Nair, Customer Support Operations
- **Sponsor:** Marcus Webb, VP of Customer Operations
- **Date submitted:** 2026-11-14

## Problem

- **Problem:** Support agents spend the first part of each shift reading new tickets and moving them to the right queue. Tickets often sit in the general queue for hours, and about one in five ends up in the wrong queue and gets moved again.
- **Who is affected:** 42 support agents across three queues, and the customers waiting on a first reply. We handle about 1,800 tickets a week.
- **Handled today:** Two agents take turns as triage each day and move tickets by hand, using a spreadsheet of keyword rules.
- **Evidence:** Ticket system export for September: median time to first reply was 6.5 hours, and 21% of tickets were reassigned at least once. Three customer complaints in October mention slow replies.

## Value and success

- **Desired outcome:** New tickets reach the correct queue within minutes without anyone sorting them, and the two triage agents go back to answering tickets.
- **Success metrics:** Median time to first reply: 6.5 hours today, 2 hours by the end of Q2 2027.
  Tickets reassigned after first routing: 21% today, under 8%.
  Triage hours per week: about 30 today, under 5.
- **Cost of inaction:** Reply times stay long going into the spring peak, and two agents stay out of the queues every day.
- **Linked goal:** Customer Operations goal for 2027: cut median first reply time in half.

## Scope

- **In scope:** Automatic routing of new email and web form tickets to one of the three existing queues.
  A way for agents to correct a wrong routing and report it.
  A weekly report of routing accuracy.
- **Out of scope:** Chat and phone channels. Automatic replies to customers. Changes to the queue structure itself.
- **Definition of done:** New tickets are routed automatically for four weeks in a row, and the accuracy and reply time targets are met in the weekly report.
- **First phase:** Start with email tickets for one queue, run it beside the manual triage for two weeks, then expand to the other queues.

## People

- **Users:** Support agents, and the two team leads who manage the queues.
- **Approvers and consulted:** Marcus Webb for approval. Information Security and the support tooling team to be consulted.
- **Operators:** The support tooling team runs it after launch. Team leads review the accuracy report each week.

## Requirements

- **Functional requirements:** Read new tickets as they arrive.
  Choose a queue based on the ticket text and the customer's plan.
  Let agents move a ticket and mark the routing as wrong.
  Send a weekly accuracy report to the team leads.
- **Integrations and data:** Connects to the current ticketing system through its API. Reads ticket text, customer plan, and product. Writes the queue assignment back to the ticket.
- **Non-functional requirements:** Routing decision within 2 minutes of a ticket arriving.
  Runs during support hours, 6am to 10pm Pacific, Monday to Saturday.
  Every routing decision is logged for audit.

## Security and compliance

- **Data classification:** Confidential
- **Regulated data:** Yes
- **Security review:** Unknown
- **Compliance notes:** Tickets contain customer names, emails, and sometimes order details. The privacy team has not looked at this yet.

## Technical context

- **Systems affected:** The current ticketing system, the customer database (for plan type), and the weekly reporting dashboard.
- **Dependencies:** The support tooling team has to give API access. The data team provides the customer plan lookup.
- **Build or buy:** Unknown

## Timeline and resources

- **Target date:** 2027-03-31
- **Deadline type:** Hard
- **Date driver:** Our contract with the current ticketing vendor renews on 2027-03-31. We need to know the routing works before we sign for another year, because it affects which plan we choose.
- **Budget:** Unknown
- **Committed people:** Priya is the day-to-day contact. Two team leads will help test. One engineer from support tooling has been asked but has not confirmed.

## Risks and rollout

- **Risks:** Mistakes on high-value customer tickets.
  Agents may not trust the routing at first.
  The privacy review could take longer than planned.
- **Assumptions:** The ticketing system API allows reading ticket text and changing the queue. The current queue structure stays the same through Q2.
- **Constraints:** No changes to the ticketing system during the spring peak, which starts in April.
- **Rollout and adoption:** Team leads brief agents before the trial. A short guide for correcting a wrong routing. Support tooling takes over questions after launch.
- **Priority context:** Ahead of the reporting dashboard refresh, which can wait. Behind the planned ticketing system upgrade, which this depends on. Each month of delay costs about 30 triage hours a week.

## Open questions

- Security review (ask Wei Chen, Information Security)
- Build or buy (ask Support tooling team lead)
- Budget (ask Dana Okafor, Finance partner)
