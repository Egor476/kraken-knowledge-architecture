---
id: instruction.unlinking_doctor
title: Unlinking Dctor from Clinic
taxonomy:
  - managing_linked_doctors

module_dependencies:
  common:
    rules:
      - rule.clinic_unlinking
    procedures:
      - procedure.unlinking_doctor

  conditional:
    pending_invitation:
      rules:
        - rule.clinic_invitations
      procedures:
        - procedure.pending_clinic_invitation

related_instructions:
  - instruction.activating-clinic-profile
---
# Unlinking Doctor from Clinic

## Intent

Guide users seeking to end a doctor's association with a clinic, including distinguishing an established link from a pending invitation.

## Knowledge selection

Use `module_dependencies` in the YAML front matter as the candidate knowledge pool.

- Retrieve relevant `common` dependencies for an existing doctor–clinic association and its removal procedure.
- Activate `pending_invitation` only when the user describes an invitation that has not been accepted or the association status is relevant and unclear.
- Retrieve only the module entries necessary for the user's situation.

## Decision logic

1. Determine whether the user is asking to remove an existing association or address an invitation that has not been accepted. Ask for clarification only if this changes the guidance.
2. For an existing association, apply the retrieved unlinking rule and procedure. Direct the user to the supported responsible role and workflow without assuming the requesting user has the necessary permissions.
3. For a pending invitation, activate `pending_invitation` and follow the relevant procedure rather than treating it as an existing association.
4. If the required access or interface steps cannot be established from the retrieved knowledge, explain the limitation and follow the global escalation policy rather than inventing controls.

## Scope and handoffs

This instruction covers removing an existing doctor–clinic association and handling an unaccepted invitation when it is mistaken for an active link. It does not cover inviting or linking doctors, activating a clinic profile, or modifying shared calendars and schedules.

For other changes of intent, follow the global instruction-routing policy. Use `related_instructions` as optional discovery hints, not automatic dependencies.

## Response requirements

- Prioritize the user's immediate question and relevant next action.
- Apply only the role and association-status rules supported by retrieved knowledge.
- Use the documented procedure without inventing administrator controls, navigation details, or side effects of unlinking.
- Do not imply that an unaccepted invitation creates an active association.
- Follow `kraken-global-instructions.md` for localization, permissions, uncertainty, and escalation.

## Completion

Help the user establish the appropriate next step and, where supported, check whether the association was removed. Do not claim that unlinking has occurred without confirmation.
