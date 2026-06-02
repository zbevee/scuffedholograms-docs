# Interactions & Actions

Any hologram can run one or more **actions** (commands) when a player interacts with it. This turns a hologram into a button: a shop opener, a teleport portal, a reward claim, a quest giver, and so on. Actions are configured on the hologram's **Triggers + Permissions** tab in the edit GUI.

## Triggers

A hologram fires its action list on one of two events, chosen by its **trigger mode**:

| Trigger | Fires when |
|---------|-----------|
| **Interact** (default) | A player clicks the hologram |
| **Collision** | A player walks into the hologram |

Each hologram has a single action list bound to whichever trigger you pick.

## Action modes

The **action mode** controls how the list is processed each time the hologram is triggered:

| Mode | Behaviour |
|------|-----------|
| **All** (default) | Every action rolls its own chance independently. Any number may fire on a single trigger. |
| **Roll** | A weighted pick. Exactly **one** action fires, chosen at random using each action's chance as its weight. |
| **Checklist** | A carousel. Fires the **next** action in order, advancing one step per trigger and looping back to the first after the last. Progress is tracked per player and survives restarts. |
| **Quest Chain** | A quest-gated sequence (see below). |

### Quest Chain

Quest Chain turns a hologram into a quest-giver NPC. Each action is given a **quest ID**, and the hologram always fires the first action whose quest the player has **not** completed. That action keeps firing on every interaction until the player completes its quest, then the hologram advances to the next action.

When the player has completed every quest in the chain, the **chain-end mode** decides what happens:

| Chain-end mode | Behaviour |
|----------------|-----------|
| **Stop** (default) | Nothing fires. The NPC has nothing left to give. |
| **Loop** | Restart from the first action (for repeatable or daily givers) |
| **Last** | Keep firing the last action forever (for example a "thanks, hero!" line) |

An action with a blank quest ID fires unconditionally as a filler step, such as a greeting line. Quest Chain needs a supported quest plugin (see [Integrations](integrations.md)).

## Action settings

Each action in the list has:

| Setting | Values | Meaning |
|---------|--------|---------|
| **Command** | text | The command to run. A leading `/` is optional. |
| **Run as** | Console / Player | Console runs with full privileges. Player runs the command as the interacting player, using their permissions. Default: Console. |
| **Chance** | 1 to 100 | Percent chance the action fires (used as the weight in Roll mode). Default: 100. |
| **Delay** | 0 to 300 s | Seconds to wait before running. Default: 0 (immediate). Pending delayed actions are dropped if the server restarts. |
| **Quest ID** | text | Only used in Quest Chain mode (ignored otherwise). |

Commands can contain [placeholders](placeholders.md) such as `{player}`, `{x}`, `{y}`, and `{z}`, which resolve to the interacting player before the command runs.

To save typing, the Add Action area has **template buttons** (Broadcast, Send Chat, Teleport, Give Item, Log UUID, and TP to holo) that pre-fill the command for you to adjust.

### Example actions

```
# Open a shop menu as the player
Run as: Player   Command: shop open

# 25% chance to give a reward from console
Run as: Console  Command: give {player} Gold 10   Chance: 25

# Teleport the player to a moving destination hologram
Run as: Console  Command: sch tptoholo {player} spawn_portal
```

## Cooldowns

Two independent cooldowns guard against spam, set on the Triggers tab. Both must pass for an action to fire:

- **Cooldown** (default **2 seconds**) is a player-wide cooldown: the minimum time between a player triggering **any** holograms. It stops rapid-fire from double-clicks, auto-clickers, or walking back and forth through a collision hologram. Set it to 0 to disable.
- **Self cooldown** (default off) is the minimum time before the **same player** can trigger the **same hologram** again. Use it for "claim once every N seconds" holograms.

Both apply to interact and collision triggers alike.

## Per-player limits

A hologram can cap how many times each player may trigger it with **max triggers per player** (0 = unlimited). The cap counts interact and collision triggers together, and you choose when it resets:

| Reset mode | When the count resets |
|------------|------------------------|
| **Never** (default) | Never. A cap of 1 means "once, ever". |
| **Restart** | Every server restart ("once per session") |
| **Daily** | 24 hours after that player's last trigger (a rolling per-player "daily reward") |
| **On Join** | Every time the player joins the server |

Combine a cap of 1 with **Daily** reset for a classic daily-reward hologram, or with **Never** for a one-time claim.

## Interaction sound

A hologram can play a sound when interacted with. Pick one from the sound dropdown: **None**, **Crystal**, **Gem**, **Teleport**, **Fire**, or **Portal**.

## Access gates

Whether a player is allowed to trigger a hologram, and whether they can see it at all, is controlled by the per-hologram permission gate and trigger overrides. See [Permissions](permissions.md).
