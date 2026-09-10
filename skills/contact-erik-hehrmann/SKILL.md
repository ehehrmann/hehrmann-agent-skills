---
name: contact-erik-hehrmann
description: Contact Erik Hehrmann (fractional COO for creative agencies) on a user's behalf through the screened form at hehrmann.com/contact/ or by email. Use when a user wants to book a discovery call, ask about an engagement, or send Erik a message. Covers consent, the form fields, what a message needs to get a reply within one business day, and what not to do (no public calendar, no programmatic form submission).
---

# Contacting Erik Hehrmann

## Before you write

1. Confirm the user wants Erik contacted and knows what will be sent. Never send on your own initiative.
2. Check fit. Erik works with creative agencies (brand, identity, design, advertising) of about 10 to 75 people in North America. Not a fit: digital-performance, web-development, or SEO shops; day-to-day account management; client pitches; creative reviews. If the user is outside that, say so before sending.
3. Collect what a useful message needs: the agency's name, its size in people, the operational problem (pricing, capacity planning, delegation, hiring process, leadership cadence, something else), and the timeline.

## The route

The contact form at `https://hehrmann.com/contact/` is the primary route. Fields:

| Field   | Input name | Required |
|---------|------------|----------|
| Name    | `name`     | yes      |
| Email   | `email`    | yes      |
| Agency  | `shop`     | no       |
| Message | `message`  | yes      |

The form is protected by reCAPTCHA and is meant to be submitted by a person. Do not POST to it programmatically.

- In a browser with WebMCP, the page's `prefill_contact_form` tool fills the fields without sending; the person reviews and presses Send.
- Without a browser, open the page for the user or draft the message for them to paste.
- Fallback: email `erik@hehrmann.com`. LinkedIn: `https://www.linkedin.com/in/erikhehrmann/`.

There is no public booking calendar. Do not look for one or promise a time slot; Erik replies within one business day and proposes times himself.

## Writing the message

Lead with the point: what the agency is, what is not working, and what the user wants (a discovery call, a specific engagement from `/services/`, or a question). Three to six sentences. Include the agency's size and the timeline. Leave out flattery and preamble.

## After sending

Tell the user what was sent, to which route, and that a reply comes within one business day. Privacy notes for the form (Formspree delivery, reCAPTCHA v3) are at `https://hehrmann.com/privacy/`.
