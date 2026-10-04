# AgentLink

**Controlled access for AI agents.**

AgentLink is a proposed agent-access gateway for digital systems and connected equipment. Equipment owners or installers define who may connect, what each agent may do, which actions require human approval, and when access ends.

![AgentLink concept: Spencer assists a factory technician through an owner-controlled gateway](docs/assets/agentlink-spencer-concept.png)

## Project status

This repository is a concept and planning starter. It does not yet contain a working gateway or equipment integration. The illustration depicts the intended experience; its “first working example” caption is a goal, not a verified implementation claim.

## Proposed controls

- Approved agent identities and scoped permissions.
- Human approval for sensitive actions such as configuration changes.
- Time-limited sessions with automatic expiry.
- Administrator-controlled extensions during an active session, recorded in the activity log.
- Activity history and an immediate disconnect control.
- Integration-specific enforcement that preserves machine safety controls.

## Example: Spencer in a factory

A technician arrives with Spencer, an AI agent on a handheld device. An authorized owner or administrator grants a 15-minute diagnostic session. Spencer can read the machine's diagnostics through AgentLink. Configuration changes remain blocked until explicitly approved. The administrator can extend the session while it is active or disconnect it immediately. Access ends automatically at the current expiry time.

## Proposed architecture

The agent submits actions to the gateway. The gateway checks identity, session validity, permissions, and any required approval before forwarding an allowed action through an integration for the target system. Session and action events are recorded for review.

Each target system needs its own integration. AgentLink must not bypass equipment interlocks or other safety controls. Revoking agent access is distinct from stopping physical machinery; equipment-specific behavior must be defined by its integration.

## Initial roadmap

- [ ] Define the agent identity, pairing, and session model.
- [ ] Build the Network Studio helper as the first integration.
- [ ] Enforce read-only diagnostics and approval-gated actions.
- [ ] Add automatic expiry, live admin extensions, and revocation.
- [ ] Add an activity log and administrator session view.
- [ ] Validate permission denial, expiry, approval, and disconnect behavior.
- [ ] Document the integration contract before adding equipment adapters.

## Artwork

The concept image features Spencer, the sprout-themed AI character selected for this project. It illustrates the proposed user experience rather than a live product screen.

## License

No open-source license has been selected. Repository visibility alone does not grant reuse rights.
