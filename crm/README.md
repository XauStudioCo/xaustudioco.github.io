# XAU Prime CRM design preview

Interactive, browser-local prototype based on the approved light dashboard design. This preview is separate from the public XAU Studio marketing site.

## Included

- Dashboard with four opportunity metrics, a compact eight-stage lead flow, payment chart, appointments, website sample insights, and XØ AI demos.
- Leads board and table views, source/service/search filters, time-range filtering, lead creation/editing, client details, drag-and-drop stage changes, and a stage selector for touch and keyboard users.
- Supporting sample screens for Customers, Projects, Estimates, Invoices, Calendar, Messages, Documents, Website, Automations, AI Agents, and Settings.
- Browser-local persistence, sample reset, and a simulated incoming website lead.

## Metric definitions

- Total Leads: all records created in the selected reporting period.
- Won Jobs: records currently in Won, Work in Progress, or Job Completed.
- Win Rate: Won Jobs divided by Won Jobs plus Lost records, using the same creation-date cohort.
- Pipeline Value: only New Lead, Inspection Scheduled, Estimate Sent, and Contract Signed records in that cohort.
- Revenue Performance: a separate illustrative payment series, not the sum of won opportunities.

The lead stages, in order, are New Lead, Inspection Scheduled, Estimate Sent, Contract Signed, Won, Work in Progress, Job Completed, and Lost. Lead acquisition source and AI assistance are separate fields.

## Preview limitations

All customer, financial, analytics, AI, and calendar information is sample data. Changes are stored in localStorage under `xau-prime-preview-v1`, in the visitor's browser. No Supabase database, Retell agent, email, SMS, payment service, document signature service, or calendar account is connected. No real customer messages are sent.

This is a visual and interaction prototype, not an authenticated production CRM. It does not store secrets. Production work needs server-side authorization, tenant isolation, durable data, proper historical outcome metrics, and the chosen integrations before customer use.

## Source and serving

The `dist` directory is the source for this buildless preview. Serve it with any static web server. The GitHub review branch mirrors its contents under `crm/`, allowing the marketing site to remain unchanged until approval.

## Verification

- JavaScript syntax checked with `node --check dist/app.js`.
- Desktop Dashboard and Leads visually reviewed in the browser.
- Mobile layout reviewed in a 390-pixel iframe viewport; document width remained contained.
- Search and source filters, board/table switching, new-lead creation, and local persistence checked through the UI.
- Won → Work in Progress → Job Completed retained the same won-job total and pipeline value.
- A simulated website lead increased lead count and open pipeline value.

The current mascot is reused from the XAU Studio GitHub repository.
