# Permissions

There are two separate things permissions control in ScuffedHolograms:

1. **Who can manage holograms** (use the commands and the GUI and tool).
2. **Who can see and use a specific hologram** (an optional per-hologram access gate).

---

## Management access (admins)

A player is treated as a ScuffedHolograms admin, and may use `/sch menu`, `/sch tool`, and all other commands, if **any** of the following is true:

- They are a member of a group named (case-insensitive) `OP`, `admin`, `owner`, `staff`, or `moderator`.
- They hold one of these permission nodes:
  - `scuffedholograms.admin`
  - `hytale.command.op.add`
  - `hytale.admin`
  - `hytale.operator`
- The command is run from the **server console**.

### Granting management access without full admin

The node **`scuffedholograms.admin`** grants ScuffedHolograms management **only**: the tool, `/sch menu`, and the other `/sch` commands. It does not confer any other server-admin power. Use it to let a builder or staff member manage holograms without making them a full operator.

With [LuckPerms](integrations.md) installed:

```
/lp user <name> permission set scuffedholograms.admin true
```

or for a group:

```
/lp group <group> permission set scuffedholograms.admin true
```

Without a permissions plugin, server operators (and the console) still have management access through the group and OP checks above. The plugin works normally with no permissions plugin installed.

---

## Per-hologram access gates

Each hologram has an optional permission gate, configured on its **Triggers + Permissions** tab. When enabled, you provide a list of permission nodes and choose how the gate behaves. This is independent from management access above; it controls what ordinary players can do with that hologram.

- **Master toggle.** Off by default. While off, the hologram is fully public.
- **Permission list.** A player passes the gate if they hold **at least one** of the listed nodes (any-pass). This is convenient for rank systems where a player may hold any of several equivalent permissions. With LuckPerms installed, you pick from your existing nodes or type one.
- **Scope.** Choose what failing the gate means:
  - **Interact only (default):** players who fail the gate can still **see** the hologram but cannot trigger its [interaction actions](interactions.md).
  - **Visibility:** players who fail the gate also cannot **see** the hologram at all.

If the master toggle is on but the permission list is empty, the gate does nothing and the hologram stays public, so a half-configured gate never locks everyone out.

### Per-permission trigger overrides

Beyond the access gate, a hologram can define **trigger overrides** keyed by permission node. After a player passes the access gate, the first override whose node the player holds (in list order, so put the most specific first) can adjust how triggers fire for that player:

- **Probability:** replace the action's chance with a flat percent (0 to 100).
- **Trigger cap:** override the per-player trigger limit (0 = unlimited).
- **Allow:** explicitly deny triggering.

Each field is optional. Leave a field unset to keep the hologram's default. This lets you, for example, give VIP players a higher drop chance or a higher daily claim limit on the same hologram.
