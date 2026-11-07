# Signal Board

**Make room for the signal.** Signal Board is a chat-first personal planning workflow for turning a noisy Discord room into a calm, source-linked plan. Codex joins the room through Switch, groups related messages, flags genuine urgency, and prepares a next-day brief. The person reviews the result and stays in control of replies and calendar changes.

## Project status

- `signal-planner.template.yaml` is the Switch room template for the Codex agent.
- `index.html` is an optional neon planner UI concept with sample messages. It is not connected to Discord or Switch and is not required for the chat workflow.
- Calendar changes and outgoing replies are not wired up. The agent proposes and drafts; a person must review external actions.

Do not describe the project as a live Discord integration until the real Switch room has been connected and demonstrated.

## Set up the Switch room

1. In Switch Console, finish setting up a local Switch server and select **Codex** as the agent provider.
2. Import `signal-planner.template.yaml` in Switch Console. It creates a room and one `signal-planner` agent. Confirm the provider resolves to Codex.
3. Connect Discord to the Switch server using the Console's **Messaging apps** section. You need a Discord server where you can add a bot and manage channels.
4. In Discord Developer Portal, create the bot, enable **Server Members Intent** and **Message Content Intent**, and invite it with the `bot` and `applications.commands` scopes plus the permissions listed in the [Switch Discord guide](https://docs.switchagents.ai/switch-rooms/deploy/messaging-apps/discord).
5. Paste the bot token and Discord server ID directly into Switch Console. **Never add the bot token to this repository or paste it into chat.**
6. Post a message in the Discord channel you want to use. Switch creates the matching room when a message or command appears. Confirm the room and Discord connection are visible in Switch Console.

## Try the workflow

In the connected Discord channel, ask the agent to:

```text
@signal-planner triage the recent messages. Group related items, show DO NOW / PLAN / WAITING / FYI, explain why each item surfaced, and include a link to its source.
```

Then try:

```text
@signal-planner prepare tomorrow's brief from this room. Separate confirmed dates from suggestions that need my approval.
```

The template tells the agent not to invent dates or owners, silently send replies, or claim calendar changes are complete.

## Optional planner UI

Open `index.html` in a browser. It is a self-contained visual prototype with category filters, a next-day brief, and a simulated calendar approval interaction. Its sample Discord messages are illustrative only; they do not come from a connected server.

## Demo path

1. Show real messages arriving from one Discord channel through Switch.
2. Ask the Codex agent to triage the room and show grouped signals with source links.
3. Ask it to prepare tomorrow's brief and explain one item's priority.
4. Review a draft action in chat. Demonstrate an external action only if it is actually connected and approved.

## Hackathon submission

The repository is public. Before submitting, finish the Discord connection, capture a sub-three-minute video of Codex working in the real Switch/Discord room, and confirm this README matches the setup you demonstrated. A live deployment link is optional; a dashboard is not required for the chat workflow.
