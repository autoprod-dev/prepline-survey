# Prepline survey (Autoprod)

A one-page, one-minute anonymous survey for Prepline, the free kitchen prep-list organiser
(https://autoprod-dev.github.io/preplist-sorter/). Static site on GitHub Pages:
https://autoprod-dev.github.io/prepline-survey/

- No sign-in, no cookies, no trackers, no web fonts, no CDN. The page's only outside request is the
  answer submission when someone presses Send.
- Answers are sent to an Autoprod-owned Google Form (email collection off, no sign-in). Responses land
  in a private Google Sheet in that account. `ENDPOINT` in `index.html` is the form's `formResponse` URL.
  The send uses `fetch` with `mode: 'no-cors'` and URL-encoded form fields. If the send fails, the page
  offers a pre-filled link that opens the Google Form.
- `noindex` (robots meta + robots.txt). Content-Security-Policy (`connect-src https://docs.google.com`) and `no-referrer`.
- The `from` link parameter plus the survey version go into the form's internal Source field.

Questions or feedback: autoprod.help@gmail.com
