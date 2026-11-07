# Signal Board

**Make room for the signal.** Signal Board is a personal command center concept for turning a noisy Discord into a calm, reviewable plan. A Switch-connected agent sorts messages into urgent actions, planned tasks, follow-ups, and quieted context. The person stays in control of calendar additions and replies.

## Current prototype

The dashboard in `index.html` is a self-contained interactive front-end with sample messages. It demonstrates category filters, source links, a next-day briefing, digest feedback, and an approval step before adding a suggested calendar event. Calendar approval is simulated in the browser; the Discord messages are sample content. No Discord or calendar account is connected yet.

## Intended Switch workflow

1. Connect a selected Discord channel to a Switch room.
2. Add a triage agent to the room. It classifies messages as `urgent`, `plan`, `waiting`, or `fyi`; extracts a task, due date, suggested next action, and source message link; and explains why it surfaced the item.
3. Have the agent post structured signal cards or a daily briefing back into the Switch room. The dashboard consumes that room output and renders the board.
4. When the user approves a calendar suggestion, create the calendar event and report success back in the Switch room. Draft replies for review before posting.

Keep the first live version scoped to one server, a few channels, one calendar, and human approval for external actions. Avoid silently sending replies or creating events.

## Demo path

1. Show a busy Discord room entering through Switch.
2. Show the agent grouping routine chatter and flagging an urgent deadline with its original message link.
3. Open the next-day briefing and inspect why an item was included.
4. Approve a proposed calendar event and show the board update.

## Run locally

Open `index.html` in a browser. The prototype uses no build step or package installation. `dist/index.html` is the static deployment copy.

## Submission notes

Explain the Switch room, agent instructions, and message-to-board flow in the final README/video. Replace sample cards with messages from a real Switch-connected Discord room before presenting this as a live integration. Switch should be central: the chat room is where context is shared and the agent reports work, while the dashboard is the user's review and approval surface.
