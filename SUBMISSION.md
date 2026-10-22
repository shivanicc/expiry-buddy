# NextSpark Hacks — Devpost answers

## Project name
Expiry Buddy

## Elevator pitch
A one-page fridge tracker that tells you what to eat first so food stops going to waste.

## About the project

## Inspiration
Most food waste at home isn't from cooking too much, it's from things quietly expiring at the back of the fridge. Every "food inventory" app I tried wanted barcodes, accounts, and categories, so I stopped using it within a week. I wanted something faster than the problem: type a name, pick a date, done.

## What it does
Expiry Buddy is a single web page. You add items with an expiry date and it sorts them by urgency, colors them red (expired), yellow (3 days or less) or green (fresh), shows counts at a glance, and gives one plain-English tip about what to eat next. Everything is saved in your browser, so there's no account and nothing leaves your device.

## Who it helps
Anyone who buys groceries: students sharing a fridge, families, people cooking for one who can't get through produce before it turns. The target user is someone who would never maintain a full inventory but will happily spend five seconds when unpacking groceries.

## How I built it
One HTML file with vanilla JavaScript and CSS, no frameworks or dependencies. Items are stored as name and date in localStorage, re-sorted on every render, and bucketed by days remaining. Light and dark mode come from prefers-color-scheme.

## Challenges I ran into
A classic one: I named an input element "name" and referenced it as a bare global in the submit handler, which silently resolved to window.name instead of the element, so the form did nothing. Switching to explicit getElementById calls fixed it. Date math across time zones also needed care so "expires today" is right everywhere.

## What I learned
How much a tool is used depends more on how little it asks of you than on how much it can do. Cutting features was the main design work.

## What's next
Optional reminders via the Notifications API, a "used it" button that logs what you actually ate versus tossed, and shared lists for roommates.

## Built with
html, css, javascript, localstorage

## Tools and credits
Vanilla HTML/CSS/JS, no libraries. Claude Code (Anthropic) used to scaffold the page and draft the README. All logic written and verified by me.

## Repo
https://github.com/shivanicc/expiry-buddy

## Demo video script (1 to 3 minutes)
0:00 — Page open, empty. "This is Expiry Buddy. The problem: food expiring at the back of the fridge because inventory apps ask too much. This asks for a name and a date."
0:20 — Add "spinach" expiring tomorrow, "milk" expired two days ago, "leftover pasta" nine days out, "yogurt" in three days.
0:50 — Point at the list. "Sorted by urgency, red is expired, yellow is eat soon, green is fine. The counters show the state of the fridge at a glance, and the tip at the bottom says what to do next."
1:10 — Click the X on milk. "Toss it, remove it, the tip updates."
1:25 — Reload the page. "Everything persists in the browser, no account, no server."
1:40 — Show index.html briefly. "One file, no dependencies, MIT licensed. Thanks."
