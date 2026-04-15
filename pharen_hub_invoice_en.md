# Case Study: Incoming Invoice Tool with Pharen Hub

![Example invoice](invoice.jpg)

## Introduction

Imagine your desk piled high with paper, dozens of invoices arriving through different channels, and an accountant bouncing between email, folders and the ERP.  That was our customer’s daily reality before we stepped in.  Together we built an incoming‑invoice tool that replaced the paper chaos: invoices are automatically imported, read in less than two minutes and approved with a single click.

## Customer & key facts

| Customer | Platform type | Team | Industry | Users | Location | Market | Project duration |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Mid‑sized company | Incoming‑invoice tool | PM, app‑builder, process design, AI/OCR, QA | Finance/accounting | Accounting, purchasing, management | Germany | pan‑Europe | 4 months |

## Business value

Our conversations with the finance team made it clear: manual invoice processing costs nerves and money.  On average, a manual invoice costs \$15–\$40【755249572714523†L56-L63】, and more than half of companies spend ten or more hours per week on the process【755249572714523†L64-L66】.  Automation saves time—companies can process invoices up to 85 % faster【755249572714523†L74-L81】, the number of invoices processed per employee rises by 64 %【755249572714523†L87-L90】, and error rates drop by 90 %【755249572714523†L104-L113】.  Costs per invoice fall to \$2–\$5, about an 83 % reduction【755249572714523†L137-L144】.

- **More time for valuable work:** Where staff previously spent hours typing data, they can now focus on analysis and consulting.
- **Fewer errors:** Automatic data capture and validation reduce typos and duplicates【755249572714523†L104-L113】.
- **Cost savings:** Eliminating paper and manual effort cuts the cost per invoice【755249572714523†L137-L144】.
- **Smooth processes:** Clear workflows prevent delays and late‑payment penalties.

## User experience

The tool feels like a central inbox: incoming invoices are automatically collected and displayed in a structured way.  Key information—vendor, date, amount—is already filled in.  Users can review the details, add comments and approve or return the invoice with a click.  Warning messages highlight potential issues.  A mobile version lets users check invoices on the go.

## Customer benefits

- **Faster approvals:** Invoices are processed and approved in under two minutes.
- **Error prevention:** Intelligent fields detect duplicates and attempted fraud【755249572714523†L104-L113】.
- **Transparent history:** Every action is fully documented.
- **Less paper:** Digital workflows save space and effort.
- **Easy integration:** Connection to the ERP is seamless, without media breaks.

## Business impact

The new platform drastically shortened throughput times: invoices that used to take about 15 minutes are now completed in around two minutes【755249572714523†L92-L95】.  The team can handle 64 % more invoices per employee【755249572714523†L87-L90】, and costs per invoice have fallen by more than 80 %【755249572714523†L137-L144】.  Companies also benefit from early‑payment discounts and avoid dunning fees.  Transparency about outstanding liabilities improves budget planning.

## Project requirements

The client needed a solution that leverages existing Microsoft 365 and ERP environments, is flexible and automatically imports, reads, validates and books invoices.  Security and data protection were top priorities.

### Project phases

#### Discovery (1 week)

In short, intensive workshops we mapped the current process and identified pain points.  We evaluated various OCR services and workflow options and defined a clear target picture.

#### UI/UX design (3 weeks)

Together with the users we developed prototypes, tested them and adapted them.  A familiar environment that fits into Microsoft 365 was particularly important.  Hints and colour codes help avoid mistakes.

#### Development & integration (5 weeks)

**Pharen Hub** served as the low‑code foundation.  Using **Lists App Builder** we defined fields and workflows.  An OCR service analyses invoices and matches them against purchase orders.  Further components include:

- **Email, drive and ERP connectors** for data exchange.
- **Approval rules** with escalations.
- **Notification service** for reminders.
- **Reporting** with metrics such as processing time and savings.

## Our solution & architecture

The application runs in the cloud.  Invoices land in a SharePoint list and are read by an OCR service.  A workflow service assigns the invoice to the correct cost centre and determines the approval route.  The front‑end, built with the Lists App Builder, presents all information and allows approvals with a single click.  When approved, the data is automatically transferred to the ERP.  Dashboards provide an overview of outstanding invoices and cash flow.

## Highlights & design

- **Central inbox:** All invoices collected in one place.
- **Intelligent fields:** Automatic detection of invoice data and duplicates【755249572714523†L104-L113】.
- **One‑click approvals:** Workflows also work on smartphones.
- **Compliance & audit:** Every action is logged.
- **Key figures at a glance:** Reports show savings and throughput times.

## Outcome

Four months after project start the tool went live.  The processing time per invoice fell from about 15 minutes to roughly 2 minutes【755249572714523†L92-L95】, and the team could handle around 64 % more invoices per employee【755249572714523†L87-L90】.  Costs per invoice were reduced by more than 80 %【755249572714523†L137-L144】.  Employees felt relieved, and management finally had a transparent view of outstanding liabilities.

## Conclusion

By listening to people and understanding their workflows we were able to build a solution that simplified everyday work.  The combination of Pharen Hub, Lists App Builder and intelligent OCR shows how powerful digitalisation can be—for people and for the business.