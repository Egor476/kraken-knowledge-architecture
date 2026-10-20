---
id: instruction.reordering_addresses
title: Reordering consultation locations
taxonomy:
  - reordering_addresses

module_dependencies:
  common:
    rules:
      - rule.address_management_access
      - rule.primary_address_order
    procedures:
      - procedure.viewing_addresses
      - procedure.reordering_addresses
    ui:
      - ui.settings
      - ui.addresses
      - ui.consultation_location_card
      - ui.address_drag_handle
      - ui.saved_successfully

  conditional:
    public_profile_visibility:
      procedures:
        - procedure.checking_profile_updates

related_instructions:
  - instruction.editing_address
---
# Reordering Consultation Locations/Addresses

## Intent

Guide users through changing the order of existing consultation locations, including checking the result and addressing delayed visibility on the public profile.

## Knowledge selection

Use `module_dependencies` in the YAML front matter as the candidate knowledge pool.

- Retrieve relevant `common` dependencies for access, ordering behavior, the core procedure, and interface guidance.
- Activate `public_profile_visibility` only when the user asks about the public display or reports that the updated order is not visible.
- Retrieve only the module entries necessary for the user's situation.

## Decision logic

1. Identify the user's intended change to the order of existing consultation locations. Distinguish reordering from editing the details of a location when the distinction affects guidance.
2. Apply the relevant access and ordering rules, then guide the user through the reordering procedure using the retrieved UI knowledge.
3. Explain any relevant effect on which location is treated as primary or how locations appear to patients, based on the retrieved rules.
4. If the user reports that the public profile does not reflect the change, activate `public_profile_visibility` and follow the verification procedure. Do not promise immediate publication.

## Scope and handoffs

This instruction covers changing the order of existing consultation locations and checking the resulting display. It does not cover changing address details, creating or deleting locations, or booking configuration.

For other changes of intent, follow the global instruction-routing policy. Use `related_instructions` as optional discovery hints, not automatic dependencies.

## Response requirements

- Prioritize the user's immediate question.
- Provide actionable steps from the selected procedure.
- Apply only ordering and access rules relevant to the user's context.
- Use UI terminology and confirmation cues from retrieved knowledge.
- Do not invent additional controls, publication timing, or guaranteed patient-facing ordering.
- Follow `kraken-global-instructions.md` for localization, permissions, uncertainty, and escalation.

## Completion

Help the user check that the intended order was saved using supported confirmation guidance. If public-profile visibility remains unresolved, explain the supported verification step and any uncertainty without claiming that the public display has updated.
